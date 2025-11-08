# HƯỚNG DẪN TẠO VÀ SỬ DỤNG SSH KEY

Sử dụng SSH KEY cho bước xác thực khi thao tác với Git Repo

---

## Mục tiêu

- Tạo SSH Key theo tiêu chuẩn ED25519
- Thêm SSH Key vào Github
- Thêm SSH Key vào Gitlab
- Clone repo git

## Nội dung

### Tạo SSH Key

- Chuẩn SSH ED25519 được khuyến khích sử dụng từ Github, Gitlab,...
- Thư mục ssh mặc định

    ```text
    1. Hệ điều hành Windows
    %USERPROFILE%\.ssh\

    2. Hệ điều hành Linux (Ubuntu)
    ~/.ssh/
    ```

- SSH Key có thể được tạo từ Windows Powershell hoặc bash:

    ```bash
    cd ~/.ssh
    ssh-keygen -t ed25519 -C "johhnydam204@github" -f id_github_ed25519
    ```

  **Lưu ý:**
  - Sửa `"johhnydam204@github"` thành tên của bạn.
  - Sửa `id_github_ed25519` thành tên key mà bạn muốn. Tên cần đồng bộ với bước sau.
  - Thêm mật khẩu cho ssh key nếu muốn, không thì để trống.

### Thêm khai báo SSH Key vào ssh config

- Mở file `config` tại thư mục `~/.ssh/` bằng trình soạn thảo văn bản
  - Windows: notepad, vscode, notepadd++, ...
  - Linux: nano
- Thêm nội dung vào file `config`

```text
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_github_ed25519
```

  **Lưu ý:** `id_github_ed25519` cần phải trùng tên với tên key đã tạo ở bước trước.

### Điền mã Pubic Key lên Git Server

1. **Github**

    - Vào **Settings** => **SSH & GPG keys**
    - Mục **SSH keys**, chọn `New SSH key`

2. **Gitlab**

    - Vào **User Settings** => **SSH Keys**
    - Mục **SSH Keys**, chọn `Add new key`

3. Copy nội dung `id_github_ed25519.pub` vào mục key

    - Trong Windows Powershell hoặc Bash, thêm lệnh:

    ```bash
    cat id_github_ed25519.pub
    ```

    - Sao chép toàn bộ nội dung vào mục key trên git server

    - Đặt Title tùy chọn cho key, ví dụ: ***Johnny@OXII-PC key***

### Kiểm tra kết nối

```bash
ssh -T git@github.com
```

Bạn sẽ nhận được kết quả kết nối thành công:

```text
The authenticity of host 'github.com (20.205.243.166)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'github.com' (ED25519) to the list of known hosts.
Hi johnnydam204! You've successfully authenticated, but GitHub does not provide shell access.
```

### Sử dụng ssh key để clone repo

- Khi clone, sử dụng loại SSH thay vì HTTPS
- Ví dụ: `git@github.com:jd-fwhub/mw_wifi.git`
