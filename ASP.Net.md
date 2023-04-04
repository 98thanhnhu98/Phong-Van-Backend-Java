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

### 
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
