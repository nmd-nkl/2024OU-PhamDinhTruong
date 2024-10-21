# Git & Github Terminal
## Git
#### Commands
**`git init:`** chuyển dự án thành một git repo

**`git status:`**  cho thấy trạng thái thay đổi

**`git config --global user.name/user.gmail:`** set lại user và email

**`git add:+ tên dự án`** chuẩn bị lưu lại thời điểm của dự án
`git add .` lưu lại các file

**`git reset`** set lại file vừa lưu

**`git commit: -m 'message'`** : lưu lại dự án

**`git log:`** xem lại lịch sử
**`git log--oneline:`** gọn hơn so với git log

**`git checkout + id:`** trở lại commit nào đó

#### Branch
**`git branch:`** kiểm tra branch

**`git checkout -b {tên branch}:`** truy cập branch khác

**`git merge {tên branch}:`** tổng hợp lại branch

**`git branch -d {tên branch}:`** xoá 1 branch

## Github
**`git push: {đường link}{branch}`** đẩy lên repo

**`git clone {đường link}:`** lấy một remote về local






## Readme file
#### Các cách thường dùng
`#:` để tạo thành các heading (tối đa 6#)

`** **:` dùng để bôi đậm         `* *:` dùng để in nghiêng   

`*** ***:` cả in đậm và nghiêng`\:` để giữ lại các ký tự 
đặc biệt

`~~ ~~`   ~gạch bỏ~

>**Quotation** `>`  

` `` ` dùng để nhấn mạnh chữ trong câu

#### Tạo bảng
/|stt|cột 1|cột 2|           
|---|-----|-----|                  
`Ví dụ `  
![Alt text](image-1.png)
#### List
`+` `-` `*`
+ 1
- 2
* 3
  * 3.a


#### Code block
```c
void main
printf("```c```"); 
 ```

    có thể tạo code block bằng tab

`---/ ***` gạch ngang

#### Chèn link 
Có thể chèn link bằng dấu ngoạch vuông hoặc tròn: 
`[tên link](link)`[đây là link](https://github.com/pdihtrg)

có thể fomat cho link **<https://github.com/pdihtrg>**

***Hoặc viết chuyên nghiệp hơn***
`[1]: <https://github.com/pdihtrg>`
Đây là [github][1] của tôi 
chú ý cách ít nhất 1 dòng trống

[1]:<https://github.com/pdihtrg>
#### Vẽ biểu đồ:
Dùng mermaid: [mermaid](https:/mermaid-js.github.io/mermaid/#/)
Hoặc PlanUML

#### Math
Để viết công thức toán cần đặt giữa hai dấu `$ $` $\alpha$ or  $x^2$
