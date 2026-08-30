# FurniFlow
### Hệ thống quản lý & bán hàng nội thất

> *Tên dự án "FurniFlow" là tên đề xuất tạm thời — thay bằng tên chính thức khi cần.*

---

## Giới thiệu

**FurniFlow** là hệ thống thương mại điện tử chuyên biệt cho ngành nội thất, ra đời nhằm giải quyết một bài toán đặc thù mà các nền tảng bán hàng thông thường chưa đáp ứng tốt: **sản phẩm nội thất không phải là một mặt hàng cố định, mà là một tổ hợp có thể tùy biến** — kích thước, chất liệu, màu sắc, phụ kiện đi kèm.

Thay vì bán các sản phẩm có sẵn theo size chuẩn, FurniFlow cho phép khách hàng tự cấu hình sản phẩm theo nhu cầu (ví dụ: một chiếc sofa dài 2m2, bọc da thật, khung gỗ sồi), đồng thời hệ thống tự động tính toán giá và kiểm tra khả năng đáp ứng (tồn kho nguyên liệu, thời gian sản xuất) ngay lập tức.

## Bài toán nghiệp vụ cần giải quyết

- **Giá không cố định theo SKU** mà phụ thuộc vào công thức tính theo diện tích/khối lượng nguyên liệu, loại chất liệu, và độ phức tạp gia công.
- **Tồn kho không quản lý ở cấp thành phẩm** mà ở cấp nguyên liệu thô (gỗ, vải, da, khung sắt...), do sản phẩm chỉ được ráp/sản xuất sau khi có đơn hàng.
- **Trải nghiệm chọn mua phức tạp hơn thương mại điện tử thông thường**, khách hàng cần hình dung được sản phẩm trông như thế nào với từng lựa chọn trước khi quyết định mua.

## Đối tượng sử dụng

- **Khách hàng cuối:** duyệt sản phẩm, tùy biến cấu hình, xem giá và đặt hàng.
- **Đội vận hành/kho:** theo dõi tồn kho nguyên liệu, xử lý đơn hàng.
- **Đội kinh doanh/quản lý:** theo dõi đơn hàng, doanh thu, cấu hình bảng giá chất liệu.

## Giá trị mang lại

- Rút ngắn thời gian tư vấn và báo giá thủ công — khách hàng tự xem giá ngay khi tùy chỉnh.
- Giảm rủi ro nhận đơn vượt quá khả năng cung ứng nguyên liệu nhờ kiểm tra tồn kho thời gian thực.
- Nâng cao trải nghiệm mua sắm nhờ khả năng trực quan hóa sản phẩm theo từng lựa chọn.
- Chuẩn hóa dữ liệu cấu hình sản phẩm, làm nền tảng mở rộng sang các kênh bán khác (đại lý, showroom) trong tương lai.

## Định hướng kiến trúc

Hệ thống được xây dựng theo mô hình **tách biệt Backend (API) và Frontend (Web/App)**, phù hợp với đặc thù nghiệp vụ:

- **Backend** đảm nhiệm phần "trí tuệ" của hệ thống — tính giá theo công thức, kiểm tra và khóa tồn kho theo thời gian thực, đảm bảo dữ liệu đơn hàng nhất quán.
- **Frontend** đảm nhiệm phần trải nghiệm người dùng — hiển thị trực quan các biến thể sản phẩm, phản hồi tức thời khi khách hàng thay đổi lựa chọn.

Việc tách biệt này giúp hai đội phát triển độc lập, đồng thời cho phép hệ thống dễ dàng mở rộng thêm các kênh giao diện khác (app di động, tích hợp đại lý...) mà không cần thay đổi logic nghiệp vụ lõi.

## Tài liệu liên quan

- [Phân rã kỹ thuật tính năng Đặt hàng & Tùy biến chất liệu/kích thước](./phan-ra-ky-thuat-dat-hang-tuy-bien-noi-that.md)