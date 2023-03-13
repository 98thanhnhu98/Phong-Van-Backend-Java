# JAVA CORE
Tóm Tắt Kiến thức : Bộ nhớ Stack và Heap, kiểu nguyên thủy , kiểu giá trị thường , static , final , Collections

### Bộ nhớ STACK
là một cùng nhớ được sử dụng để lưu trữ các tham số và các biến local của phương thức mỗi khi một phương thức được gọi ra . Các tham số và các biến local của một phương thức tạo thành một bản ghi kích hoạt , còn được là một stack frame. Các bản ghi kích hoạt được đẩy vào một stack khi phương thức được gọi và đẩy ra khỏi stack khi phương thức trả về . Sự tồn tại tạm thời của các biến này quyết định thời gian sống của các biến.

### Bộ nhớ Heap
là một vùng nhớ trong bộ nhớ được sử dụng để lưu trữ các đối tượng khi từ khóa new được gọi ra , các biến static và các biến toàn cục ( biến instance ).

### Kiểu Nguyên Thủy (Wrapper Class)
Là một kiểu Object chứa các phương thức xử lý giá trị đó. Nó còn được sử dụng để truyền giá trị vào các phương thức yêu cầu đối tượng.

### Kiểu Giá Trị (Primitive Data Type)
là một kiểu dữ liệu cơ bản không có phương thứ xử lý giá trị , dùng để lưu dữ liệu và được lưu trực tiếp trong bộ nhớ.

### làm việc với Static và Non-Static
VD 1 : Khi mà muốn gọi 1 static class trong 1 public class 
```
public class A {
    static class B{
        void Ba(){
            System.out.println("HELlO WORLD");
            }
        }
}
class C {
    public static void main(String[] args) {
        A.B b = new A.B();
        b.Ba();
    }
}
```
khi mà T muốn gọi thằng inner static class B thì như method main() ở class C ta phải Khai báo ra thằng A rồi . thằng B với cả khi gọi 
ra ta bắt buộc phải khai báo cho nó tạo mới new không thể gắn null cho class đó;

VD 2 : Khi khởi tạo biến static và muốn gọi trong một method non-static
```
public class A {
    static int D;

    void Ba(){
        System.out.println(D);
    }
}
```
VD 3 : Khi khởi tạo biến non-static và muốn gọi trong một method static thì bắt buộc phải khai báo biến đó là static hoặc bỏ static ở method đi
```
public class A {
    static int D;

    static void Ba(){
        System.out.println(D);
    }
}

```

### làm việc với Final
+ Khi khai báo public final class A thì class A sẽ không thể kế thừa được
+ Khi khai final properties a thì thuộc tính a này bắt buộc phải được khai báo và sẽ không thể sửa đổi.

### Collections
#### - List
+ ArrayList : 
  - là một danh sách mảng động.
  - Thứ tự các phần tử dựa theo thứ tự thêm vào và có thể giống nhau.
  - Lưu dữ liệu theo chỉ mục => cho phép truy cập ngẫu nhiên => tốc độ truy xuất nhanh.
  - Thao tác thêm/sửa/xóa chậm vì cần dịch chuyển các phần tử khi thêm/xóa khỏi danh sách.
  - Yêu cầu ít bộ nhớ hơn so với linkedlist.

+ LinkedList : 
  - Được sắp xếp có thứ tự và có thể giống nhau.
  - Thao tác thêm/sửa/xóa nhanh vì không cần phải dịch chuyển nếu bất kì phần tử nào bị xóa khỏi danh sách.
  - Truy xuất các phần tử chậm vì nó phải duyệt qua tất cả các phần tử từ đầu đến cuối để tìm phần tử.
  - Lưu trữ nhiều hơn so với arraylist.
  
+ Vector :
  - 

#### - Queue
Là một danh sách hàng đợi .
+ PriorityQueue : 
  - Là một hàng đợi ưu tiên được xắp xếp


+ linkedList :
  - 

+ ArrayQueue : 
  -

#### - Dequeue
+ LinkedList :
  - 

+ ArrayQueue :
  -

#### - Set
+ HashSet :
  - Không dựa theo thứ tự lúc thêm vào và giá trị các phần tử là duy nhất
  - Dung lượng lưu trữ mặc định là 16
  - Cho phép chứa phần tử null
  - Hệ số tải mặc đinh (0,75) Khi nào hashset được lấp đầy 75% các phần tử sẽ được chuyển sang hashtable , các phẩn tử chuyển sang hashtable mới có kích thước gấp đôi hash table ban đầu)
