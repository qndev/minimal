---
layout: post
title: "Signing commits with GPG"
categories: [Git]
tags: [github, gpg]
comments: true
---

### Tạo GPG key nếu bạn chưa có GPG key

> _**Note:**_ GnuPG không được cài đặt mặc định trên các hệ điều hành như OS X hay Windows
> vì vậy để sử dụng GPG bạn cần cài đặt GPG tool trên máy tính cá nhân [tại đây](https://www.gnupg.org/download/index.html)

<!--more-->

##### 1. Mở Terminal/Git Bash 

##### 2. Tạo cặp khoá public và private key bằng lệnh sau:

```shell
$ gpg --full-gen-key
```
##### 3. Lựa chọn loại key mà bạn muốn, mặc định là RSA and RSA (default)

```shell
gpg (GnuPG) 2.1.18; Copyright (C) 2017 Free Software Foundation, Inc.
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.

Please select what kind of key you want:
   (1) RSA and RSA (default)
   (2) DSA and Elgamal
   (3) DSA (sign only)
   (4) RSA (sign only)
Your selection? 1

```
##### 4. Câu hỏi tiếp theo sau khi chọn loại key là kích thước, độ dài khoá, nhập kích thước khóa mong muốn (4096)

```shell
RSA keys may be between 1024 and 4096 bits long.
What keysize do you want? (3072) 4096
Requested keysize is 4096 bits
```
##### 5. Tiếp theo, bạn cần xác định và xác nhận thời hạn hiệu lực của khóa của bạn (0 = key does not expire)

```shell
Please specify how long the key should be valid.
         0 = key does not expire
      <n>  = key expires in n days
      <n>w = key expires in n weeks
      <n>m = key expires in n months
      <n>y = key expires in n years
Key is valid for? (0) 0
Key does not expire at all
Is this correct? (y/N) y
```
##### 6. Điền đầy đủ thông tin tên, email của bạn và xác nhận Okay

```shell
GnuPG needs to construct a user ID to identify your key.

Real name: NGUYEN DINH QUANG
Email address: quangnd.hust@gmail.com
Comment: Signing commits with GPG
You selected this USER-ID:
    "NGUYEN DINH QUANG (Signing commits with GPG) <quangnd.hust@gmail.com>"

Change (N)ame, (C)omment, (E)mail or (O)kay/(Q)uit? O
We need to generate a lot of random bytes. It is a good idea to perform
some other action (type on the keyboard, move the mouse, utilize the
disks) during the prime generation; this gives the random number
generator a better chance to gain enough entropy.
```
##### 7. Nhập mật khẩu cho key

##### 8. Xem danh sách private key mà bạn vừa tạo

```shell
$ gpg --list-secret-keys --keyid-format LONG
/home/qndev/.gnupg/pubring.kbx
------------------------------
sec   rsa4096/049992A7735D3F37 2019-07-03 [SC]
      735DCD1E4BDEC073C545CAE4049992A7735D3F37
uid                 [ultimate] NGUYEN DINH QUANG (GnuPG key) <quangnd.hust@gmail.com>
ssb   rsa4096/725B673277F5A92F 2019-07-03 [E]
```
##### 9. Export public key với GPG key ID là _**049992A7735D3F37**_ tại _**sec**_ bên trên

```shell
$ gpg --armor --export 049992A7735D3F37
```
##### 10. Cuối cùng copy public key và add vào Github hoặc GitLab account

```shell
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
0ISaQFM0D0wVxq7L6bxuU07Q
=6AQO
-----END PGP PUBLIC KEY BLOCK-----
```

### Add GPG key vào Github account (tương tự GitLab)

##### 1. Ở góc trên bên phải, nhấp vào hình đại diện và đi đến Settings >> chọn SSH and GPG keys >> chọn New GPG key.

Settings                   | SSH and GPG keys          | New GPG key
:-------------------------:|:-------------------------:|:-------------------------:
![Settings](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/settingsgithub.png) | ![SSH and GPG keys](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/gpgkey.png) | ![New GPG key](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/newgpgkey.png)

##### 2. Paste GPG key vừa copy bên trên và click _**Add GPG key**_

![Paste GPG key](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/addnewgpgkey.png)

### Liên kết GPG key với Git

- Liệt kê danh sách private key `$ gpg --list-secret-keys --keyid-format LONG`
- Sao chép GPG key ID **sec**. Ở ví dụ này đó là **049992A7735D3F37**
```shell
$ gpg --list-secret-keys --keyid-format LONG
sec   rsa4096/049992A7735D3F37 2019-07-03 [SC]
      735DCD1E4BDEC073C545CAE4049992A7735D3F37
uid                 [ultimate] NGUYEN DINH QUANG (GnuPG key) <quangnd.hust@gmail.com>
ssb   rsa4096/725B673277F5A92F 2019-07-03 [E]
```
- Config GPG signing key với Git
```shell
$ git config --global user.signingkey 049992A7735D3F37
```
Thay thế 049992A7735D3F37 bằng GPG key ID của bạn.

### Signing commits

```shell
$ git commit -S -m "Your commit message"
```
Với option **-S** chỉ định GPG-sign commits

### Ok kiểm tra “Verified” commit trên Github

![Verified](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/verified.png)

---
