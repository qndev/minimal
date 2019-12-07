---
layout: post
title: "Factorization into A = LU [4]"
categories: [Mathematics]
tags: [linear algebra, OCW]
comments: true
---

### Inverse of a product - nghịc đảo của tích ma trận

Nghịch đảo của tích hai ma trận \\(AB\\) đó là \\(B^{-1}A^{-1}\\)

### Transpose of a product - chuyển vị

Chúng ta có thể thu được chuyển vị của ma trận bằng cách hoán đổi các hàng và cột của nó. Hay nói theo cách khác đó là phần tử ở hàng \\(i\\) cột \\(j\\) của ma trận \\(A\\) sẽ là phần tử ở hàng \\(j\\) cột \\(i\\) của ma trận \\(A^{T}\\).

Chuyển vị của tích ma trận \\(AB\\) là \\(B^{T}A^{T}\\). Đối với bất kì ma trận khả nghịch \\(A\\), thì nghịc đảo của \\(A^{T}\\) là \\((A^{-1})^T\\):

\\[
(A^{T})^{-1}=(A.A^{-1})^T.(A^T)^{-1}=(A^{-1})^T.(A^T).(A^T)^{-1}=(A^{-1})^T
\\]

### A = LU

Chúng ta đã biết cách sử dụng phương pháp khử để chuyển đổi một ma trận \\(A\\) phù hợp thành một ma trận tam giác trên \\(U\\). Điều này dẫn đến phân tích thành nhân tử \\(A\\) thành \\(LU\\), điều mà rất hữu ích cho việc hiểu về ma trận \\(A\\).

Nhớ lại rằng chúng ta có thể mô tả phương pháp khử các phần tử của ma trận \\(A\\) (trong trường hợp không có việc hoán đổi các hàng trong khi thực hiện phép khử) theo cách nhân với một chuỗi các ma trận loại bỏ \\(E_{ij}\\), vì vậy \\(A\to E_{21}A \to E_{31}E_{21} \to \cdots \to U\\). Trong trường hợp ma trận kích thước \\(2 \times 2\\) như sau:

\\[
E_{21}A=U \sim \begin{bmatrix}1 & 0 \\\ -4 & 1\end{bmatrix}\begin{bmatrix}2 & 1 \\\ 8 & 7\end{bmatrix}=\begin{bmatrix}2 & 1 \\\ 0 & 3\end{bmatrix}
\\]

Chúng ta có thể chuyển đổi thành \\(A=LU\\) bằng cách loại bỏ ma trận \\(E_{21}\\); để làm đuược điều đó ta nhân hai vế của biểu thức với \\(E_{21}A=U\\) với ma  trận nghịch đảo của nó \\(E_{21}^{-1}\\): \\(E_{21}^{-1}E_{21}A=E_{21}^{-1}U\\).

\\[
A=LU\sim\begin{bmatrix}2 & 1 \\\ 8 & 7\end{bmatrix}=\begin{bmatrix}1 & 0 \\\ 4 & 1\end{bmatrix}\begin{bmatrix}2 & 1 \\\ 0 & 3\end{bmatrix}
\\]

Ma trận \\(U\\) là ma trận tam giác trên với các phần tử chốt trên đường chéo. Ma trận \\(L\\) là ma trận tam giác dưới và cũng có các phần tử \\(1\\) trên đường chéo. Đôi khi chúng ta cũng sẽ muốn tạo ra một ma trận đường chéo mà các phần tử là phần tử chốt:

\\[
A=LDU^{\mathbf'}\sim\\begin{bmatrix}2 & 1 \\\ 8 & 7\end{bmatrix}=\begin{bmatrix}1 & 0 \\\ 4 & 1\end{bmatrix}\begin{bmatrix}2 & 0 \\\ 0 & 3\end{bmatrix}\begin{bmatrix}1 & 1/2 \\\ 0 & 1\end{bmatrix}
\\]

Trong trường hợp không gian ba chiều, nếu \\(E_{32}E_{31}E_{21}A=U\\) thì \\(A=E_{21}^{-1}E_{31}^{-1}E_{32}^{-1}U=LU\\).

Ví dụ, giả sử \\(E_{31}\\) là ma trận đơn vị và \\(E_{32}\\), \\(E_{21}\\) là hai ma trận dưới đây:

\\[
E_{32}E_{21}=E \sim \begin{bmatrix}1 & 0 & 0\\\ 0 & 1 & 0 \\\ 0 & -5 & 1\end{bmatrix}\begin{bmatrix}1 & 0 & 0\\\ -2 & 1 & 0 \\\ 0 & 0 & 1\end{bmatrix}=\begin{bmatrix}1 & 0 & 0\\\ -2 & 1 & 0 \\\ 10 & -5 & 1\end{bmatrix}
\\]

Phần tử \\(10\\) mới xuất hiện góc trái do ta trừ 2 lần dòng nhất từ dòng thứ hai, sau đó trừ 5 lần dòng mới thứ hai từ dòng thứ ba.

Phép phân tích thành nhân tử \\(A=LU\\) thích hợp hơn so với phép biến đổi \\(EA=U\\) bởi vì tổ hợp các phép trừ của các hàng không có tác động lên \\(L\\) như nó đã làm đối với \\(E\\). Và \\(L=E^{-1}=E_{21}^{-1}E_{32}^{-1}\\).

\\[
E_{21}^{-1}E_{32}^{-1}=L \sim \begin{bmatrix}1 & 0 & 0\\\ 2 & 1 & 0 \\\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix}1 & 0 & 0\\\ 0 & 1 & 0 \\\ 0 & 5 & 1\end{bmatrix}=\begin{bmatrix}1 & 0 & 0\\\ 2 & 1 & 0 \\\ 0 & 5 & 1\end{bmatrix}
\\]

Để ý rằng phần tử \\(0\\) ở hàng ba cột một của ma trận \\(L=E^{-1}\\), nơi mà có phần tử \\(10\\) của \\(E\\). Nếu không có sự tráo đổi hàng. các số nhân của ma trận loại bỏ được sao chép trực tiếp vào \\(L\\).

### How expensive is elimination?

Một vài ứng dụng yêu cầu nghịch đảo các ma trận có kích thước rất lớn. Việc này thực hiện được là nhờ máy tính. Làm thế nào chúng ta có thể biết được máy tính làm viêc vất vả như thế nào? Chúng tốn bao nhiêu thời gian?

Có bao nhiêu phép tính mà máy tính thực thiện trong suốt quá trình thực thi phép khử đối với ma trận \\(n\times n\\)? Phép toán đặc trưng đó là phép nhân một hàng và sau đó trừ nó bởi hàng khác, đòi hỏi theo thứ tự của \\(n\\) phép tính. Có \\(n\\) hàng vì vậy tổng số phép toán sử dụng để khử các phần tử ở cột thứ nhất là \\(n^2\\). Dòng thứ hai và cột thứ hai thì có tổng số phép tính ít hơn với chi phí vào khoảng \\(((n-1)^2\\)) và tiếp tục với các hàng và cột khác của ma trận \\(n\times n\\). Như vậy tổng cộng chi phí hay số phép toán cần thực hiện để biến đổi \\(A\\) thành \\(LU\\) theo thứ tự là \\(n^3\\):

\\[
1^2+2^2+\cdots+(n-1)^2+n^2=\sum_{i=1}^n i^2\approx\displaystyle \int_0^nx^2dx=\frac{1}{3}n^3
\\]

Trong khi chúng ta thực hiện phép biến đổi \\(A\\) đồng thời chúng ta cũng thực hiện trên \\(\mathbf{b}\\) với chi phí là \\(n^2\\) (chi phí này không đáng kể so với \\(n^3\\)).

### Row exchanges

Điều gì sẽ xảy ra nếu cần phải hoán đổi các hàng với nhau trong khi thực hiện phép khử hay nói theo cách khác đó là điều gì sẽ xảy ra nếu có phần tử \\(0\\) ở vị trí chốt? 

Để hoán đổi vị trí hai hàng với nhau ta nhân vào bên trái với ma trận hoán vị, ví dụ: Ma trận \\(P_{12}=\begin{bmatrix}0 & 1 & 0\\\ 1 & 0 & 0 \\\ 0 & 0 & 1\end{bmatrix}\\) hoán đổi hàng một và hai của ma trận \\(3\times 3\\). Nghịch đảo của ma trận \\(P\\) là \\(P^{-1}=P^T\\).

Có \\(n!\\) cách khác nhau để hoán đổi các hàng của ma trận \\(n\times n\\) vì vậy sẽ có \\(n!\\) ma trận hoán vị.

---
> [MIT OpenCourseWare](https://ocw.mit.edu)
>
> **18.06SC Linear Algebra** / Fall 2011
>
> [Terms of Use](https://ocw.mit.edu/terms/)

---
