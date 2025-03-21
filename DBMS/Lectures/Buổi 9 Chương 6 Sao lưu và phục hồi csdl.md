Login ko thể sao lưu bằng backup thông thường vì nằm trong sys.user
- Cách khác: lưu lại script

Backup qua device
Backup trực tiếp trên file
Đổi tên file để tránh bị windows scan

Giao tác tự động khi chỉ có 1 lệnh (create/delete/update)

Recovery: 3 đk:

- Mode recovery: phải là Full
- ?
- ?

CREATE PROCEDURE Getbackup @QLVT_AT NVARCHAR(255)
AS
BEGIN
	SET NOCOUNT ON;
	SELECT
		 backup_start_date AS [Backup Datetime],
		 ROW_NUMBER() OVER (ORDER BY backup_start_date DESC) AS [Backup Order],
		 user_name AS [Backup_User]
    FROM msdb.dbo.backupset
    WHERE database_name = @QLVT_AT
    ORDER BY backup_start_date DESC;
END;