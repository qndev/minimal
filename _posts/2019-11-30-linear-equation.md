---
layout: post
title: "Phương trình tuyến tính trong đại số tuyến tính - Notes"
categories: [Mathematics]
tags: [linear algebra]
comments: true
---

### Hệ phương trình tuyến tính

**Một phương trình tuyến tính** với các biến \\(x_1,x_2,x_3,...,x_n\\) trong phưowng trình có thể viết dưới dạng:
\\[a_1x_1 + a_2x_2 + ... + a_nx_n = b \tag{1}\\]
trong đó \\(b\\) và các hệ số \\(a_1,a_2,...,a_n\\) là các số thực. Các chỉ số \\(n\\) là các số nguyên dương.
Ví dụ: Các phương trình:
\\[-x_1 + 15x_1 + 4x_2 = 1996 \; và \; x_2 = 28x_1 +2x_3 + 15\\]
là các phương trình tuyến tính bởi khi ta rút gọn chúng lạ ta có \\(14x_1 + 4x_2 = 1996 \; và \; 28x_1 - x_2 +2x_3 = -15 \\)có dạng (1).
Các phương trình: \\(4x_1 - 5x_2 = x_1x_2 \; và \; x_2 = 2\sqrt{x_1} -6\\) không phải là các phương trình tuyến tính.

**Hệ phương trình tuyến tính** hay hệ tuyến tính là tổ hợp của một hoặc nhiều phương trình tuyến tính có liên quan đến các biến giống nhau được gọi là \\(x_1,x_2,...,x_n \\).
Ví dụ: Ta có hệ phương trình: \\[\begin{cases} 2x_1 - x_2 + 1.5x_3 = 8 \\\ x_1 + 0x_2 - 4x_3 = -7 \end{cases} \tag{2}\\]

**Lời giải của hệ** là danh sách \\((s_1,s_2,s_3,...,s_n)\\) các số mà tại đó làm thoả mãn từng phương trình trong hệ (các giá trị \\(s_1,s_2,s_3,...,s_n\\)) thay thế tương ứng chó các biến (\\(x_1,x_2,x_3,...,x_n\\)). Ví dụ: \\((5,6.5,3)\\) là lời giải cho hệ phương trình (2) bởi vì khi thay thế các số thực trên tương ứng với \\(x_1,x_2,x_3\\) của hệ ta được các phương trình luôn đúng: \\(8 = 8 \; và -7 = -7\\).

**Tất cả các lời giải** có thể thoả mãn hệ được gọi là tập lời giải (tập nghiệm). Hai hệ phương trình tuyến tính được gọi là tương đương nhau nếu chúng có cùng tập nghiệm.

**Chú ý:** Một hệ phương trình tuyến tính có thể có: không có nghiệm hoặc có chính xác một nghiệm duy nhất hoặc có vô số nghiệm.

Ví dụ: Ta có hệ phương trình: \\(\begin{cases} x_1 - 2x_2 = -1 \\\ -x_1 + 3x_2 = 3 \; \end{cases}\\) có nghiệm duy nhất.

![Image: Hệ phương trình có nghiệm duy nhất](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/sysequation1.gif)

Trong hệ trên hệ pt có cặp nghiệm \\((x_1,x_2) = (3,2)\\).

Hệ phương trình: \\(\begin{cases} x_1 - 2x_2 = -1 \\\ -x_1 + 2x_2 = 3 \; \end{cases}\\) không có nghiệm.

![Image: Hệ phương trình không có nghiệm](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/sysequation2.gif)

Hệ phương trình: \\(\begin{cases} x_1 - 2x_2 = -1 \\\ -x_1 + 2x_2 = 1 \; \end{cases}\\) có vô số nghiệm.

![Image: Hệ phương trình có vô số nghiệm](https://raw.githubusercontent.com/qndev/qndev.github.io/master/public/images/sysequation3.gif)

`Một hệ phương trình được gọi là thoả mãn nếu chúng hoặc có một nghiệm hoặc vô số nghiệm, hệ pt không thoả mãn nếu chúng vô nghiệm.`

**Kí hiệu ma trận** 

Các thông tin cần thiết của một hệ phương trình tuyến tính có thể ghi lại gọn trong một hình chữ nhật bao gồm các hệ số của hệ phương trình được gọi là ma trận. Ta có hệ pt sau:
\\[
\left\\{
\begin{array}{ll}
x_1 - 2x_2 + x_3 &= 0 \\\
2x_2 - 8x_3 &= 8 \\\
5x_1 -5x_3 &= 10
\end{array}
\right.
\tag{3}\\]

Với các hệ số tương ứng với các biến của các cột như sau:
\\(\begin{bmatrix}1 & -2 & 1 \\\ 0 & 2 & -8 \\\ 5 & 0 & -5 \end{bmatrix}\\) ma trận các hệ số của hệ pt (3).

Và ma trận \\(\begin{bmatrix}1 & -2 & 1 &0 \\\ 0 & 2 & -8 &8 \\\ 5 & 0 & -5 & 10 \end{bmatrix}\\) (4) được gọi là ma trận bổ sung của hệ.

**Chú ý:** Ở hàng 2 và hàng 3 của các ma trận trên có các phần tử 0 tương ứng với các hệ số tương ứng với các biến \\(x_1\\) và \\(x_2\\) của phương trình (2) và (3) của hệ (3) nhưng không được xuất hiện. Cụ thể ta có thể viết lại pt (2) và (3) của hệ (3) như sau: \\(0x_1+2x_2-8x_3 = 8\\) và \\(5x_1+0x_2-5x_3 = 10\\). Ma trận bổ sung bên trên có thêm cột bên phải là các hằng số bên phải của các phương trình trong hệ.

Kích thước của ma trận được thể hiện thông qua các chỉ số hàng và cột mà ma trận có. Ma trận (4) có 3 hàng và 4 cột được gọi là ma trận 3 nhân 4 (3 by 4).

**Giải hệ phương trình tuyến tính**

Giải hệ phương trình tuyến tính (3)

Lời giải: Thực hiện thủ tục khử (loại bỏ) được biểu hiện bằng hệ phương trình và ma trận hệ số của hệ phương trình song song để dễ dàng so sánh.

...
