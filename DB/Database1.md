# Database 

### Nêu cách làm dữ liệu giả cho 2-3 table để phục vụ demo và có thể thường xuyên cập nhật, reset? 
có thể sử dụng một số công cụ như:
SQL Data Generator: Đây là một công cụ được thiết kế để tạo ra các bản ghi giả trong cơ sở dữ liệu. Công cụ này hỗ trợ nhiều loại dữ liệu khác nhau, 
cho phép tạo ra các bản ghi có tính ngẫu nhiên hoặc tuân theo một mẫu cụ thể.
Faker: Đây là một thư viện mã nguồn mở hỗ trợ tạo dữ liệu giả trong nhiều ngôn ngữ khác nhau.

### Làm thế nào để biết table hiện tại phụ thuộc hay được table/view/sp khác phụ thuộc? Kiểm tra bằng cách nào?
1. SQL Server Management Studio (SSMS): Đây là công cụ quản lý cơ sở dữ liệu cho SQL Server. Bạn có thể sử dụng SSMS để xem các phụ thuộc giữa các bảng,
view, stored procedure trong cơ sở dữ liệu. Bạn có thể mở Object Explorer, tìm đến bảng hoặc view hoặc stored procedure cần kiểm tra,
sau đó chọn Dependencies để xem các phụ thuộc liên quan.

2. Query Analyzer: Đây là một công cụ tương tác với cơ sở dữ liệu trong SQL Server. Bạn có thể sử dụng Query Analyzer để thực hiện các
câu lệnh truy vấn để tìm kiếm các phụ thuộc giữa các bảng, view, stored procedure. Ví dụ, để tìm các bảng phụ thuộc vào bảng Customers,
bạn có thể sử dụng câu lệnh sau:
``
SELECT name
FROM sys.objects
WHERE OBJECTPROPERTYEX(object_id, 'IsTable') = 1
AND OBJECTPROPERTYEX(object_id, 'IsMSShipped') = 0
AND EXISTS (
  SELECT *
  FROM sys.sql_expression_dependencies AS sed
  INNER JOIN sys.objects AS o
  ON sed.referencing_id = o.object_id
  WHERE sed.referenced_id = OBJECT_ID('dbo.Customers')
);
``
Trong đó, sys.objects là một bảng hệ thống trong SQL Server, chứa thông tin về các đối tượng trong cơ sở dữ liệu. 
sys.sql_expression_dependencies là một bảng hệ thống khác, chứa thông tin về các phụ thuộc giữa các đối tượng trong cơ sở dữ liệu.

Third-party tools: Ngoài các công cụ tích hợp trong SQL Server, còn có nhiều công cụ bên thứ ba khác có thể giúp bạn kiểm tra 
các phụ thuộc giữa các đối tượng trong cơ sở dữ liệu. Một số công cụ phổ biến là ApexSQL Clean, Redgate SQL Dependency Tracker, và Quest Toad for SQL Server.

### Bạn có biết cách để tối ưu hóa tốc độ thực hiện tính năng search trong ứng dụng phía database không?
1. Chọn và tối ưu cơ sở dữ liệu: Chọn kiểu cơ sở dữ liệu phù hợp với yêu cầu của ứng dụng, đồng thời thiết kế và tối ưu hóa cơ sở dữ liệu
để giảm thiểu thời gian thực hiện các truy vấn search.

2. Sử dụng index: Index giúp tăng tốc độ thực hiện các truy vấn search bằng cách tạo ra một bản sao của dữ liệu có thứ tự hóa để tìm kiếm nhanh hơn.
Chọn các trường phù hợp và tạo index cho chúng.

3. Sử dụng Full-text search: Full-text search là một tính năng của cơ sở dữ liệu cho phép tìm kiếm văn bản toàn văn nhanh chóng và hiệu quả hơn.
Nếu ứng dụng của bạn yêu cầu tìm kiếm dữ liệu văn bản, nên sử dụng tính năng này.

4. Sử dụng Stored Procedure: Sử dụng Stored Procedure để tối ưu hóa thời gian thực hiện truy vấn. Stored Procedure giúp
tối ưu hóa thời gian thực hiện truy vấn bằng cách giảm thiểu số lần truy cập cơ sở dữ liệu.

5. Sử dụng phân trang: Nếu kết quả tìm kiếm có quá nhiều, bạn nên sử dụng phân trang để tải các kết quả tìm kiếm một cách dần dần, 
giúp tăng tốc độ thực hiện tính năng search.

6. Sử dụng kỹ thuật caching: Sử dụng kỹ thuật caching để lưu trữ các kết quả tìm kiếm phổ biến trong bộ nhớ cache. 
Khi có yêu cầu tìm kiếm tương tự, ứng dụng sẽ trả về kết quả từ bộ nhớ cache thay vì thực hiện lại truy vấn search trong cơ sở dữ liệu,
giúp tăng tốc độ thực hiện tính năng search.

7. Tối ưu hóa code
 
### Nêu định nghĩa và phân biệt Cluster Index và Non-Cluster Index?
Clustered index (chỉ mục gom cụm) và non-clustered index (chỉ mục không gom cụm) là hai loại chỉ mục trong cơ sở dữ liệu quan hệ.

Clustered index được sắp xếp dữ liệu trong bảng theo thứ tự chỉ mục. Nó được sử dụng để tìm kiếm nhanh các giá trị cụ thể hoặc phạm vi giá trị trong bảng.
Mỗi bảng chỉ có thể có một clustered index, và do đó chỉ mục này được sử dụng để sắp xếp toàn bộ bảng.
Ex : priamry key khi được sử dụng cũng tạo ra một clustered index.
Non-clustered index tạo ra một danh sách riêng biệt của các giá trị chỉ mục và con trỏ tới dữ liệu trong bảng. Điều này cho phép truy xuất nhanh các giá trị chỉ mục hoặc phạm vi giá trị cụ thể, nhưng không phải sắp xếp toàn bộ bảng. Một bảng có thể có nhiều non-clustered inde

### Nếu khi rẽ nhánh trong Code mà dùng hết If và không dùng Else thì có gặp phải vấn đề gì không?
Khi rẽ nhánh trong code, nếu sử dụng hết điều kiện if mà không sử dụng else, điều này không gây ra vấn đề gì, và mã có thể hoạt động đúng như mong đợi.

Tuy nhiên, điều này có thể gây ra một số vấn đề về độ đọc hiểu của mã nguồn. Khi có quá nhiều điều kiện if mà không có else,
nó có thể làm cho mã trở nên khó đọc và khó hiểu. Nếu sau đó cần thêm điều kiện else vào để xử lý trường hợp còn lại, sẽ khó khăn hơn để tìm hiểu và hiệu chỉnh mã.

### Bạn hãy nêu ý tưởng để lập trình nhanh, không cần setup database công cụ: input là 1 File CSV chứa Name, Age, Output 1 file CSV, kết quả có cột email được điền vào?
Viết một Action trong Controller để xử lý dữ liệu từ file CSV. Đọc dữ liệu từ file CSV vào một danh sách đối tượng, sau đó xử lý và lưu trữ dữ liệu đó. 
và map tới 1 file khác có thêm thuộc tính Email , rồi trả về view file có đủ 4 thuộc tính trên.

### Thành phần của mẫu web của ASP.NET là gì?
- Model: Đây là thành phần đại diện cho dữ liệu của ứng dụng. Model được sử dụng để truy xuất và lưu trữ dữ liệu của ứng dụng.

- View: Đây là thành phần đại diện cho giao diện người dùng của ứng dụng. View được sử dụng để hiển thị dữ liệu cho người dùng.

- Controller: Đây là thành phần xử lý logic của ứng dụng. Controller nhận đầu vào từ người dùng thông qua các request HTTP và sử dụng Model để truy xuất và lưu trữ dữ liệu. Sau đó, Controller sử dụng View để hiển thị kết quả cho người dùng.

- Routing: Đây là thành phần quản lý các URL của ứng dụng. Routing xác định Controller và Action phù hợp với URL được yêu cầu.

- Middleware: Đây là thành phần quản lý các request và response của ứng dụng. Middleware cho phép thực hiện các thao tác trước và sau khi request được xử lý, như kiểm tra đăng nhập, ghi log, nén dữ liệu, v.v.

- Dependency Injection: Đây là thành phần cho phép tiêm các phụ thuộc vào các thành phần của ứng dụng, giúp quản lý và sử dụng các đối tượng trong ứng dụng một cách dễ dàng và linh hoạt hơn.

