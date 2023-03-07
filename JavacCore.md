# JAVA CORE

### String
là lớp chuỗi cơ bản trong Java, đại diện cho một chuỗi các ký tự không thể thay đổi được (immutable).Do tính chất không thể thay đổi của String 
nên nó an toàn để sử dụng trong môi trường đa luồng. Nhưng cũng vì không thay đổi giá trị của nó mà nó thể sẽ làm tốn bộ nhớ thêm khi thao tác với nó,
giá trị ban đầu của nó sẽ không thay đổi mà nó sẽ tạo ra lớp đối tượng mới.

### String Builder
là lớp chuỗi có thể thay đổi được (mutable), được sử dụng khi ta cần thực hiện các thao tác cập nhật trên chuỗi một cách hiệu quả. StringBuilder có tính chất là không đồng bộ hóa nên không thích hợp dùng trong môi trường đa luồng. String Builder chỉ cấp phát một lần vùng nhớ tối thiểu đủ cho chuỗi , xong sử dụng lại vùng nhớ đó nên không bị cấp phát vùng nhớ thừa.

### String Bufffer
tương tự như StringBuilder, là lớp chuỗi có thể thay đổi được (mutable), được sử dụng khi ta cần thực hiện các thao tác cập nhật trên chuỗi một cách hiệu quả. Tuy nhiên, StringBuffer được thiết kế để sử dụng an toàn trong môi trường đa luồng nên 
nó không thích hợp dùng trong môi trường đơn luồng. String Buffer cũng chỉ cấp một lần vùng nhớ tối thiểu đủ cho chuỗi , xong sử dụng lại.
