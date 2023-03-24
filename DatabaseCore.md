# Phỏng vấn DB
Tóm tắt kiến thức : Transaction, Trigger, Các Tập lệnh truy vấn SQL, Đệ Quy SQL, Full Outer Join, Left Join, Right Join, 3 Chuẩn NF

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

### 3 Chuẩn NF
##### 1NF :
 _ Trong 1 bảng : 
  + Các thuộc tính của bảng phải là nguyên tố.
  + Giá trị của các thuộc tính trên các hàng phải là đơn trị, không chứa nhóm lặp , Không có một thuộc tính nào
   có giá trị có thể tính toán được từ một thuộc tính khác .

##### 2 NF:
 _ Loại bỏ các thuộc tính không khóa phụ thuộc vào một bộ phận khóa chính và tách ra thành một bảng riêng, 
 khóa chính của bảng là bộ phận của khóa mà chúng phụ thuộc vào.
 _ Các thuộc tính còn lại lập thành một quan hệ, khóa chính của nó là khóa chính ban đầu.

##### 3NF:
 _ Loại bỏ các thuộc tính phụ thuộc bắc cầu ra khỏi quan hệ và tách chúng thành quan hệ riêng có khóa chính là thuộc tính bắc cầu.
 _ Các thuộc tính còn lại lập thành một quan hệ có khóa chính là khóa ban đầu.


### Full Outer Join
Gom 2 bảng lại thỏa mãn điều kiện và không thỏa mãn điều kiện sẽ là null.

### Cross Join
là tổ hợp record của bảng A với all record của bảng B.

### Left Join
Bảng bên phải nhập vào bảng bên trái.
Record nào bảng bên phải không có thì để null.
Record nào bảng bên trái không có thì không lấy.

### Right Join
Bảng bên trái nhập vào bảng bên phải.
Record nào bảng bên trái không có thì để null.
Record nào bảng bên phải không có thì không lấy.

