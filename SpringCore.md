# Spring Core

### Solid
là một tập hợp các nguyên tắc để thiết kế phần mềm linh hoạt, dễ bảo trì và dễ mở rộng.

### Ioc 
Dựa trên DIP một trong 5 nguyên lí của SOLID .nó giúp triển khai nguyên lý DIP trong SOLID. 
Bằng cách sử dụng IOC container, các class được chia sẻ các interface chung, chứ không phụ thuộc trực tiếp vào nhau.  
Vậy nên nó sinh ra Ioc Container để sử dụng và quản lí bằng cách dùng DI tiêm các bean vào. 

### DI
là một kỹ thuật tiêm

### So sánh IOC và DI 
theo em hai cái này nó tương tự nhau . Di là một trong nhiều phương thức của IOC 

### Spring quản lí bean bằng gì 
Spring quản lí bean bằng Ioc Container

### ORM 
ORM là một framework hỗ trợ object mapping với các bảng trong database

### JPA (Java persistence API)
JPA là một đặc các tiêu chuẩn của Java để làm việc với cơ sở dữ liệu quan hệ

### Hibernate
Là một thư viện ORM giúp các lập trình viên  , nó cho phép tương tác với cơ sở dữ liệu quan hệ 

### Bean 
Nó là những cái module chính của chương trình , được tạo ra và quản lí bởi spring Ioc Container
### Bean Lifestyle (Vòng đời của Bean)
IOC container tạo bean bằng cách gọi constructor sau đó @PostContructor được gọi đến và qua nhiều phương thức khác cuối khi Bean đó không dùng nữa thì @PreDestroy được gọi đến và hủy Bean.