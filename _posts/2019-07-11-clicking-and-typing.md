---
layout: post
title: "Clicking & Typing"
categories: [Linux]
tags: [file system, command line]
comments: true
---

### Loanh quanh câu chuyện sử dụng hệ điều hành nhân Linux 

Sau một thời gian dài sử dụng hệ điều hành nhân Linux, cũng gọi là có chút ít thành thạo trong quá trình dần thay thế hệ điều hành Windows cũng như các phần mềm có bản quyền chuyển sang sử dụng các phần mềm mã nguồn mở trên các hệ điều hành nhân Linux đi kèm. Nhiều người cho rằng các hệ điều hành nhân Linux sử dụng khá khó khăn kể cả đối với những lập trình viên khi mới bắt đầu tiếp xúc với nó. Thật sự điều đó có thể đúng đối với một số bản phân phối khác nhau của HĐH nhân Linux cũng như các phiên bản trước đây quá lâu rồi. Còn hiện tại các bản phân phối như Debian, Fedora, ... hay các nhánh con của nó cũng khá dễ dàng cài đặt và sử dụng.

<!--more-->

Một thế mạnh của hệ điều hành nhân Linux đó là công cụ **Terminal**, nơi mà chúng ta có thể quản lý thao tác với máy tính thông qua giao diện dòng lệnh một cách nhanh chóng và hiệu quả và các thao tác đó ta có thể đem ra so sánh với các thao tác **Clicking** mà chúng ta vẫn thường làm mà chưa thực sự quan tâm đến sự tương đồng đó với **Typing**.

Ok bây giờ ta sẽ đi tìm hiểu xem việc thao tác với máy tính thông qua Terminal của HĐH nhân Linux  để nói rõ xem chủ đề ngày hôm nay _**Clicking & Typing**_ nó là gì???

### Chắc hẳn bất kể người sử dụng máy tính nào đều rất quen thuộc với các thao tác: xem, tìm kiếm, tạo file, rename, move,...

#### Mở thư mục xem tệp tin

> **Clicking:** Một cách đơn giản chỉ cần double-click vào thư mục
> và sau đó folder window (cửa sổ làm việc) của thư mục sẽ hiện ra.
> Và chúng ta có thể nhìn thấy các thư mục con cũng như các tệp tin trong thư mục vừa mở đó.

![Open Folder](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/openfolder.png)

> **Typing:** Để mở thư mục trên Terminal cách đơn giản đó là sử dụng command line **cd**, xem danh sách tệp tin: **ls**.

```console
$ pwd
/home/qndev
$ cd Pictures
$ pwd
/home/qndev/Pictures
$ ls
150px-Flore_des_serres_v14_053a.jpg
301px-Flore_des_serres_v14_053a.jpg
481px-Flore_des_serres_v14_053a.jpg
```
#### Tìm kiếm

> **Clicking:** Chỉ cần gõ tệp tin hoặc thư mục cần tìm trên thanh toolbar với đường dẫn: ví dụ /usr/share/applications/...
> Trên đường dẫn thanh toolbar sẽ hiển thị những suggest items matched với nội dung mà chúng ta muốn tìm và hit enter
> item tìm được.

![Search](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/find.png)

> **Typing:** Đối với command line ta có thể sử dụng **ls** + **grep** "matched-search" (hoặc _find *.jpg*_)
> Và ví dụ dưới đây là tìm kiếm tất cả các tệp tin có định dạng file ".jpg".
> Có thể cung cấp đường dẫn đến thư mục cần tìm như một option 

```console
$ pwd
/home/qndev
$ ls
Desktop  Documents  Downloads  Music  Pictures  Public  Repositories  Templates  Videos
$ ls Pictures | grep ".jpg"
150px-Flore_des_serres_v14_053a.jpg
301px-Flore_des_serres_v14_053a.jpg
481px-Flore_des_serres_v14_053a.jpg
512px-Flore_des_serres_v14_053a.jpg
Flore_des_serres_v14_053a.jpg
$ cd Pictures
$ pwd
/home/qndev/Pictures
$ ls | grep ".jpg"
150px-Flore_des_serres_v14_053a.jpg
301px-Flore_des_serres_v14_053a.jpg
481px-Flore_des_serres_v14_053a.jpg
512px-Flore_des_serres_v14_053a.jpg
Flore_des_serres_v14_053a.jpg
```

#### Di chuyển qua lại giữa các thư mục

> **Clicking:** Double-click vào thư mục, hit back icon trên toolbar để quay trở về thư mục cha hoặc trước đó.

![Navigate Directories](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/navigate_directories.png)

> **Typing:** _**cd**_ command line sẽ đưa bạn đến những thư mục khác nhau với đường dẫn coi như option đi kèm với _**cd**_ cho từng trường hợp
> **cd ..** quay trở lại thư  thư mục cha, **cd ~** quay trở về thư mục user home (thư mục người dùng).

```console
$ pwd
/
$ ls
bin   home            lib         mnt   run   tmp      vmlinuz.old
boot  initrd.img      lib64       opt   sbin  usr
dev   initrd.img.old  lost+found  proc  srv   var
etc   keybase         media       root  sys   vmlinuz
$ cd home
$ pwd
/home
$ ls
lost+found  qndev
$ cd qndev
$ ls
Desktop    Downloads  Pictures  Repositories  Videos
Documents  Music      Public    Templates
$ cd Pictures
$ pwd
/home/qndev/Pictures
$ cd ..
& pwd
/home/qndev
$ cd /usr/share/applications
$ pwd
/usr/share/applications
$ cd ~
$ pwd
/home/qndev
```

#### Tạo file, folder, rename

> **Clicking:** Right click tại vị trí muốn tạo tệp tin hoặc thư mục _and and and..._ click vào item Create Document hoặc Create Folder.
> Right click file hoặc folder và chọn **Rename...** option -> đổi tên.

Create Folder             |  Create Document File
:-------------------------:|:-------------------------:
![Create Folder](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/createfolder.png)  |   ![Create Document File](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/createnewfile.png) 

![Rename](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/rename.png)

> **Typing:** **echo**/**touch**/**mkdir**/**mv**

```console
$ echo Hello > /home/qndev/Documents/helloworld.txt
$ echo World >> /home/qndev/Documents/helloworld.txt
$ touch /home/qndev/Documents/helloworld.txt && echo "Hello World" > /home/qndev/Documents/helloworld.txt
$ mkdir directory_name
$ mv old_name new_name
```

Như vậy với các câu lệnh trên ta có thể tạo ra tệp tin helloworld.txt trong thư mục Documents với nội dung **Hello World**, thư mục rỗng với tên 
directory_name.

#### Di chuyển, sao chép tệp tin

> **Just** kéo thả tệp tin đến nơi cần tới.
> **Right click** sao chép tệp tin _and_ **right click again** -> paste.

![Move](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/movefile.png)

> **Typing:** **mv**/**cp**.

```console
$ pwd && ls
/home/qndev/Desktop
crud-operations-sap-ui5  myblog                              test.txt
hyde                     qndev.github.io
jekyll-theme             Screenshot_2019-07-14_05-38-25.png
$ mv test.txt /home/qndevDocuments
$ ls /home/qndevDocuments
test.txt
```
#### Create Launcher applications

> **Clicking:** Right click và chọn Create Launcher điền đầy đủ thông tin ví dụ như hình dưới.
> Right click file Launcher vừa tạo xong và chọn **Properties** file -> tab **Permissions** -> tick **_Allow this file to run as a program_**

Create Launcher applications | Allow file as program
:-------------------------:|:-------------------------:
![Create Launcher applications](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/createlauncher.png) | ![Allow this file to run as a program](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/allowprogram.png)

> **Typing:** [Click here](https://qndev.github.io/2019/01/24/make-desktop-shortcut-in-linux)

### Ok

Như vậy việc thao tác giữa môi trường giao diện Desktop Environment (DE) cùng với các utilities đi kèm với nó với hàng loạt các thao tác **Clicking** cũng tương tự như làm việc với giao diện dòng lệnh thông qua Terminal. Thông qua một số câu lện command line đơn giản ta có thể thấy việc sử dụng Linux thật sự thú vị.

---
