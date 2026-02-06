# BÁO CÁO BÀI TẬP VỀ NHÀ – TUẦN 2

* **Họ và tên:** Lê Phi Ân  
* **MSSV:** 2374802010204  
* **Lớp:** Giới thiệu về học sâu (252_71ITAI40403_0101)

---

## Giới thiệu

Repository này chứa **Bài tập về nhà – Tuần 2**, tập trung vào việc sử dụng thư viện **Pandas** để tiền xử lý và phân tích dữ liệu phục vụ cho môn **Giới thiệu về học sâu**.  
Nội dung bài tập bao gồm các thao tác cơ bản với Series, DataFrame, indexing, xử lý dữ liệu thiếu, aggregation và gộp dữ liệu.

---

## 1. Công nghệ sử dụng

* **Python 3**
* **Pandas**
* **NumPy**

---

## 2. Kiến thức Pandas

### Pandas Series
* Series là mảng **một chiều có chỉ mục (index)**.
* Có thể khởi tạo từ list hoặc NumPy array.
* Truy cập dữ liệu bằng **index số**, **slice**, hoặc **index chữ**.
* Các thuộc tính quan trọng:
  * `.values`: dữ liệu dạng mảng
  * `.index`: nhãn chỉ mục

### Pandas DataFrame
* DataFrame là cấu trúc dữ liệu **hai chiều**, gồm hàng (index) và cột (columns).
* Được tạo từ dictionary với key là tên cột.
* Truy cập cột bằng:
  * `df['column']` (khuyến nghị)
  * `df.column` (hạn chế khi trùng tên method)

---

## 3. Cách hoạt động

### Indexing & Slicing trong DataFrame
* **loc**:
  * Truy cập theo **nhãn index**
  * Slice **bao gồm điểm cuối**
* **iloc**:
  * Truy cập theo **vị trí số**
  * Slice **không bao gồm điểm cuối**
* Nên dùng `iloc` khi làm việc với index số để tránh nhầm lẫn.

---

### DataFrame Indexing & Feature Engineering
* Truy cập cột bằng dictionary-style hoặc attribute-style.
* Có thể **tạo cột mới** trực tiếp bằng phép gán.
* Dùng **boolean masking** để lọc dữ liệu.
* Fancy indexing giúp chọn dữ liệu linh hoạt theo điều kiện.

---

### Broadcasting & Index Alignment
* Pandas tự động **căn chỉnh index** khi thực hiện phép toán.
* Khi index không khớp → sinh giá trị **NaN**.
* Series có thể broadcast theo hàng hoặc cột trong DataFrame.

---

## 4. Bài tập về nhà 1 – Tiền xử lý dữ liệu tuổi thọ

### Quy trình thực hiện
* Đọc file `howlongwelive.csv` vào DataFrame.
* Khám phá dữ liệu:
  * Xem dòng đầu/cuối
  * Kiểm tra shape
  * Thống kê với `.describe()`
* Làm sạch dữ liệu:
  * Xóa cột **Hepatitis B** và **Population** do chứa nhiều NaN
  * Chuyển cột **Status** từ chuỗi sang số bằng `.map()`:
    * Developing → 0
    * Developed → 1
  * Đổi tên cột *thinness* cho thống nhất
* Tách dữ liệu:
  * **X**: tất cả cột trừ *Life expectancy*
  * **y**: cột *Life expectancy*
  * Chuyển sang NumPy array

### Kết quả
* DataFrame còn **2938 × 20**
* **X** là mảng đặc trưng, **y** là mảng nhãn

---

## 5. Handling Missing Data

* Giá trị thiếu được biểu diễn bằng **np.nan**
* Các phương pháp xử lý:
  * `isnull()`, `notnull()`
  * `dropna()`
  * `fillna()` (điền bằng mean)
* Lưu ý: điền NaN có thể ảnh hưởng đến phân phối dữ liệu.

---

## 6. DataFrame Concatenation & Merge

* **concat**:
  * Nối DataFrame theo hàng hoặc cột
  * Mặc định join kiểu outer
* **merge**:
  * Gộp bảng theo khóa chung (tương tự SQL join)

---

## 7. Bài tập về nhà 2 – Phân tích & gộp dữ liệu

### Các bước thực hiện
* Điền toàn bộ giá trị NaN bằng **mean** của từng cột.
* Groupby theo **Country** để:
  * Tính tuổi thọ trung bình
  * Tìm quốc gia có tuổi thọ cao nhất và thấp nhất
* Groupby theo **Status** để so sánh:
  * Developed vs Developing
* Tạo DataFrame phụ gồm:
  * `ID` (trùng Country)
  * `Noise_level` (giá trị ngẫu nhiên)
* Merge vào bảng chính theo ID

### Kết quả
* Dữ liệu không còn NaN
* Quốc gia phát triển có tuổi thọ trung bình cao hơn rõ rệt
* Bảng cuối cùng có thêm cột **Noise_level**

---

## 8. Kết quả đạt được

| Bài tập | Nội dung | Ý nghĩa kỹ thuật |
|--------|---------|------------------|
| **BTVN 01** | Tiền xử lý dữ liệu tuổi thọ | Làm sạch, mã hóa và chuẩn bị dữ liệu cho mô hình |
| **BTVN 02** | Phân tích & gộp dữ liệu | Thống kê theo nhóm và kết hợp nhiều nguồn dữ liệu |

