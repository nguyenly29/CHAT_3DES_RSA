![Uploading Screenshot 2025-06-26 163345.png…]()

- Giới thiệu về đề tài
Đây là ứng dụng web đơn giản cho phép hai người dùng trao đổi tin nhắn văn bản theo mô hình ngang hàng (P2P) với mức độ bảo mật cao. Hệ thống sử dụng mã hóa TripleDES, xác thực danh tính bằng RSA, và kiểm tra toàn vẹn dữ liệu với SHA-256, giúp đảm bảo các yêu cầu:
Giữ bí mật nội dung tin nhắn.
Ngăn chặn việc giả mạo danh tính người gửi.
Phát hiện mọi thay đổi, chỉnh sửa dữ liệu trong quá trình truyền tải.
- Công nghệ sử dụng
Python 3
Flask - Framework web đơn giản, dễ triển khai.
PyCryptodome - Thư viện hỗ trợ các thuật toán mã hóa TripleDES, RSA, SHA-256.
HTML/CSS (Templates) - Tạo giao diện người dùng đơn giản.
- Các chức năng chính
Đăng ký tài khoản, sinh cặp khóa RSA cho từng người dùng.
Đăng nhập vào hệ thống.
Hỗ trợ trao đổi khóa mã hóa 3DES an toàn thông qua RSA.
Gửi và nhận tin nhắn được mã hóa TripleDES.
Kiểm tra toàn vẹn dữ liệu bằng SHA-256.
Xác thực chữ ký số RSA để đảm bảo danh tính người gửi.
Hiển thị tin nhắn sau khi xác thực và giải mã thành công.
Cảnh báo nếu dữ liệu bị chỉnh sửa hoặc giả mạo.
- Mô hình hoạt động
1️⃣ Handshake & Trao khóa
Người gửi và người nhận trao đổi khóa công khai RSA.
Người gửi ký thông tin xác thực (ID + thời gian) và gửi khóa 3DES được mã hóa bằng RSA.
2️⃣ Gửi tin nhắn an toàn
Nội dung tin nhắn được mã hóa TripleDES (CBC mode) với khóa bí mật.
Tạo giá trị băm SHA-256 kiểm tra toàn vẹn.
Ký số bằng RSA đảm bảo tính xác thực.
3️⃣ Phía người nhận
Giải mã khóa 3DES bằng RSA.
Kiểm tra toàn vẹn dữ liệu.
Xác thực chữ ký số.
Nếu hợp lệ: giải mã và hiển thị tin nhắn.
Nếu không hợp lệ: cảnh báo nguy cơ giả mạo hoặc chỉnh sửa dữ liệu.
