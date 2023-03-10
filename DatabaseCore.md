# Phỏng vấn DB
Tóm tắt kiến thức : Transaction, Trigger, Các Tập lệnh truy vấn SQL, Đệ Quy SQL

### Transaction


### Trigger
là những thủ tục thực thi.
trigger sẽ được gọi mỗi khi có thao tác thay đổi thông tin bảng.
kiểm tra dữ liệu xem có đảm bảo không , nếu không thì rollback lại.
Trong Trigger có :
+ Inserted : chứa những trường đã insert | update bảng.
+ Delete chứa những trường bị xóa khỏi bảng.

Kiểu như là nó quản lí sự thay đổi dữ liệu insert | update | delete dữ liệu ,
khi khởi tạo trigger nó sẽ check theo điều kiện mình đặt ra bên trong , nếu không đảm bảo
thì mình sẽ rollback transaction - tức là hủy bó phương thức đó và coi như chưa có gì thay đổi trong bảng.
Lưu ý :
+ Vì sự quản lí của nó mà câu truy vấn có thể sẽ bị lâu hơn bình thường vì nó phải đi qua thằng trigger này.

### Trong SQL, DDL, DML, DCL và TCL 
là các tập lệnh để tương tác với cơ sở dữ liệu. Cụ thể:

##### DDL (Data Definition Language)
là ngôn ngữ định nghĩa dữ liệu, được sử dụng để tạo và quản lý các đối tượng cơ sở dữ liệu như bảng, chỉ mục, chế độ xem, khóa, thủ tục lưu trữ và hàm. Một số lệnh DDL phổ biến trong SQL bao gồm CREATE, ALTER và DROP.

##### DML (Data Manipulation Language) 
là ngôn ngữ thao tác dữ liệu, được sử dụng để truy vấn, thêm, sửa đổi hoặc xóa dữ liệu trong các bảng hoặc các đối tượng khác trong cơ sở dữ liệu. Một số lệnh DML phổ biến trong SQL bao gồm SELECT, INSERT, UPDATE và DELETE.

##### DCL (Data Control Language) 
là ngôn ngữ kiểm soát dữ liệu, được sử dụng để quản lý quyền truy cập và đảm bảo tính toàn vẹn dữ liệu. Một số lệnh DCL phổ biến trong SQL bao gồm GRANT và REVOKE.

##### TCL (Transaction Control Language) 
là ngôn ngữ kiểm soát giao dịch, được sử dụng để quản lý các giao dịch trong cơ sở dữ liệu. Một số lệnh TCL phổ biến trong SQL bao gồm COMMIT và ROLLBACK.

### Đệ quy Database và truy vấn phân cấp
Wiki SQL: https://en.wikipedia.org/wiki/Hierarchical_and_recursive_queries_in_SQL#Common_table_expression

Link tham khảo : https://viblo.asia/p/nghich-ngom-voi-bai-toan-multi-level-query-63vKjbNbK2R

