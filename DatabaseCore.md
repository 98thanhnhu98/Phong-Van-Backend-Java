# Phỏng vấn DB

### Transaction

### 

### Trigger
là những thủ tục thực thi 
trigger sẽ được gọi mỗi khi có thao tác thay đổi thông tin bảng
kiểm tra dữ liệu xem có đảm bảo không , nếu không thì rollback lại
Trong Trigger có :
+ Inserted : chứa những trường đã insert | update bảng
+ Update chứa những trường bị xóa khỏi bảng.

Kiểu như là nó quản lí sự thay đổi dữ liệu insert | update | delete dữ liệu ,
khi khởi tạo trigger nó sẽ check theo điều kiện mình đặt ra bên trong , nếu không đảm bảo
thì mình sẽ rollback transaction - tức là hủy bó phương thức đó và coi như chưa có gì thay đổi trong bảng

Vì sự quản lí của nó mà câu truy vấn có thể sẽ bị lâu hơn bình thường vì nó phải đi qua thằng trigger náy
### DDL

### DML 
