# BÁO CÁO BÀI TẬP VỀ NHÀ – TUẦN 2

* **Họ và tên:** Lê Phi Ân
* **MSSV:** 2374802010204
* **Lớp:** Giới thiệu về học sâu (252_71ITAI40403_0101)
## 1. Công nghệ sử dụng

Nội dung bài tập tập trung vào việc làm chủ thư viện **NumPy** – công cụ nền tảng cho xử lý dữ liệu trong Deep Learning:

* **NumPy ndarray:**
  Khởi tạo mảng và chuyển đổi dữ liệu từ Python List sang Array/Tensor.
* **Indexing & Slicing:**
  Truy xuất phần tử theo vùng, bước nhảy và các chiều khác nhau.
* **Boolean & Fancy Indexing:**
  Lọc dữ liệu bằng mảng điều kiện (`True/False`) hoặc danh sách chỉ số.
* **Array Manipulation:**
  Biến đổi hình dạng ma trận với `reshape`, `flatten`, `ravel`, `take`.
* **Data Splitting:**
  Chia tập dữ liệu Train/Test phục vụ huấn luyện mô hình.

## 2. Cách hoạt động

### Indexing & Slicing

* **Slicing:**
  Sử dụng cú pháp `[start:end:step]` để cắt mảng theo yêu cầu
  *(ví dụ: `x[2:8:2]`)*.
* **Reshape & Flatten:**
  Dùng `.reshape(-1)` hoặc `.flatten()` để làm phẳng dữ liệu trước khi đưa vào mạng thần kinh.
* **Boolean Filtering:**
  Lọc dữ liệu bằng điều kiện logic, kết hợp toán tử `&` (AND) và `|` (OR).

---

### Ứng dụng Logic Ma trận: Tic-Tac-Toe (BTVN 01)

* **Khởi tạo:**
  Tạo bàn cờ 3×3 với giá trị `99` đại diện cho ô trống bằng `np.full`.
* **Tọa độ hóa:**
  Cập nhật nước đi bằng Indexing 2D `board[row, col]`.
* **Kiểm tra hợp lệ:**
  Ngăn chặn việc ghi đè lên ô đã được đánh trước đó.

### Tiền xử lý dữ liệu (BTVN 04)

* **Tạo dữ liệu:**
  Giả lập dữ liệu sinh viên (150 mẫu, 5 đặc trưng) bằng `np.random.rand`.
* **Tách Features & Labels:**

  * `X = data[:, :4]` (4 cột đầu – biến độc lập)
  * `y = data[:, 4]` (cột cuối – nhãn)
* **Chia Train/Test:**
  70% dữ liệu cho huấn luyện, 30% cho kiểm tra.
* **Subsetting:**
  Dùng `np.array_split` để chia `X_train` thành 10 tập con không chồng chéo.

---

## 3. Kết quả đạt được

| Bài tập     | Nội dung           | Ý nghĩa kỹ thuật                           |
| ----------- | ------------------ | ------------------------------------------ |
| **BTVN 01** | Tic-Tac-Toe        | Quản lý trạng thái dữ liệu trên ma trận 2D |
| **BTVN 02** | Indexing ma trận   | Thành thạo truy xuất dữ liệu bằng tọa độ   |
| **BTVN 03** | Boolean Filtering  | Lọc dữ liệu hiệu quả bằng Vectorization    |
| **BTVN 04** | Data Preprocessing | Quy trình chuẩn bị dữ liệu cho mô hình AI  |


