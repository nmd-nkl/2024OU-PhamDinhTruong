# Hướng đối tượng OOP
## OOP là gì?

### 1.Khái niệm:
>[!TIP]
>*Lập trình hướng đối tượng là phương pháp lập trình lấy đối tượng làm nền tảng để xây dựng chương trình*

#### Đối tượng: 
Một đối tượng gồm 2 thông tin **`Thuộc tính`** và **`Phương thức`**
* **`Thuộc tính`** là những thông tin, đặc điểm của đối tượng
* **`Phương thức`** là những thao tác, hành động mà đối tượng đó có thể thực hiện

####  Lớp
>[!TIP]
> *Các đối tượng có đặc tính tương tự nhau được gọi là 1 lớp đối tượng*

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
### 1. Tính đóng gói
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

