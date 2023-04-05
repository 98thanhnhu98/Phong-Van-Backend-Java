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

### Nếu khi rẽ nhánh trong Code mà dùng hết If và không dùng Else thì có gặp phải vấn đề gì không?
Khi rẽ nhánh trong code, nếu sử dụng hết điều kiện if mà không sử dụng else, điều này không gây ra vấn đề gì, và mã có thể hoạt động đúng như mong đợi.

Tuy nhiên, điều này có thể gây ra một số vấn đề về độ đọc hiểu của mã nguồn. Khi có quá nhiều điều kiện if mà không có else,
nó có thể làm cho mã trở nên khó đọc và khó hiểu. Nếu sau đó cần thêm điều kiện else vào để xử lý trường hợp còn lại, sẽ khó khăn hơn để tìm hiểu và hiệu chỉnh mã.



