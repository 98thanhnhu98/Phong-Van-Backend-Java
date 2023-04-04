# Phong-Van-ASP.NET mvc
### Bạn hãy nêu các trường hợp dùng công cụ Inspector trong trình duyệt?
1 Kiểm tra Css
2 Kiểm tra Js
3 Kiểm tra lỗi
4 Kiểm tra phần tử cụ thể

### Phân biệt HTTP GET vs HTTP POST?
Get - là dùng vào những trường hợp lấy phần tử, có thể gửi dữ liệu trên uri nhưng sẽ không an toàn, get sẽ load nhanh hơn 
Post - là dùng vào những trường hợp gửi phần tử , có thể dùng để lấy phần tử , gửi dữ liệu trên header nên sẽ được bảo mật hơn


### Nêu cách xây dựng chức năng load data từ SQL Server lên Html table dưới View trong ASP.NET MVC?
Để hiển thị dữ liệu từ SQL Server lên HTML table dưới View trong ASP.NET MVC, mình có thể sử dụng Entity Framework để truy vấn 
dữ liệu từ database và sau đó truyền dữ liệu đó cho View thông qua một model.

### Xây dựng chức năng tải ảnh lên ASP.NET MVC như thế nào?
Tạo một View để hiển thị form upload ảnh cho người dùng. Trong View này, bạn có thể sử dụng thẻ <form> để tạo một form upload, 
và sử dụng thẻ <input type="file"> để cho người dùng chọn ảnh cần tải lên.

Trong Controller, xử lý yêu cầu tải ảnh lên. Bạn có thể sử dụng đối tượng HttpPostedFileBase để lấy thông tin về ảnh đã được tải lên từ form upload
  ```
  [HttpPost]
public ActionResult Upload(HttpPostedFileBase imageFile)
{
    if (imageFile != null && imageFile.ContentLength > 0)
    {
        // Lấy thông tin về ảnh
        var fileName = Path.GetFileName(imageFile.FileName);
        var contentType = imageFile.ContentType;

        // Lưu ảnh vào thư mục tạm
        var path = Path.Combine(Server.MapPath("~/App_Data"), fileName);
        imageFile.SaveAs(path);

        // Trả về kết quả tải ảnh thành công
        return Content("Upload successful!");
    }

    // Trả về kết quả tải ảnh thất bại
    return Content("Upload failed!");
}
  ```
  
Trong phương thức Upload, chúng ta kiểm tra xem người dùng đã chọn ảnh để tải lên hay chưa, nếu có thì lấy thông tin về ảnh đó và lưu vào thư mục tạm trên server. Sau đó, trả về thông báo cho người dùng biết kết quả của quá trình tải ảnh.

Lưu ý rằng, để có thể sử dụng đối tượng HttpPostedFileBase, bạn cần phải đặt thuộc tính enctype="multipart/form-data" cho thẻ <form> trong View, để cho phép tải lên các dữ liệu có kiểu MIME như hình ảnh, âm thanh, video, v.v.

### Bạn sẽ xử lý như thế nào nếu gặp lỗi Circular references?
Circular references là một lỗi xảy ra khi hai hoặc nhiều đối tượng trong ứng dụng tham chiếu đến nhau một cách vòng tròn. Khi gặp lỗi này, việc xử lý có thể rất phức tạp và khó khăn, tùy thuộc vào cấu trúc của ứng dụng.
  
1. Sử dụng một thư viện chuyên dụng để giải quyết vấn đề này, ví dụ như JSON.NET của Newtonsoft. Thư viện này cung cấp một số cách để giải quyết vấn đề Circular references, như sử dụng các thuộc tính ReferenceLoopHandling hoặc PreserveReferencesHandling.

2. Tắt tính năng Serialization cho các đối tượng gây ra vấn đề Circular references. Việc này có thể được thực hiện thông qua cấu hình trong ứng dụng.

3. Sử dụng các kỹ thuật khác nhau để phân tách các đối tượng tham chiếu nhau, ví dụ như tách thành các đối tượng con hoặc tạo một đối tượng trung gian để lưu trữ các tham chiếu. Tuy nhiên, cách tiếp cận này có thể làm tăng độ phức tạp và khó bảo trì của ứng dụng.

### - Phân biệt IQueryable và IEnumerable? Nêu vấn đề Client Evaluation trong Entity Framework?
Khi sử dụng IEnumerable, câu lệnh truy vấn sẽ thực hiện trên máy chủ và trả về dữ liệu cho client. Sau khi trả hết dữ liệu, client mới thực hiện lấy  bản ghi theo điều kiện.
Khi sử dụng IQueryable, câu lệnh truy vấn sẽ thực hiện trên máy chủ, lọc trên máy chủ và trả dữ liệu cho client.
  
### Nêu giải pháp xử lý long running process? (Gửi email hàng loạt, Tổng hợp các số liệu, …)
1.Sử dụng hàng đợi (queue): Đưa các quá trình xử lý dài hạn vào một hàng đợi để xử lý theo thời gian thực sự cần thiết. Hàng đợi này có thể được triển khai thông qua các công nghệ như RabbitMQ, ActiveMQ, hoặc Azure Queue.

2.Tách quá trình thành nhiều phần nhỏ: Chia quá trình lâu dài thành nhiều phần nhỏ hơn để xử lý dễ dàng hơn, giúp tránh được tắc nghẽn và tránh gây tốn tài nguyên hệ thống.

3.Sử dụng công nghệ tách biệt quy trình (process isolation): Sử dụng công nghệ tách biệt quy trình để đảm bảo rằng quá trình lâu dài không ảnh hưởng đến các hoạt động khác của hệ thống.

4.Sử dụng các dịch vụ bên ngoài (third-party services): Sử dụng các dịch vụ bên ngoài để xử lý các quá trình lâu dài như gửi email hàng loạt hoặc tổng hợp số liệu. Như vậy, các dịch vụ này sẽ đảm nhận việc xử lý và giải phóng tài nguyên hệ thống của bạn.

5.Sử dụng kỹ thuật cache: Sử dụng kỹ thuật cache để lưu các kết quả của quá trình xử lý dài hạn, giảm thiểu việc phải thực hiện lại các phép tính, giảm thiểu thời gian phản hồi và tăng hiệu suất xử lý.

6.Xây dựng các tiến trình dự phòng (failover processes): Xây dựng các tiến trình dự phòng để đảm bảo rằng quá trình xử lý không bị gián đoạn hoặc bị tắt do các lỗi hệ thống.
  
### ASP.NET core
ASP.NET Core is the framework you want to use for web development with .NET
  
### ASP.NET mvc
  
# Server
  
### HTTP/HTTPS
HTTP là một giao diện ứng dụng giao thức truyền thông , là một thể hiện của sự giao tiếp giữa client và server.
HTTPS là một phiên bản bảo mật của HTTP , nó sử dụng mã hóa SSL/TLS
  
  
  
  
  
  
  
  
  
  
  
