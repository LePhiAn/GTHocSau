Họ và tên: Lê Phi Ân
MSSV: 2374802010204
Lớp: Giới thiệu về học sâu :252_71ITAI40403_0101

1. Công nghệ sử dụng
    BTVN 01 & 02: PyTorch Autograd (Cơ chế tự động tính đạo hàm) và thuật toán tối ưu hóa Gradient Descent.
    BTVN 03: Linear Regression (Hồi quy tuyến tính) và kỹ thuật tạo dữ liệu giả lập (Synthetic Data).
    BTVN 04: Memory Management (Quản lý bộ nhớ) giữa hai thư viện NumPy và PyTorch.
    BTVN 05: Tensor Manipulation (Các hàm khởi tạo và biến đổi hình dạng ma trận).
2. Cách hoạt động
    Gradient và Gradient Descent (01 & 02): Khai báo biến: Dùng requires_grad=True để đánh dấu biến cần tính đạo hàm.
    Lan truyền ngược (Backpropagation): Dùng .backward() để máy tự tính độ dốc tại một điểm.
    Cập nhật: Dùng vòng lặp để thay đổi giá trị $x$ theo hướng ngược lại với độ dốc nhằm tìm điểm thấp nhất của hàm số.
    Hồi quy tuyến tính (03): Tạo dữ liệu: Dùng torch.randint và torch.randn để tạo ra X (giờ học) và Y (điểm số) theo công thức có sẵn nhiễu.
    Học từ dữ liệu: Máy tính lặp lại quy trình: Dự đoán -> So sánh sai số (Loss) -> Chỉnh sửa hệ số $w$ và $b$ thông qua đạo hàm.
    Quản lý bộ nhớ (04): from_numpy: Chỉ tạo một "lớp vỏ" bọc ngoài mảng cũ, dùng chung địa chỉ ô nhớ.torch.tensor: Cấp phát vùng nhớ mới, sao chép toàn bộ dữ liệu sang một thực thể độc lập.
    Khởi tạo và Reshape (05): Sử dụng các hàm zeros, ones, rand để tạo nhanh dữ liệu mẫu.
Dùng view và view_as để sắp xếp lại số lượng hàng/cột mà không làm thay đổi giá trị gốc của Tensor.
3. Kết quả
    BTVN 01 & 02: Tìm được giá trị x tối ưu khiến hàm số đạt giá trị nhỏ nhất (cực tiểu).
    BTVN 03: Máy tính tự tìm ra được các hệ số w = 3 và b = 5 gần chính xác với công thức gốc dù ban đầu chỉ được cho các con số ngẫu nhiên.
    BTVN 04:
        Trường hợp 1 (from_numpy): Thay đổi mảng gốc thì Tensor thay đổi theo.
        Trường hợp 2 (torch.tensor): Thay đổi mảng gốc thì Tensor vẫn giữ nguyên.
    BTVN 05: Chuyển đổi linh hoạt cấu trúc dữ liệu (ví dụ từ mảng 1 chiều 10 phần tử thành ma trận 2x5 hoặc 5x2) để chuẩn bị cho các bước tính toán trong mạng thần kinh.