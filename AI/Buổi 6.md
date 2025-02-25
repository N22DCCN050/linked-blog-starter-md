Cây quyết định
- Vấn đề quá vừa dữ liệu (overfitting)
	- Cây t chính xác hơn cây t' trong ptn nhưng t kém chính xác hơn t' trên dữ liệu nói chung.
- Nguyên nhân:
	- Mẫu dữ liệu thường ko đủ, ko đại diện cho phân bố của dữ liệu nói chung.
	- Dữ liệu có nhiễu
	- Cây phức tạp và có nhiều nút..
- Giải pháp hạn chế:
	- Dừng việc dựng cây quyết định sơm
	- Xây dựng cây đầy đủ sau đó tỉa để cây trở nên đơn giản.
	- Tỉa cây - thuật toán ID3:
		- Dừng tập huấn luyện để dựng cây đầy đủ. Sau đó xem xét tỉa dần.
		- Với nút được tỉa:
			- Các nhánh bên dưới sẽ bị bỏ đi.
			- Nút trở thành lá.     
			- Nhãn của nút lá mới lấy theo đa số nhãn của mẫu tại nút đó.
			- Nút sẽ được tỉa nếu accuracy ko giảm sau khi tỉa.
			- Dừng tỉa khi không được tia
**Tính Entropy**

Thuật toán k hàng xóm gần nhất (kNN)
-  Xác định tham số K
- Tính khoảng cách giữa query point với các đối tượng cho training data.
- Sắp xếp khoảng cách theo thứ tự tăng dần và xác định k láng giềng gần nhất với query point.
- Lấy tất cả các lớp của k láng giềng gần nhất.
- Dựa vào phần lớn lớp của láng giềng gần nhất để xác định lớp cho query point.