# Các câu hỏi phỏng vấn
### 1 Em hãy mô tả bản thân, quá trình làm việc, kinh nghiệm của các dự án mà em đã từng trải qua :
Tôi là một backend developer với gần 2 năm kinh nghiệm làm việc phát triển các hệ thống dựa trên kiến trúc phân tán và viết mã các API RESTful trong backend và chủ yếu làm việc với framework Java core và Spring boot .cùng với kinh nghiệm trong sử dụng các công nghệ khác như MySQL , Redis, RabbitMQ và gitlab.
### 2 Dự án nào mà em tâm đắc nhất :
Dự án mà em cảm thấy tâm đắc đó là dự án đăng bán thông tin cho thuê nhà
theo em nhớ thì dự án này có các features chính :
+ Quản Lí Admin
+ Quản lí các gói dịch vụ về đăng bán thông tin
+ Thống kê Người dùng (thống kê theo gói dịch vụ ,theo tình trạng hợp đồng người dùng , tình trạng hết hạn ,gia hạn gói )
+ Ở phần người dùng thì quản lí hợp đồng của mình ( có thể đổi gói dịch vụ , tình trạng thanh toán gói dịch vụ ) ,quản lí các sản phẩm mình đã đăng tải

Note : nói chung là admin quản lí các dịch vụ như là 1 tháng - 20 tin, 3 tháng 50 tin và 12 tháng - 100 tin đăng bán các sản phẩm, quản lí các gói hợp đồng đang còn thời hạn , hợp đồng sắp hết thời hạn và hợp động hết thời hạn ,muốn gia hạn thêm hoặc muốn đổi gói dịch vụ khác 
Phía User thì quản lí các sản phẩm mình có thể update lại thông tin sản phẩm , muốn đổi gói dịch vụ hoặc gia hạn gói dịch vụ .

### 3 Trong dự án, có những cách nào để tối ưu hóa hiệu năng trong lập trình
Có nhiều cách để tối ưu hóa hiệu năng như là tối ưu hóa ở code , tối ưu hóa ở database hoặc là nâng cấp con server :
+ Tối ưu hóa ở code thường thì em sẽ tracing để xem nó đang bị lỗi gì và lỗi ở đâu
+ Tối ưu hóa ở server , thường thì ở phần này mình sẽ chia tải ra còn nếu không còn biện pháp gì nữa thì bắt buộc phải nâng cấp con Server .

### 3.1 khi mà có quá nhiều request thì em giải quyết như nào (hệ thống bị treo, quá tải request)
+ thường thì khi có quá nhiều request thì lúc đó thì bọn em sẽ dùng TPS COUNTER , tức là khi một cái transaction chạy thì nó sẽ check xem có vượt quá limit không, nếu không thì nó sẽ tăng lên một và khi thực hiện xong nó sẽ trừ đi một còn khi lớn hơn limit thì bọn em sẽ throw ra exception và trả lại message cho khách hàng là quá tải hệ thống.

(nếu mà thấy thái độ của ông phỏng vấn tốt thì nên hỏi )
### 4 Em có câu hỏi gì cho anh không?
+ Dự án dùng công nghệ gì ? -> em rất thích công nghệ này , em rất hứng thú về công nghệ này 
