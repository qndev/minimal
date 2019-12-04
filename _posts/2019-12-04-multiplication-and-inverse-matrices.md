---
layout: post
title: "Lecture notes of 18.06SC - Multiplication and inverse matrices [3]"
categories: [Mathematics]
tags: [linear algebra, OCW]
comments: true
---

### Matrix Multiplication - Phép nhân ma trận

Ta có tích của hai ma trận \\(AB=C\\), với \\(A\\) là ma trận \\(m\\)x\\(n\\), \\(B\\) là ma trận \\(n\\)x\\(p\\) thì \\(C\\) là ma trận \\(m\\)x\\(p\\). Chúng ta sẽ sử dụng \\(c_{ij}\\) để kí hiệu cho các giá trị ở hàng \\(i\\) và cột \\(j\\) của ma trận \\(C\\).

#### Standard (row times column) - hàng nhân cột

Cách cơ bản để miêu tả phép nhân ma trận đó là các giá trị \\(c_{ij}\\) bằng tích của hàng \\(i\\) của ma trận \\(A\\) và cột \\(j\\) của ma trận \\(B\\). Hay nói cách khác:

\\[
c_{ij}=\sum_{k=1}^n a_{ik}b_{kj}
\\]

#### Columns - theo cột

Tích của ma trận \\(A\\) và cột \\(j\\) của ma trận \\(B\\) bằng cột \\(j\\) của ma trận \\(C\\). Điều này cho chúng ta biết rằng các cột của ma trận \\(C\\) là tổ hợp các cột của ma trận \\(A\\).

#### Rows - theo hàng

Tích của hàng \\(i\\) của ma trận \\(A\\) và ma trận \\(B\\) bằng hàng \\(i\\) của ma trận \\(C\\). Vì vậy các hàng của ma trận \\(C\\) là tổ hợp các hàng của ma trận \\(B\\).

#### Column times row - cột nhân hàng

Một cột của ma trận \\(A\\) là vector \\(m\\)x\\(1\\) và hàng của ma trận \\(B\\) là một vector \\(1\\)x\\(p\\). Tích của chúng là ma trận:

\\[
\begin{bmatrix}2 \\\ 3 \\\ 4\end{bmatrix}\begin{bmatrix}1 & 6\end{bmatrix}=\begin{bmatrix}2 & 12 \\\ 3 & 18 \\\ 4 & 24\end{bmatrix}
\\]

Như vậy ta thấy các cột của ma trận \\(\begin{bmatrix}2 & 12 \\\ 3 & 18 \\\ 4 & 24\end{bmatrix}\\) là phép nhân của cột \\(\begin{bmatrix}2 \\\ 3 \\\ 4\end{bmatrix}\\)của ma trận \\(A\\) và các hàng của ma trận \\(\begin{bmatrix}2 & 12 \\\ 3 & 18 \\\ 4 & 24\end{bmatrix}\\) là phép nhân của hàng \\(\begin{bmatrix}1 & 6\end{bmatrix}\\) của ma trận \\(B\\).

Nếu chúng ta nghĩ về các giá trị, phần tử trong các hàng của ma trận này như những tọa độ điểm \\((2,12)\\), \\((3,18)\\), \\((4,24)\\), tất cả các điểm này cùng nằm trên một đường thẳng, tương tự như hai vector cột với hai điểm có tọa độ \\((2,3,4)\\) và \\((12,18,24)\\).

Như vậy \\(AB=\sum_{k=1}^n \begin{bmatrix}a_{1k} \\\ . \\\ . \\\ . \\\ a_{mk}\end{bmatrix}\begin{bmatrix}b_{k1} & \ldots & b_{kn}\end{bmatrix}\\).

#### Blocks - khối

Nếu chúng ta chia ma trận \\(A\\) và \\(B\\) ra thành các khối khớp nhau, chúng ta có thể viết tích \\(AB\\) dưới dạng của tích các khối:

\\[
\begin{bmatrix}A_1 & A_2 \\\ A_3 & A_4\end{bmatrix}\begin{bmatrix}B_1 & B_2 \\\ B_3 & B_4\end{bmatrix}=\begin{bmatrix}C_1 & C_2 \\\ C_3 & C_4\end{bmatrix}
\\]

Và \\(C_1=A_1B_1+A_2B_3\\).

### Inverses - nghịch đảo ma trận

#### Square matrices - ma trận vuông

Nếu \\(A\\) là ma trận vuông, thì câu hỏi quan trọng nhất mà bạn có thể hỏi về nó là liệu \\(A\\) có ma trận nghich đảo \\(A^{-1}\\). Nếu câu trả lời là có, thì \\(A^{-1}A=I=A^{-1}\\) và chúng ta có thể nói rằng ma trận \\(A\\) là khả nghịch hay không suy biến.

Nếu ma trận \\(A\\) là ma trận suy biến. Ma trận \\(A\\) không có ma trận nghịc đảo - định thức của nó bằng \\(0\\) và chúng ta có thể tìm thấy một vài vector \\(\mathbf{x}\\) để \\(A\mathbf{x}=0\\). Ví dụ:

\\[
\begin{bmatrix}1 & 3 \\\ 2 & 6\end{bmatrix}\begin{bmatrix}3 \\\ -1\end{bmatrix}=\begin{bmatrix}0 \\\ 0\end{bmatrix}
\\]

Trong ví dụ này \\(3.\begin{bmatrix}1 \\\ 2\end{bmatrix}-1.\begin{bmatrix}3 \\\ 6\end{bmatrix}=\begin{bmatrix}0 \\\ 0\end{bmatrix}\\) và cả hai vector cột trong ma trận đó đều nằm trên một đường thẳng.

Việc tìm kiếm ma trận nghịch đảo gần như liên quan đến việc giải hệ phương trình tuyến tính:

\\[
\begin{bmatrix}1 & 3 \\\ 2 & 7\end{bmatrix}\begin{bmatrix}a & c \\\ b & d\end{bmatrix}=\begin{bmatrix}1 & 0 \\\ 0 & 1\end{bmatrix}\sim AA^{-1}=I
\\]

có thể đọc như việc nói "\\(A\\) nhân với cột \\(j\\) của ma trận \\(A^{-1}\\) bằng cột \\(j\\) của ma trận đơn vị". Đay chỉ là một dạng đặc biệt của phương trình \\(A\mathbf{x}=\mathbf{b}\\).

### Gauss-Jordan Elimination - phương pháp khử Gauss

Chúng ta có thể sử dụng phương pháp khử để giải hai hay nhiều phương trình tuyến tính tại cùng một thời điểm.

Ta chỉ cần đặt song song hai ma trận \\(A\\) và ma trận đơn vị \\(I\\) sau đó dùng hệ thống các phép biến đổi không suy biến đồng thời trên các hàng của \\(A\\) và \\(I\\) (thực chất của mỗi phép biến đổi chính là nhân cả \\(A\\) và \\(I\\) với cùng một ma trận không suy biến). Sau một số hữu hạn bước biến \\(A\\) thành \\(I\\) - thực chất là đưa ra ma trận \\(E\\) để \\(EA=I\\) còn ma trận \\(I\\) thì trở thành ma trận \\(EI=E=A^{-1}\\)
\\((E \times \Big[ \ A \; \Big| \; I \ \Big] = \Big[ \ EA \; \Big| \; EI \ \Big] = \Big[ \ I \; \Big| \; E \ \Big])\\).

\\[
\Big[ \ A \; \Big| \; I \ \Big] \to \Big[ \ I \; \Big| \; A^{-1} \ \Big]
\\]

\\[
\left[ \begin{array}{cc|cc}
1 & 3 & 1 & 0 \\\
2 & 7 & 0 & 1 \\\
\end{array} \right] \to 
\left[ \begin{array}{cc|cc}
1 & 3 & 1 & 0 \\\
0 & 1 & -2 & 1 \\\
\end{array} \right] \to
\left[ \begin{array}{cc|cc}
1 & 0 & 7 & -3 \\\
0 & 1 & -2 & 1 \\\
\end{array} \right]
\\]

Một lần nữa chúng ta đã sử dụng phương pháp khử Gauss để biến ma trận ban đầu thành ma trận tam giác trên, và tiếp tục sử dụng ý tưởng của Jordan về việc khử các phần tử ở phía trên bên phải của ma trận.

\\[
A^{-1}=\begin{bmatrix}7 & -3 \\\ -2 & 1\end{bmatrix}
\\]

---
> [MIT OpenCourseWare](https://ocw.mit.edu)
>
> **18.06SC Linear Algebra** / Fall 2011
>
> [Terms of Use](https://ocw.mit.edu/terms/)

---
