Tính chất: ACID (atomicity, consistency, isolation, durability)
- Tính nguyên tử: 1 tập lệnh coi như một lệnh
- Tính nhất quán: 
	- Ràng buộc toàn vẹn phải nguyên vẹn sau giao tác
	- Các mẩu tin hoặc phải được xử lý hết (nếu tất cả đều thoả điều kiện giao tác), hoặc không được xử lý mẩu tin nào (nếu có ít nhất một trong các mẩu tin ko thoả).
- Tính biệt lập: 
	- Dữ liệu 1 ng dùng đang xử lý thì nó phải được biệt lập khỏi ng dùng khác (tương tự biến cục bộ) => dữ liệu rác.
	- Dữ liệu của mình ko đc biệt lập => ng khác có thể thêm dữ liệu => phantom row.
	- 5 mức biệt lập
		- Read uncommitted:
		- Read committed
		- Repeatable read
		- Serializable: triệt tiêu đc cả dữ liệu rác và phantom row
		- Snapshot
- Tính bền vững: đã commit thì ko rollback
Phân loại
Các mức biệt lập