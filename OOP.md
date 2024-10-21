# Hướng đối tượng OOP
## OOP là gì?

### 1.Khái niệm:
>[!TIP]
>Lập trình hướng đối tượng là phương pháp lập trình lấy đối tượng làm nền tảng để xây dựng chương trình

#### Đối tượng: 
Một đối tượng gồm 2 thông tin **`Thuộc tính`** và **`Phương thức`**
* **`Thuộc tính`** là những thông tin, đặc điểm của đối tượng
* **`Phương thức`** là những thao tác, hành động mà đối tượng đó có thể thực hiện

####  Lớp
>[!TIP]
> Các đối tượng có đặc tính tương tự nhau được gọi là 1 lớp đối tượng

### 2. Ưu nhược điểm của OOP

|Ưu điểm  |Nhược điểm|
|:--:|:--:|
| Khả năng mô hình hoá các bài toán, đối tượng. |Dữ liệu và xử lý tách rời | 
|Dễ bảo trì, dễ mở rộng và code nhìn gọn hơn |Khi cấu trúc dữ liệu thay đổi sẽ dẫn đến thuật toán bị thay đổi | 
| Người dùng có thể tái sử dụng OOP, tiết kiệm tài nguyên |Không tự động khởi tạo, giải phóng dữ liệu động | 

## Class và Object
### 1. Class
>[!TIP]
>**Một Class trong C# gồm các thành phần:**
> * **Thuộc tính:**  là các thành phần dữ liệu hay còn gọi là các biến
> * **Phương thức:** là các hàm thành phần thể hiện các hành vi của một đối tượng thuộc lớp
> * **Phương thức khởi tạo**
> * **Phương thức huỷ bỏ**

**Cú pháp:**
```cs
class <tên lớp>
{
    <Phạm vi truy cập> <Các thành phần của lớp>;
}
Ví dụ:
class men{
    public double weight; //thuộc tính
    public double height;
    public void study(){ //phương thức
        Console.WriteLine("Đang học bài");
    }
}
```
**Phương thức khởi tạo**
* Được gọi khi tạo đối tượng
* Tên trùng với lớp
*  Nếu không khai báo bất kỳ phương thức nào thì hệ thống sẽ tự tạo phương thức khoie tạo mặc định không có đối số và nội dung gì
*  Có thể có nhiều constructor bên trong 1 lớp
```cs

class men{
    public double weight; 
    public double height;
    //khởi tạo không có tham số
    public men(){
        w =70;
        h=170;
    }
    //Khởi tạo có tham số
    public men(int w,int h){
        weight=w;
        height=h;
    }
    public void in4(){ 
        Console.WriteLine("Chiều cao" + h +"Cân nặng "+ w);
    }
}
```
**Phương thức huỷ bỏ**
* Có tên trùng với tên lớp nhưng để phân biệt với constructor thì ta thêm dấu “~” vào trước tên lớp.
* Không có kiểu trả về
* Nếu không khai báo destructor thì C# sẽ tự động tạo ra 1 destructor mặc định và không có nội dung gì
* Chỉ có 1 destructor duy nhất trong 1 lớp
* Tự động gọi bởi garbage collector khi đối tượng không còn được dùng
### 2. Sự khác nhau giữa Class và Object
|Lớp (Class)  |	Đối tượng (Object)|
|:--:|:--:|
| Là khuôn mẫu mà từ đó đối tượng được tạo ra|Là một thể hiện của lớp | 
|Là tập hợp những đối tượng có thuộc tính giống nhau |Là một thực thể trong thế giới thực | 
| Một lớp chỉ được khai báo một lần|Một đối tượng được khai báo nhiều lần theo yêu cầu| 

## Các tính chất của OOP
### 1. Tính đóng gói < Encapsulation >
>[!TIP]
>##### Phạm vi truy cập
>* **public:** Có thể truy cập bất cứ đâu
>* **private:** Chỉ có thể truy cập bên trong class được khai báo đó
>* **protected:** Chỉ có thể truy cập ở bên trong class và các class kế thừa khác
>* **internal:** Chỉ có thể truy cập trong cùng 1 Assembly (nói cách khác là cùng project). Thường dùng cho class
>* **protected internal:** Tương tự như **internal** ngoài ra có thể truy cập từ lớp dẫn xuất lớp chứa nó

> [!CAUTION]
> * Nếu khai báo lớp mà không chỉ ra phạm vi cụ thể thì phạm vi mặc định là **internal**.
>* Nếu khai báo thành phần bên trong lớp mà không chỉ ra phạm vi cụ thể thì phạm vị mặc định là **private**.

**get và set**
Cú pháp:
```cs
<kiểu dữ liệu> <tên property>{
        get { return <tên thuộc tính>; }

        set { <tên thuộc tính> = value; }
    }

Ví dụ:
    private int diem;
    public int diem{
        getDiem{ return diem;}
        setDiem{ diem=value;}
    }
```
### 2. Tính kế thừa < Inheritance >
>[!TIP]
>Kế thừa là việc thừa hưởng lại những thuộc tính, phương thức từ 1 lớp khác 

**Cú pháp:**
```cs
class <tên lớp con> : <tên lớp cha>{

}
Ví dụ:
Class Animial{
    protected float weight;
    protected float height;
    public void in4(){
        Console.WriteLine(" Weight: "+Weight+" Height: "+Height);
    }
}

class Cat: Animal{
    public Cat(){
        weight=2;
        height=25;
        //lớp Cat kế thừa lớp Animail nên các thuộc tính weight và height lớp Cat có thể sử dụng mà không cần khai báo
    }
}
```
> [!CAUTION]
>* **Constructor** mặc định của lớp cha luôn được gọi mỗi khi có 1 đối tượng thuộc lớp con khởi tạo, và gọi trước phương thức khởi tạo của lớp con
>* Có thể dùng từ khoá **base** để dại diện cho lớp cha và gọi đến các thành phần của lớp cha

### 3. Tính Đa hình < Polymorphism >
>[!TIP]
>* Hiện tượng các đối tượng thuộc các lớp khác nhua có thể hiểu cùng 1 thông điệp theo các cách khác nhau
>* Tính đa hình chủ yếu chia làm hai loại **Compile time** và **Runtime**

**Đa hình biên dịch (compile time:)** được sử dụng bằng cách nạp chồng hàm hoặc nạp chồng toán tử. Cho phép định nghĩa nhiều phương thức có cùng tên những khác tham số (kiểu dữ liệu tham số hoặc số lượng tham số)

```cs
public class inDuLieu {
      public int hamIn(int i) {
            return i;
      }

      public double hamIn(double f) {
            return f;
      }
}

class Program
{
    static void Main()
    {
        inDuLieu In = new inDuLieu();
        Console.WriteLine(In.hamIn (1235));       
        Console.WriteLine(In.hamIn (3,14));    
    }
}
```
**Đa hình thời gian chạy (Method Overriding):** Khi một lớp con định nghĩa lại phương thức đã được định nghĩa trong lớp cha.
```cs
public class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("Animal speaks");
    }
}

public class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

class Program
{
    static void Main()
    {
        Animal myDog = new Dog();
        myDog.Speak();  // Output: Dog barks
    }
}
```
### 4. Tính Trừ tượng < Abstraction >
>[!TIP]
>* Tính trừu tượng cho phép tổng quát hóa một đối tượng. Nghĩa là ẩn đi những thông tin chi tiết bên trong, chỉ thể hiện ra những thông tin bên ngoài. Và nhìn vào thông tin bên ngoài đó ta có thể hiểu được đối tượng đó làm gì.
>* Tính chất này được thể hiện qua việc sử dụng **interface** hoặc **abstract class**
```cs
abstract class Animal
    {
        /*
            Khai báo phương thức thuần ảo nên không cần định nghĩa nội dung cho phương thức
         */
        public abstract void Speak();

    }
```
>[!TIP]
>* **Interface** định nghĩa một tập hợp các phương thức mà lớp thực thi phải triển khai. Interface không thể chứa các thuộc tính, phương thức, hoặc constructor mà không có thân phương thức (body).
>* **Interfaces** giúp đạt được tính đa hình và tách biệt giữa các phương thức đã định nghĩa và cách chúng được triển khai, cho phép xây dựng các hệ thống linh hoạt hơn.
```cs
public interface IAnimal
{
    void Speak();
}

public class Cat : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("Cat meows");
    }
}

public class Dog : IAnimal
{
    public void Speak()
    {
        Console.WriteLine("Dog barks");
    }
}

class Program
{
    static void Main()
    {
        IAnimal myCat = new Cat();
        IAnimal myDog = new Dog();

        myCat.Speak();  // Output: Cat meows
        myDog.Speak();  // Output: Dog barks
    }
}
```
**Nạp chồng (Overload)** cho phép bạn định nghĩa nhiều phương thức hoặc toán tử với cùng tên nhưng khác nhau về số lượng hoặc kiểu tham số. Điều này giúp cải thiện khả năng đọc và sử dụng mã.

***Nạp chồng phương thức:*** Được thực hiện khi có cùng tên nhưng khác số lượng hoặc kiểu tham số.

```cs
public class Display
{
    public void Show(int number)
    {
        Console.WriteLine("Number: " + number);
    }

    public void Show(string text)
    {
        Console.WriteLine("Text: " + text);
    }
}

class Program
{
    static void Main()
    {
        Display display = new Display();
        display.Show(5);          // Output: Number: 5
        display.Show("Hello");    // Output: Text: Hello
    }
}
```
***Nạp chồng toán tử:*** Trong C#, bạn cũng có thể nạp chồng các toán tử, cho phép bạn định nghĩa cách các toán tử hoạt động với các kiểu dữ liệu tùy chỉnh.
```cs
public class Point
{
    public int X { get; set; }
    public int Y { get; set; }

    public static Point operator +(Point p1, Point p2)
    {
        return new Point { X = p1.X + p2.X, Y = p1.Y + p2.Y };
    }
}

class Program
{
    static void Main()
    {
        Point p1 = new Point { X = 5, Y = 10 };
        Point p2 = new Point { X = 3, Y = 7 };
        Point result = p1 + p2;

        Console.WriteLine($"Result: X = {result.X}, Y = {result.Y}");  // Output: Result: X = 8, Y = 17
    }
}
```