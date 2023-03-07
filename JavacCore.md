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

### OOP (Object Oriented Programming) là một phương pháp lập trình hướng đối tượng , cho phép dev tập trung vào object để phát triển các ứng dụng và nó được thể qua 4 tính chất :

#### 1 - Tính đa hình : Đa hình cho phép một đối tượng có thể biểu diễn nhiều hình dạng khác nhau. Trong Java, đa hình được thực hiện thông qua hai cơ chế là kế thừa (Inheritance) và ghi đè phương thức (Method Overriding).

VD : Overrding

 ```
 class Vehicle{  
  //defining a method  
  void run(){System.out.println("Vehicle is running");}  
}  
//Creating a child class  
class Bike2 extends Vehicle{  
  //defining the same method as in the parent class  
  void run(){System.out.println("Bike is running safely");}  
  
  public static void main(String args[]){  
  Bike2 obj = new Bike2();//creating object  
  obj.run();//calling method  
  }  
}  
 ```

#### 2 - Tính trừu tượng : Trừu tượng cho phép tập trung vào các thông tin cần thiết và che giấu chi tiết cài đặt. Trong Java, trừu tượng được thực hiện thông qua các lớp trừu tượng (Abstract Class) và các phương thức trừu tượng (Abstract Method).

#### 3- Tính kế thừa : Kế thừa cho phép lớp con (Subclass) được phép sử dụng lại các thuộc tính và phương thức của lớp cha (Superclass). Trong Java, kế thừa được thực hiện thông qua từ khóa "extends".

#### 4 - Tính đóng gói : Đóng gói cho phép che giấu thông tin và cài đặt của một đối tượng để không cho các đối tượng khác truy cập trực tiếp. Trong Java, đóng gói được thực hiện thông qua các phương thức Getter và Setter.
