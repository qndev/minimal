---
layout: post
title: "Lecture notes of 18.06SC - Elimination with matrices [2]"
categories: [Mathematics]
tags: [linear algebra, OCW]
comments: true
---

### Method of Elimination

Phép khử là kỹ thuật được sử dụng bởi hầu hết các phần mềm máy tính để giải hệ phương trình tuyến tính. Nó tìm nghiệm \\(\mathbf{x}\\) của \\(A\mathbf{x}=b\\) khi ma trận \\(A\\) là ma trận nghịch đảo. Ví dụ:

\\[A=\begin{bmatrix}\boxed 1 & 2 & 1 \\\ 3 & 8 & 1 \\\ 0 & 4 & 1\end{bmatrix} and \; \mathbf{b}=\begin{bmatrix}2 \\\ 12 \\\ 2\end{bmatrix}\\]

Số \\(1\\) mà ta đánh dấu trong ô vuông của ma trận \\(A\\) ở trên được gọi là phần tử chốt đầu tiên. Chúng ta lấy dòng đầu tiên rồi sau đó nhân từng phần tử của dòng với một số thích hợp (trong trường hợp này là \\(3\\)) rồi trừ đi các giá trị tương ứng của dòng thứ hai. Phần tử đầu tiên của dòng thứ hai sẽ bằng \\(0\\). Như vậy ta đã thực hiện phép khử phần tử \\(3\\) của dòng hai và cột một.

Bước tiếp theo ta thực hiện phép khử khác để biến phần tử ở hàng ba và cột một thành \\(0\\). Phần tử chốt thứ hai bây giờ xuất hiện tại vị trí hàng hai cột hai. Tiến hành tìm phần tử (trong trường hợp này là số \\(2\\)) để nhân với hàng hai để loại bỏ \\(4\\) ở hàng ba cột hai. Ta thu được phần tử chốt thứ ba là \\(5\\) ở vị trí hàng 3 cột 3 sau khi tiến hành lấy hàng ba trừ 2 nhân với hàng hai.

Như vậy chúng ta bắt đầu bằng ma trận khả nghịch \\(A\\) và biến nó thnahf ma trận tam giác trên \\(U\\), các phần tử bên trái phía dưới của \\(U\\) đều bằng \\(0\\) và các phần tử chốt \\(1, 2, 5\\) trên đường chéo của \\(U\\).

\\[
A=\begin{bmatrix}\boxed 1 & 2 & 1 \\\ 3 & 8 & 1 \\\ 0 & 4 & 1\end{bmatrix} \to \begin{bmatrix}\boxed 1 & 2 & 1 \\\ 0 & \boxed 2 & -2 \\\ 0 & 4 & 1\end{bmatrix} \to U=\begin{bmatrix}\boxed 1 & 2 & 1 \\\ 0 & \boxed 2 & -2 \\\ 0 & 0 & \boxed 5\end{bmatrix}
\\]

Chúng ta cũng thực hiện các phép khử tương ứng của ma trận \\(A\\) đối với vector \\(\mathbf{b}=\begin{bmatrix}2 \\\ 12 \\\ 2\end{bmatrix}\\).

Phép khử đã biến phương trình \\(A\mathbf{x}=\mathbf{b}\\) thành \\(U\mathbf{x}=\mathbf{c}\\), trong ví dụ trên \\(U=\begin{bmatrix}1 & 2 & 1 \\\ 0 & 2 & -2 \\\ 0 & 0 & 5\end{bmatrix}\\) được biến đổi từ \\(A\\) và \\(\mathbf{c}=\begin{bmatrix}2 \\\ 6 \\\ -10\end{bmatrix}\\) từ \\(\mathbf{b}\\).

Phương trình \\(U\mathbf{x}=\mathbf{c}\\) rõ ràng là dễ giải hơn bằng cách thay thế ngược các ẩn số từ dưới lên, trong ví dụ với phương trình này ta có thể viết thành hệ phương trình tuyến tính với 3 ẩn số \\(\mathbf{x}=\begin{bmatrix}x \\\ y \\\ z\end{bmatrix}\\\):

\\[
\left\\{\begin{array}{rl}
x + 2y + z & = 2 \\\
2y -2z & = 6 \\\
5z & = -10
\end{array}\right. \to z=-2, y=1, x=2
\\]

Nghiệm \\(\mathbf{x^T}=(2,1,-2)\\) cũng là nghiệm của phương trình \\(A\mathbf{x}=\mathbf{b}\\).

Ta có định thức của \\(U\\) là tích của các phần tử chốt trên đường chéo. Các phần tử chốt này phải khác không, nếu có phần tử \\(0\\) tại vị trí chốt thì ta cần hoán đổi hàng đó với hàng không có phần tử \\(0\\) tại vị trí chốt. Nếu không có hàng nào thỏa mãn sau khi hoán đổi thì ma trận \\(A\\) không khả nghịch. Việc khử không được sử dụng để tìm một nghiệm duy nhất vì nó không tồn tại.

### Elimination Matrices

Tích của ma trận (3x3) và vector cột (3x1) là một vector (3x1) đó là tổ hợp tuyến tính các cột của ma trận.

Tích của một hàng (1x3) và ma trận (3x3) là một hàng (1x3) là tổ hợp tuyến tính của các hàng của ma trận.

Việc phép khử để lấy phần tử chốt thứ hai bằng cách trừ 3 lần hàng một từ hàng hai (nghĩa là \\(row(2)=-3.row(1)+row(2))\\) tương đương với việc tính tích của hai ma trận dưới đây:

\\[
\begin{bmatrix}1 & 0 & 0 \\\ -3 & 1 & 0 \\\ 0 & 0 & 1\end{bmatrix}\begin{bmatrix}1 & 2 & 1 \\\ 3 & 8 & 1 \\\ 0 & 4 & 1\end{bmatrix}=\begin{bmatrix}1 & 2 & 1 \\\ 0 & \boxed 2 & -2 \\\ 0 & 4 & 1\end{bmatrix}
\\]

Ma trận khử được dùng để khử các phần tử ở hàng \\(m\\) cột \\(n\\) được kí hiệu là \\(E_{mn}\\). Việc tính toán trên đưa ma trận từ \\(A\\) thành \\(E_{21}A\\). Ba bước khử ở trên dẫn đến \\(U\\): \\(E_{32}(E_{31}(E_{21}A))=U\\) với \\(E_{31}=I\\), do đó:

\\[E_{32}(E_{21}A)=U\\]

Phép nhân ma trận có tính chất kết hợp vì vậy ta cũng có thể viết \\((E_{32}E_{21})A=U\\). Tích của hai ma trận \\(E_{32}E_{21}\\) cho chúng ta biết cách để biến đổi ma trận \\(A\\) thành ma trận \\(U\\). Nghịch đảo của ma trận \\(E_{32}E_{21}\\) cho chúng ta biết cách để biến đổi ma trận \\(U\\) thành ma trận \\(A\\).

\\[{(E_{32}E_{21})}^{-1}(E_{32}E_{21})A={(E_{32}E_{21})}^{-1}U) \sim A={(E_{32}E_{21})}^{-1}U\\]

Nếu chúng ta giải phương trình \\(U\mathbf{x}=EA\mathbf{x}=E\mathbf{b}\\), thì cũng đồng nghĩa với việc chúng ta giải phương trình \\(A\mathbf{x}=\mathbf{b}\\). Đây là lý do tại sao phương pháp khử hoạt động: tất cả các bước có thể được đảo ngược.

Một ma trận hoán vị trao đổi hai hàng của một ma trận; ví dụ:

\\[
\begin{bmatrix}0 & 1 & 0 \\\ 1 & 0 & 0 \\\ 0 & 0 & 1\end{bmatrix}
\\]

Hàng thứ nhất và hàng thứ hai của ma trận \\(PA\\) tương ứng là hàng thứ hai và hàng thứ nhất của ma trận \\(A\\). Ma trận \\(P\\) được xây dựng bằng cách trao đổi các hàng của ma trận đơn vị.

Để trao đổi các cột của ma trận ta thực hiện bằng cách nhân vào bên phải của ma trận đó (như trong \\(AP\\) với ma trận hoán vị. Lưu ý rằng phép nhân ma trận không có tính chất giao hoán: \\(PA\ne AP\\).

### Inverses

Chúng ta có ma trận:

\\[
E_{21}=\begin{bmatrix}1 & 0 & 0 \\\ -3 & 1 & 0 \\\ 0 & 0 & 1\end{bmatrix}
\\]

bằng cách \\(row(2)-3.row(1)\\), hay nói cách khác đó là phép biến đổi ma trận \\(A\\) ở ví dụ trên thành ma trận \\(E_{21}A=\begin{bmatrix}1 & 2 & 1 \\\ 0 & 2 & -2 \\\ 0 & 4 & 1\end{bmatrix}\\). Để hòa tác lại thao tác tính toán, biến đổi này hay biến ma trận \\(E_{21}A\\) trở lại ma trận \\(A\\) chúng ta cần sử dụng ma trận nghịc đảo:

\\[
E_{21}^{-1}=\begin{bmatrix}1 & 0 & 0 \\\ 3 & 1 & 0 \\\ 0 & 0 & 1\end{bmatrix}
\\]

Và trong thực tế thì \\(E_{21}^{-1}E_{21}=I\\).

---
> [MIT OpenCourseWare](https://ocw.mit.edu)
>
> **18.06SC Linear Algebra** / Fall 2011
>
> [Terms of Use](https://ocw.mit.edu/terms/)

---
