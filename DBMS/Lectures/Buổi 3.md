SQL SERVER Services 
- Database engine 
- Analysis Services 
- Reporting services

Multiple Servers 
- One default instance: same name as PC 
- Many named servers: computer_name\instance_name 
 
Server Variable: @@SERVERNAME 
- SELECT @@SERVERNAME

TRANSACTION (T-SQL): update, delete, …

Kiến trúc CSDL trong SQL SERVER 
- Server 
- Cơ sở dữ liệu: 2 loại 
	- System db: sysdatabases 
		- Master, model, msdb, tempdb 
		- SELECT * FROM SYS.sysdatabasessl 
	- User db

Table tạm: cục bộ (#), toàn cục (##) 
- SELECT 
- INTO 
- FROM 
Điểm chung: đều biến mất khi ngắt kết nối 
 
Tối ưu truy vấn: Chọn trước, chiếu trước, kết sau, tạo chỉ mục 
- Tạo thứ tự đối với dữ liệu trong WHERE 
- Thay ORDER BY bằng INDEX 
