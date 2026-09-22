# THỰC HÀNH SẮP XẾP VÀ VẼ SƠ ĐỒ TUẦN TỰ CHỨC NĂNG ĐẶT XE RIKKEILOGISTICS
## Bước 1: Sắp xếp lại đúng thứ tự thời gian
1. Khách hàng gửi taoDonHang() tới App Điều Phối

2. App Điều Phối gửi yêu cầu nhận đơn sang Điện thoại Tài xế (không chờ ngay lập tức)

3. Điện thoại Tài xế phản hồi Đồng ý/Từ chối về cho App Điều Phối (đây là một thông điệp độc lập, không bắt buộc phải là Return, vì yêu cầu gửi đi ở bước trước là Async — Tài xế không bị "giữ chờ" nên phản hồi có thể đến sau, tại một thời điểm bất kỳ)

4. alt
[Tài xế đồng ý] App Điều Phối khởi tạo một bản ghi Chuyến Đi (Trip) mới — lifeline của Trip bắt đầu đúng tại thời điểm này, chỉ xảy ra nếu tài xế Đồng ý

[Tài xế không đồng ý] App Điều Phối không khởi tạo bản ghi Chuyến Đi (Trip)

5. App Điều Phối báo cho Khách hàng kết quả cuối cùng ("Đã tìm thấy xe" hoặc "Không tìm được tài xế") — bước này nằm ngoài khối alt, phía sau cả 2 nhánh, vì nó luôn xảy ra dù tài xế đồng ý hay từ chối

## Bước 2: Vẽ sơ đồ hoàn chỉnh 
