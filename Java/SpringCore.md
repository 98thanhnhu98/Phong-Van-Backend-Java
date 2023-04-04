# Spring Core
Tóm tắt kiến thức: Các nguyên tắc của Solid, Ioc, DI, ORM, JPA, Hibernate, Bean, BeanLifecycle
### Solid
là một tập hợp các nguyên tắc để thiết kế phần mềm linh hoạt, dễ bảo trì và dễ mở rộng.

### Ioc 
Dựa trên DIP một trong 5 nguyên lí của SOLID .nó giúp triển khai nguyên lý DIP trong SOLID. 
Bằng cách sử dụng IOC container, các class được chia sẻ các interface chung, chứ không phụ thuộc trực tiếp vào nhau.  
Vậy nên nó sinh ra Ioc Container để sử dụng và quản lí bằng cách dùng DI tiêm các bean vào. 

### DI
là một kỹ thuật tiêm sự phụ thuộc vào các Bean.

### So sánh IOC và DI 
theo em hai cái này nó tương tự nhau . Di là một trong nhiều phương thức của IOC

### Spring quản lí bean bằng gì 
Spring quản lí bean bằng Ioc Container.

### ORM 
ORM là một framework hỗ trợ object mapping với các bảng trong database.

### JPA (Java persistence API)
JPA là một đặc các tiêu chuẩn của Java để làm việc với cơ sở dữ liệu quan hệ.

### Hibernate
Là một thư viện ORM giúp các lập trình viên  , nó cho phép tương tác với cơ sở dữ liệu quan hệ .

### Bean 
Nó là những cái module chính của chương trình , được tạo ra và quản lí bởi spring Ioc Container.

### Bean Lifestyle (Vòng đời của Bean)
IOC container tạo bean bằng cách gọi constructor sau đó @PostContructor được gọi đến và qua nhiều phương thức khác cuối khi Bean đó không dùng nữa thì @PreDestroy được gọi đến và hủy Bean.

### Spring Cloud 
là một công nghệ phần mềm sử dụng để phát triển các ứng dụng phân tán.
Một ứng dụng được gọi là phân tán (Distributed application) khi các phần của nó có thể được phát triển trên các ngôn ngữ khác nhau, và được triển khai trên các máy chủ khác nhau.

### Có gì khác biệt giữa class khởi tạo bean và class không khởi tạo bean
_ class không khởi tạo bean thì sẽ phải do dev khởi tạo new ra.
_ class khởi tạo bean thì khi chạy chương trình springboot thì nó sẽ tự động gọi ra các class đó.

### Phân biệt @component, @controller, @service, @repository?
_ @component : sử dụng để định nghĩa 1 khuôn mẫu chung cho toàn bộ dự án , các bean được tạo ra trong class được đánh dấu với  @Component  thường sẽ được dùng chung cho toàn bộ dự án hoặc cho một profile cụ thể . 
Spring chỉ tìm kiếm và chọn ra những class được đánh dâu với  @Component  annotation để khởi tạo và đăng ký với ApplicationContext.
Spring sẽ không tìm kiếm các class được đánh dấu  @Service  và  @Repository . tuy nhiên chúng vẫn sẽ được đăng ký với ApplicationContext bởi 2 anomation chúng đã được đánh dấu với  @Component  annomation .  @Service  và  @Repository  là một trường hợp đặc biệt của  @Component , về mặt kỹ  thuật thì nó tương tự nhau nhưng chúng được sử dụng với mục đích khác nhau.

_ @Service : Dùng để đánh dấu các class thuộc tầng service phục vụ các logic nghiệp vụ .

_ @Repository : Dùng để đánh dấu các class thuộc tầng giao tiếp với database.
Để áp dụng trên class Data Access Object dùng để thao tác với database.

_ @Controller : Đánh dâu class để xử lý request web . Thường được sử dụng để phục vụ các request từ UI .
Mặc định nó trả về một chuỗi cho biết route nào cần redirect . Nó chủ yếu được sử dụng với.
anomation @RequestMapping.

