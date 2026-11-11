# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` | Phương tiện cơ giới chở người, thường có 4 bánh, thiết kế chủ yếu để chở hành khách. | Sedan, hatchback, SUV, coupe. SUV vẫn được xếp vào `car`, không phải `truck`. |
| `truck` | Phương tiện cơ giới được thiết kế chủ yếu để vận chuyển hàng hóa, thường có khoang chở hàng riêng hoặc thùng hàng. | Xe tải thùng, xe ben, xe tải đông lạnh, xe đầu kéo có rơ-moóc. |
| `bus` | Phương tiện cơ giới được thiết kế chủ yếu để chở nhiều hành khách, thường có khoang hành khách lớn và nhiều ghế ngồi. | Xe buýt thành phố, xe khách, xe buýt trường học. |
| `van` | Phương tiện cơ giới có thân xe dạng hộp, khoang chở người hoặc hàng hóa kết hợp, thường nhỏ hơn xe tải và có thiết kế thân liền. | Minivan, cargo van, passenger van. |

## Quy tắc chung

- Box bám sát vật thể nghĩa là:
    - Sử dụng hình chữ nhật nhỏ nhất có thể bao quanh toàn bộ phần nhìn thấy được của phương tiện.
    - Không cắt mất các bộ phận nhìn thấy được như gương chiếu hậu, cản xe hoặc bánh xe.
    - Không lấy quá nhiều vùng nền xung quanh phương tiện.
    - Box phải bao quanh một phương tiện riêng biệt, không gộp nhiều phương tiện vào cùng một box.

- Vật thể bị che khuất:
    - Chỉ vẽ box bao quanh phần phương tiện thực sự nhìn thấy được.
    - Không tự suy đoán hoặc mở rộng box để bao gồm phần bị phương tiện khác che khuất.
    - Nếu hai phương tiện che khuất nhau, phải tạo hai box riêng biệt nếu có đủ bằng chứng nhận diện được từng phương tiện.
    - Nếu chỉ nhìn thấy một phần quá nhỏ và không thể xác định lớp, chuyển sang trạng thái cần review hoặc escalation theo quy trình dự án.

- Vật thể bị cắt bởi rìa ảnh:
    - Nếu phương tiện bị cắt bởi cạnh ảnh nhưng vẫn nhận diện được, vẫn gán nhãn.
    - Box chỉ bao quanh phần phương tiện nằm trong phạm vi ảnh.
    - Không mở rộng tọa độ box vượt ra ngoài kích thước ảnh.
    - Không loại bỏ phương tiện chỉ vì nó không xuất hiện đầy đủ trong ảnh.

- Vật thể rất nhỏ/mơ hồ:
    - Chỉ gán nhãn khi có đủ đặc điểm hình ảnh để xác định phương tiện thuộc một trong bốn lớp.
    - Không suy đoán lớp chỉ dựa trên màu sắc hoặc một vài pixel không rõ ràng.
    - Nếu không thể phân biệt giữa hai lớp, đánh dấu cần review/escalation thay vì tự chọn ngẫu nhiên.
    - Ngưỡng kích thước tối thiểu phải theo quy định của dự án; không tự đặt ngưỡng pixel khi chưa có yêu cầu.

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_015` | Xe con bị cắt một phần trong cạnh dưới ảnh. | Gắn `car` nếu vẫn nhận diện được, box chỉ bao quanh phần nhìn thấy | Vật thể bị truncation nhưng vẫn có đủ đặc điểm để xác định lớp. |
| `drive_016` | Xe con bị bụi cỏ che một phần. | Gắn `car`  | Vật thể vẫn xác định được lớp và có đủ bằng chứng hình ảnh. |
| `drive_017` | Xe tải có hình ảnh mơ hồ. | Gắn `truck` nếu nhận diện được, box chỉ bao quanh phần nhìn thấy. | Phân loại vật thể dựa trên kích thước. |
