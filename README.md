<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/cd5a80b1-23f9-4238-90ae-5daf05e62fe1" /># BÁO CÁO BÀI TẬP 7 - NHÓM 3

- GVHD: Nghi Hoàng Khoa
- Sinh viên thực hiện:
    + 24520213 - Hoàng Ngọc Uyên Chi
    + 24520450 - Nguyễn Ngọc Hân

## Các lỗi xuất hiện trong source code.
### Nhóm lỗi syntax:
1. File customers.php: lỗi thiếu dấu ngoặc vuông đóng mảng khi truy cập phần tử:
    ```
    if($customer['active'))
    ```
    => Cách khắc phục: thêm ] thành:
    ```
    if($customer['active'])
    ```

2. File reports.php: Khai báo biến mảng thiếu dấu ';' kết thúc câu lệnh:
    ```
    $reportRows = []
    ```
    => Cách khắc phục: Thêm ';' vào cuối thành:
    ```
    $reportRows = [];
    ```

3. File settings.php: Khai báo mảng cấu hình bị thiếu dấu đóng mảng, kết thúc bằng ';' thay vì '];'

    => Cách khắc phục: Sửa lại thành '];' ở cuối mảng '$config'

### Nhóm lỗi logic:
1. File checkout.php: Tính tổng tiền giỏ hàng ($subtotal) bị sai do dùng toán tử gán '=', khiến giá trị bị ghi đè qua mỗi vòng lặp.

    => Đổi thành toán tử cộng dồn += để tính tổng tất cả sản phẩm.

2. File dashboard.php: Tính sai tổng doanh thu ($totalRevenue). Điều kiện đang cộng dồn các đơn hàng đang chờ (pending).

    => Đổi điều kiện lọc sang trạng thái hoàn thành: 
    ```
    if ($order['status'] === 'completed').
    ```

3. File dashboard.php: Hiển thị sai danh sách "Low shelf SKUs". Dùng điều kiện $product['stock'] < 1 (hết sạch hàng) nên không hiển thị được các món sắp hết (như Campus Gel Pen tồn kho 1).

    => Đổi điều kiện cảnh báo thành < 5.

4. File orders.php: Bảng hàng chờ lấy (Pickup queue) liệt kê sai dữ liệu. Vòng lặp đang lọc ra các đơn hàng đã hoàn thành (completed).

    => Đổi chuỗi so sánh thành 'pending' (hoặc 'waiting') để hiển thị đúng đơn hàng chờ.

5. File reports.php: Báo cáo tồn kho (Shelf report) gom nhóm sai. Đang sử dụng tên sản phẩm ($product['name']) làm key để nhóm, khiến báo cáo bị xé lẻ.

    => Đổi lại thành dùng đúng trường danh mục: 
    ```
    $category = $product['category'];.
    ```
## Kết quả chạy được sau khi sửa lỗi:
<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/a4264f2d-3922-4cbc-bfcd-5ec3d86aa212" />
<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/cb20a1db-f2f0-45a7-b608-67cb5c0c8e6a" />
<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/d2bea392-734e-4340-bb97-52313c13aa66" />
<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/c93d1814-6526-4c70-9fb5-e6ce1bf057c2" />
<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/ab37fca2-ab20-40bd-ad39-3dd758a7fe03" />
<img width="1850" height="1005" alt="image" src="https://github.com/user-attachments/assets/0f27178a-bb20-4d58-99ae-87485c878d11" />





