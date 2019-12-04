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

