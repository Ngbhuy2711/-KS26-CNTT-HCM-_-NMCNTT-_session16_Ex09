# Phần 1 : phân tích 2 giải pháp xác thực
 - 3 yếu tố xác thực
   + Syk : mật khẩu
   + syh : Mã otp/điện thoại
   + Sya : vân tay/khuôn mặt
 - khi bật 2FA : mật khẩu = know ; mã otp = have
 - Nguyên lý TOTP khi Offline: Điện thoại và server dùng chung Khóa bí mật (Shared Secret) và Mốc thời gian chuẩn (Unix Epoch). Điện thoại dùng chip thạch anh tự đếm giờ để tính ra mã OTP đếm lùi 30 giây hoàn toàn độc lập, không cần mạng.
# phần 2 : lập bảng so sánh trade-off và ra quyết định
| tiêu chí | SMS OTP | TOTP authenticator |
| :--- | :---: | ---: |
| chống sim swapping và ss7 | kém | tuyệt đối |
| tính sẵn sàng |  phụ thuộc sóng di động | sẵn sàng 100% online |
| chi phí vận hành | tốn phí gửi tin nhắn | miễn phí |
| mất điện thoại | làm lại sim | cần backup code / mã hóa cloud sync |

- quyết định cho studio là chọn authenticator
- lý do : loại bỏ nguy cơ sim swapping nhắm vào ban sáng lập , đồng thời cho phép kỹ sư làm việc khi đi GDC hay trên máy bay ko có sóng
# phần 3
Mục đích: Là 10 "chìa khóa phụ" dùng 1 lần để cấp cứu mở tài khoản khi mất hoặc hỏng điện thoại sinh mã.

2 vị trí lưu an toàn:

In ra giấy vật lý cất trong két sắt / tủ cá nhân có khóa.

Lưu tệp mã hóa trong phần mềm Quản lý mật khẩu (Password Manager) có Master Key.

1 sai lầm tai hại cần tránh: Chụp ảnh màn hình lưu trong album ảnh điện thoại hoặc gửi qua tin nhắn chat không mã hóa (Zalo, Telegram, Ghi chú), vì dính malware là lộ toàn bộ mã dự phòng.

