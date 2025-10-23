# QUY ĐỊNH ĐẶT TÊN NHÁNH TRONG FW GIT

Quy định đặt tên nhánh trên git áp dụng cho OXIITEK FIRMWARE

---

## Phiên bản tài liệu

### V1.0

- Phiên bản đầu tiên của tài liệu
- Người tạo: Đàm Duân - PRD Manager
- Ngày tạo: 02/10/2025

### V1.1

- Thay đổi quy định về kí tự phân cách, quy định về viết hoa và viết thường của tên nhánh
- Người tạo: Đàm Duân - PRD Manager
- Ngày tạo: 02/10/2025

## Nội dung

| 1             | 2 | 3             | 4 | 5                 | 6 | 7                 | 8 | 9                         |
|:-------------:|:-:|:-------------:|:-:|:-----------------:|:-:|:-----------------:|:-:|:-------------------------:|
| Mã Project    | / | Mã phần cứng  | / | Mã đối tượng FW   | / | Mã Chip Target    | / | Mã giai đoạn phát triển   |

### Mô tả

1. **Mã Project**
     - Viết thường
     - Đặt tên theo mã của Project theo bảng dưới đây:

     |Tên Project    |Mã Project |Mô tả                              |
     |:--------------|:---------:|:----------------------------------|
     |Smart Switch   |SWT        |Công tắc thông minh                |
     |Smart Socket   |SSK        |Ổ cắm thông minh                   |
     |Ind Cooker     |IND        |Bếp từ                             |
     |VRV            |VRV        |Bộ điều khiển điều hòa thông minh  |
     |JIG            |JIG        |FCT-PRD JIG                        |
     |ERW            |ERW        |Bộ điều khiển cửa                  |
     |Beacon         |BCN        |Chấm công thông minh               |
     |Sensor         |SEN        |Cảm biến                           |

2. **_**

     Kí tự phân cách

3. **Mã phần cứng**
     - Mã PCBA được in trên thiết kế PCB
     - Phải được viết hoa toàn bộ
     - Phiên bản phần cứng, lưu ý không sử dụng kí tự **'.'** , ví dụ V4.1 thì viết là V41
     - Tổng số ký tự không vượt quá 20 kí tự
     - Ví dụ: Mã công tắc: SW2S-M4-V4.1 được viết là SW2S-M4-V41

4. **/**

     Kí tự phân cách

5. **Mã đối tượng FW**
     - Viết thường
     - Đặt theo Mã dưới đây:

    | Loại          | Mã |Mô tả                                                         |
    |:--------------|:--:|:-------------------------------------------------------------|
    |FW USER        | U  |FW dành cho thực thi sản phẩm ra thị trường                   |
    |FW FACTORY     | F  |FW dành cho quá trình sản xuất, thực thi cấu hình, cài đặt    |

6. **_**

     Kí tự phân cách

7. **Mã Chip Target**
     - Viết thường
     - Đặt theo Mã dưới đây:

     | Loại MCU  |Mô tả                                          |
     |:----------|:----------------------------------------------|
     |ESP32      | Espressif ESP32 family                        |
     |MSP430     | TI MSP430 family                              |
     |RX140      | Renesas RX140 familyt                         |
     |HT45F      | Holtek HT45F family (HT45F0074A/HT45F0075)    |
     |BS86D      | Holtek BS86D family (BS86D20)                 |
     |STM32F4    | ST Microelectronic STM32F4 family             |

8. **_**

     Kí tự phân cách

9. **Mã giai đoạn phát triển**
     - DEV: Mã cho DEV phát triển tính năng, Developer của Team sẽ phát triển và tự code tính năng trên này
     - STG: Chạy thử nghiệm trên Server STG, khi pull code lên git, sẽ tự động sinh mã qua CI/CD
     - PROD: Chạy chính thức trên Server Production, khi pull code lên git, sẽ tự động sinh mã qua CI/CD
