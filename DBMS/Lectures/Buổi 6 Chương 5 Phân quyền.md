Chưa tạo tài khoản => bấm nút xoá thì ko phản hồi
Đã có tài khoản:
- Ko tạo đc tk mới bằng tên của mình
- Nếu là tài khoản của mình thì ko xoá đc

Role trên server
- dbcreator: phục hồi csdl
- securityadmin: tạo tk server của ng khác
- sysadmin: all quyền

Role trên csdl:
- db_accessadmin
- db_securityadmin
- db_backupadmin

=> Muốn có quyền tạo tk cho ng khác cần có 3 quyền
- securityadmin
- db_accessadmin
- db_securityadmin
=> Muốn có quyền backup and restore
- dbcreator
- db_backupadmin

TH 1 tk có 2 quyền xung đột thì dbms chọn quyền cấm.


SELECT *SID*, NAME FROM SYS.syslogins (trong server)
SELECT UID, NAME, *SID*, issqlrole FROM SYS.sysusers (trong db => user trong db liên kết với logins qua SID)
SELECT * FROM SYS.sysmember


EX4:
	CREATE PROCEDURE getUserGroup
		@username VARCHAR(20)
	AS 
	BEGIN
		DECLARE @uid INT
		SELECT @uid=uid
		FROM sys.sysusers WHERE name=@username
	
		SELECT UID AS MA_NHOM, NAME AS TENNHOM
		FROM SYS.sysusers
		INNER JOIN SELECT (groupuid FROM SYS.sysusers WHERE memberuid=@uid) TMP ON SYS.sysusers.uid=TMP.groupuid
	END
EX5:
	CREATE PROCEDURE getUsersInGroup
	    @rolename VARCHAR(20) 
	AS
	BEGIN
	    DECLARE @roleid INT; 
	    SELECT @roleid = uid
	    FROM sys.sysusers WHERE name = @rolename;
	    
	    //IF @group_uid IS NULL
	    //BEGIN
	    //    PRINT 'Không tìm thấy nhóm';
	    //    RETURN;
	    //END
	    
	    SELECT NAME AS TEN_USER
	    FROM SYS.sysusers
	    INNER JOIN (SELECT memberuid FROM SYS.sysmember WHERE groupuid = @roleid) TMP ON SYS.sysusers.uid=TMP.groupuid
	END

BT 567

dropuser + droplogin