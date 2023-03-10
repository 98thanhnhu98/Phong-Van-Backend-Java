# JAVA CORE
Tóm tắt kiến thức : String, String builder, String Buffer, Tính chất OOP, Thread, MultiThread, Overriding, OverLoading

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

VD 1 : Overrding

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
 Output : 
 
         Bike is running safely

#### 2 - Tính trừu tượng : Trừu tượng cho phép tập trung vào các thông tin cần thiết và che giấu chi tiết cài đặt. Trong Java, trừu tượng được thực hiện thông qua các lớp trừu tượng (Abstract Class) và các phương thức trừu tượng (Abstract Method).
VD 2 : Abtract class

```
// Abstract class
abstract class Animal {
  // Abstract method (does not have a body)
  public abstract void animalSound();
  // Regular method
  public void sleep() {
    System.out.println("Zzz");
  }
}
// Subclass (inherit from Animal)
class Pig extends Animal {
  public void animalSound() {
    // The body of animalSound() is provided here
    System.out.println("The pig says: wee wee");
  }
}
class Main {
  public static void main(String[] args) {
    Pig myPig = new Pig(); // Create a Pig object
    myPig.animalSound();
    myPig.sleep();
  }
}
```

Output: 

    The pig says: wee wee
    Zzz
   
#### 3- Tính kế thừa : Kế thừa cho phép lớp con (Subclass) được phép sử dụng lại các thuộc tính và phương thức của lớp cha (Superclass). Trong Java, kế thừa được thực hiện thông qua từ khóa "extends".

        Xem lại VD 1

#### 4 - Tính đóng gói : Đóng gói cho phép che giấu thông tin và cài đặt của một đối tượng để không cho các đối tượng khác truy cập trực tiếp. Trong Java, đóng gói được thực hiện thông qua các phương thức Getter và Setter.
File Student.java
VD 3 : Encapsulation
```
public class Student {
    private String name;
 
    public String getName() {
        return name;
    }
 
    public void setName(String name) {
        this.name = name;
    }
}
```
File Test.java
```
class Test {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("Hai");
        System.out.println(s.getName());
    }
}
```
       Hai
       
       
### Thread and multithreading
Thread được coi là đơn vị nhỏ nhất của một chương trình đang chạy vì nó là một tiểu trình độc lập, có khả năng chạy đồng thời với các thread khác trong chương trình. Mỗi thread có một luồng thực thi riêng, có thể chạy cùng lúc với các thread khác, thực hiện các tác vụ độc lập và có thể truy cập và thay đổi các biến và tài nguyên chung.

Trong một chương trình đa luồng, các thread thực hiện các tác vụ đồng thời để tăng tốc độ xử lý và cải thiện hiệu suất của chương trình. Mỗi thread có thể thực hiện một tác vụ riêng biệt hoặc chia sẻ các tài nguyên chung với các thread khác.

Do đó, thread được coi là đơn vị nhỏ nhất của một chương trình đang chạy vì nó là thành phần cơ bản của chương trình đa luồng và là đơn vị thực thi các tác vụ độc lập trong chương trình đó.
VD 4 : Thread 
```
class Simple1 extends Thread {
    public void run() {
        System.out.println("task one");
    }
}
 
class Simple2 extends Thread {
    public void run() {
        System.out.println("task two");
    }
}
 
public class TestMultitasking3 {
    public static void main(String args[]) {
        Simple1 t1 = new Simple1();
        Simple2 t2 = new Simple2();
 
        t1.start();
        t2.start();
    }
}
```
Output :

    task one
    task two

### Overload 
là các phương thức mà các phương đó có tên phương thức trùng nhau nhưng tham số truyền vào là khác nhau

### Override 
là phương thức kế thừa và ghi đè lại thằng cha
