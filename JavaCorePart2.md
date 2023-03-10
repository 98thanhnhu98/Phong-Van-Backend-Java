# JAVA CORE

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
VD 3 : Khi khởi tạo biến non-static và muốn gọi trong một method static thì bắt buộc phải khai báo biến đó là static hoặc bở static ở method đi
```
public class A {
    static int D;

    static void Ba(){
        System.out.println(D);
    }
}

```
