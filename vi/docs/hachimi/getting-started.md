# Bắt đầu

## Độ tương thích

Hãy kiểm tra độ tương thích trước khi cài đặt.

### Windows
| Phiên bản | Hỗ trợ |
| --- | :---: |
| JP | ✅ |
| KR | ⚠️ |

### Android

| Phiên bản | Cài đặt thường | Cài trực tiếp |
| --- | :---: | :---: |
| JP | ✅ | ✅ |
| KR | ⚠️ | ⚠️ |
| TW GP | ⚠️ | ❔ |
| TW MC | ⚠️ | ⚠️ |
- ✅ - Hỗ trợ hoàn toàn.
- ⚠️ - Hoạt động, nhưng game không chịu bởi vì một tác nhân ngoài lề (chẳng hạn như ch.trình chống hack).
- ❔ - Có thể hoạt động, không chắc chắn.
- ❌ - Không hỗ trợ.


## Hướng dẫn cài đặt

### Windows

Tính đến phiên bản v0.13.0, Hachimi hiện đang hỗ trợ 2 cách chạy với các bước cài đặt khác nhau. **Chỉ chọn một cách chạy duy nhất, và chỉ sử dùng trình cài đặt hoặc cài đặt bằng cách thủ công, ĐỪNG dùng nhiều thứ cùng lúc.**

#### Cách 1: DotLocal DLL redirection (UnityPlayer.dll) (khuyên dùng)

::: warning
Một số ch.trình chống hack như Vanguard sẽ phát hiện bạn sử dụng tính năng DLL redirection, ngay cả khi nó không ảnh hưởng trực tiếp đến game mà nó đăng bảo vệ. Sử dụng cách 2 hoặc tắt DLL redirection mỗi khi bạn muốn chơi game sử dụng Vanguard hoặc một ch.trình chống hack khác kiểm tra giống như vậy.
:::

- Sử dụng trình cài đặt: Tải về file `hachimi_installer.exe` dành cho bản mới nhất từ [trang Releases](https://github.com/Hachimi-Hachimi/Hachimi/releases). Mở nó lên, **chọn Target "UnityPlayer.dll"** và nhấn vào nút Install.

When installing for the first time, the installer might ask to you enable DotLocal DLL redirection. Press OK and it will be enabled for you. **You will need to restart your computer after enabling for it to work.**

Khi bạn cài đặt lần đầu, trình cài đặt có thể sẽ hỏi bạn có muốn bật DotLocal DLL redirection hay không. Nhấn OK và nó sẽ được bật lên cho bạn. **Bạn sẽ phải khởi động lại máy sau khi bật để nó có thể hoạt động.**

- **Thủ công**
1. Mở Command Prompt (Run as Administrator) và chạy lệnh sau:
```
reg add "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options" /v DevOverrideEnable /t REG_DWORD /d 1
```
2. Khởi động lại máy.
3. Tải về file `hachimi.dll` dành cho bản mới nhất từ [trang Releases](https://github.com/Hachimi-Hachimi/Hachimi/releases).
4. Trong thư mục cài đặt game, tạo một thư mục mới có tên là `umamusume.exe.local` và di chuyển file DLL mà bạn vừa tải về vào trong. Sửa tên lại thành `UnityPlayer.dll`.

#### Cách 2: Plugin shimming (cri_mana_vpx.dll)

Bạn sẽ phải cài đặt **cả hai** thứ này:

- **Hachimi**
    - **Sử dụng trình cài đặt:** Tải về file `hachimi_installer.exe` dành cho bản mới nhất từ [trang Releases](https://github.com/Hachimi-Hachimi/Hachimi/releases). Mở nó lên, **chọn Target "cri_mana_vpx.dll"** và nhấn vào nút Install.
    - **Thủ công:** Tải về file `hachimi.dll` dành cho bản mới nhất từ [trang Releases](https://github.com/Hachimi-Hachimi/Hachimi/releases) và di chuyển nó vào `C:\Windows\System32`, đặt tên là `cri_mana_vpx.dll`.
- **Shinmy (shim dành cho DMM)**
    - **Sử dụng trình cài đặt:** Tải về file `shinmy_installer.exe` dành cho bản mới nhất từ [trang Releases](https://github.com/Hachimi-Hachimi/Shinmy/releases). Mở nó lên và nhấn vào nút Install. Không cần chỉnh sửa các tùy chọn nếu bạn không biết công dụng của chúng. Trong trường hợp trình cài đặt không thể tìm thấy thư mục cài đặt của DMM, bạn sẽ phải tự chọn nó.
    - **Thủ công:** Tải về file `shinmy_mallet.dll` dành cho bản mới nhất từ [trang Releases](https://github.com/Hachimi-Hachimi/Shinmy/releases) và di chuyển nó vào thư mục cài đặt DMM. Đổi tên thành `version.dll` hoặc `winhttp.dll`.

::: warning
Sau khi cài đặt Shinmy, mỗi lần mà bạn mở DMM lên, nhiều chương trình có tên như `shinmy.exe` sẽ cố gắng chạy cùng nó. Hãy cho phép tất cả các chương trình đó chạy để shim có thể hoạt động đúng cách.
:::

### Android

Cài đặt bằng [UmaPatcher](https://github.com/LeadRDRK/UmaPatcher) là cách dễ nhất vì nó sẽ chỉnh sửa file APK cho bạn. Khuyến khích không nên cài đặt game trước khi sử dụng.

::: danger
Nếu như bạn đã cài đặt game trước đó, bạn phải gỡ cài đặt trước khi cài bản đã được patch lần đầu tiên. Sau này, bạn có thể
cập nhật game mà không cần gỡ cài đặt bằng cách cài một phiên bản mới đã được patch.
:::

1. Tải về và cài đặt phiên bản UmaPatcher mới nhất từ [trang Releases](https://github.com/LeadRDRK/UmaPatcher/releases).
2. Chuẩn bị một trong các gói cái đặt game sau đây:
    - **Các file Split APK:** Một file APK base và một trong những file APK split config (config.arm64_v8a, config.armeabi-v7a, v.v.),
    chỉ chọn một file split config phù hợp với thiết bị của bạn.
    Hiện tại chỉ được sử dụng bởi bản JP.
    - **File APK riêng lẻ**: Một file APK đầy đủ.
    - **File XAPK**: Một file ZIP chứa các file Split APK (có đuôi file được sửa lại thành XAPK).
3. Mở UmaPatcher và chọn "Cài đặt thường". Chọn các file mà bạn đã chuẩn bị.
4. Nhấn vào nút Vá để bắt đầu quá trình vá và cài đặt ứng dụng.

Bạn sẽ phải lặp lại quy trình này từ bước 2 mỗi lần cập nhật app game.

#### Dành cho người dùng root
UmaPatcher hỗ trợ một phương thức cài đặt sử dụng root mà không cần yêu cầu bạn gỡ cài đặt game và cho phép game được cập nhật như thường từ bất kì cửa hàng ứng dụng nào.

Khi game đã được cài đặt, nhấn vào thẻ ở phía trên màn hình chính để chọn ứng dụng mà bạn muốn patch (nếu cần). Sau đó, chọn "Cài trực tiếp" làm phương thức cài đặt rồi nhấn vào nút Vá. Không cần chọn bất kì file nào.

Bạn sẽ phải cài đặt lại mỗi khi app game được cập nhật.

#### Thủ công
1. Build hoặc tải các thư viện đã được build sẵn từ [trang Releases](https://github.com/Hachimi-Hachimi/Hachimi/releases).
2. Giải nén file APK của game. Bạn có thể dùng [apktool](https://apktool.org/) cho bước này.
3. Sửa tên file `libmain.so` cho từng thư mục bên trong thư mục `lib` thành `libmain_orig.so`.
4. Copy các file thư viện mới vào các thư mục tương ứng (v.d. `libmain-arm64-v8a.so` sẽ nằm trong `lib/arm64-v8a`). Sửa tên của chúng thành `libmain.so`.
5. Build file APK và cài đặt.

## Thiết lập lần đầu
Lúc mở game lần đầu tiên sau khi đã cài Hachimi, hộp thoại này sẽ hiện lên:

![First Time Setup](/assets/first-time-setup.jpg)

*Nếu bạn không thấy nó, Hachimi đã không được cài đặt đúng cách. Hãy xem hướng dẫn cài đặt và thử lại.*

Nhấn vào nút Next và chọn bản dịch mà bạn muốn, rồi nhấn vào nút Done để lưu các thiết lập của bạn và bắt đầu kiểm tra cập nhật.

Hachimi sẽ báo bạn tải về một bản cập nhật mới dành cho bản dịch, nhấn vào nút Yes để tải về các file dịch.