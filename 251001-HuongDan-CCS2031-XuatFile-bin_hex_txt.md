# HƯỚNG DẪN THIẾT LẬP BUILD VÀ XUẤT FILE THỰC THI

## PHẦN MỀM [CCS V20.3.1](https://www.ti.com/tool/CCSTUDIO#downloads) (Code Composer Studio)

1. Bấm chuột phải vào Project, chọn Properties
2. Chọn Tools -> MSP430 Hex Utility -> Tích chọn vào Enable 'MSP430 HEX Utility'
3. Chọn Build -> Steps -> Chọn Post-build step -> Chọn edit (biểu tượng cây bút)

     - Đánh vào dòng lệnh:

     ```txt
     REM Sinh file BIN (Binary Raw)
     "${CCS_INSTALL_ROOT}/utils/tiobj2bin/tiobj2bin" "${BuildArtifactFileName}" "${BuildArtifactFileBaseName}.bin" "${CG_TOOL_ROOT}/bin/ofd430" "${CG_TOOL_ROOT}/bin/hex430" "${CCS_INSTALL_ROOT}/utils/tiobj2bin/mkhex4bin"
     REM Sinh file HEX (Intel Hex)
     "${CG_TOOL_ROOT}/bin/hex430" --memwidth=8 --romwidth=8 --intel -o "${BuildArtifactFileBaseName}.hex" "${BuildArtifactFileName}"
     REM Sinh file TXT (TI-TXT)
     "${CG_TOOL_ROOT}/bin/hex430" --memwidth=8 --romwidth=8 --ti_txt -o "${BuildArtifactFileBaseName}.txt" "${BuildArtifactFileName}"
    ```

     - Chọn Apply (biểu tượng dấu tích V)
4. Chọn nút Save and Close
5. Nhấn Ctrl + B để build (hoặc chọn menu Project - Build Projects)
