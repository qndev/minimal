---
layout: post
title: "Transposes, permutations, spaces R^n [5]"
categories: [Mathematics]
tags: [linear algebra, OCW]
comments: true
---

### Permutations

Phép nhân với ma trận hoán vị \\(P\\) hoán đổi các hàng của ma trận; khi chúng ta thực hiện phương pháp khử, chúng ta sử dụng các ma trận hoán vị để chuyển các phần tử \\(0\\) ra khỏi vị trí chốt. Phép phân tích \\(A=LU\\) khi đó sẽ trở thành \\(PA=LU\\), với \\(P\\) là nma trận hoán vị sẽ sắp xếp lại bất kì hàng nào của ma trận \\(A\\). Và \\(P^{-1}=P^T\\), \\(P^TP=I\\).

### Transposes

Khi chúng ta thực hiện chuyển vị ma trận, các hàng của chúng sẽ thành cột và các cột sẽ thành hàng. Nếu chúng ta kí hiệu phần tử ở hàng \\(i\\) cột \\(j\\) của ma trận \\(A\\) là \\(A_{ij}\\) thì chúng ta có thể biểu diễn \\(A^T\\) bằng: \\(A_{ij}^T=A_{ji}\\). Ví dụ:

\\[
{\begin{bmatrix}1 & 3\\\ 2 & 3\\\ 4 & 1\end{bmatrix}}^T=\begin{bmatrix}1 & 2 & 4\\\ 3 & 3 & 1\end{bmatrix}
\\]

Ma trận \\(A\\) là ma trận đối xứng nếu \\(A^T=A\\). Cho ma trận \\(R\\) bất kì không nhất thiết phải là ma trận vuông thì \\(R^TR\\) luôn luôn là ma trận đối xứng bởi vì \\((R^TR)^T=R^T(R^T)^T=R^TR\\). Chú ý: \\((R^T)^T=R\\).

### Vector spaces

Chúng ta có thể công các vector, nhân vector với một số có nghĩa là chúng ta có thể thảo luận về tổ hợp tuyến tính của vectơ. Các tổ hợp tuyến tính này tuân theo các nguyên tắc của không gian vector.

Một không gian vectơ như vậy là \\(\mathbb{R}^2\\), tập hợp tất cả các vectơ với chính xác hai thành phần số thực. Chúng ta mô tả vector \\(\begin{bmatrix}a \\\ b\end{bmatrix}\\) bằng cách vẽ mũi tên từ gốc tọa độ tới điểm có tọa độ \\((a,b)\\) đó là \\(a\\) đơn vị về phía bên phải và \\(b\\) đơn vị về phía trên, và chúng ta gọi \\(\mathbb{R}^2\\) là mặt phằng \\(x-y\\).

Một ví dụ khác về không gian đó là \\(\mathbb{R}^n\\), tập hợp các vectơ (cột) với n thành phần số thực.

### Closure - tính bao đóng

Tập hợp các vectơ với chính xác hai thành phần có giá trị **thực dương** không phải là một không gian vectơ, bởi vì tổng của hai vectơ bất kì trong tập vẫn là vectơ thuộc tập đó nhưng nhân một số ví dụ \\(-5\\) với một vectơ thì kết quả lại không thuộc tập có hai thành phần giá trị thực dương ở trên.

Chúng ta nói tập hợp các vectơ dương này có tính bao đóng với phép cộng chứ không có tính bao đóng với phép nhân.

Nếu tập hợ các vectơ có tính bao đóng dưới tổ hợp tuyến tính (với cả phép cộng và phép nhân với bất kì số thực nào), và nếu phép nhân và phép cộng hoạt động theo cách này, thì chúng ta gọi tập hợp đó là không gian vectơ.

### Subspaces - không gian vectơ con

Một không gian vectơ được chứa bên trong một không gian vectơ khác được gọi là không gian con của không gian đó. Ví dụ: lấy bất kì vectơ khác \\(\vec 0\\) bào trong \\(\mathbb{R}^2\\). Thì tập hợp các vectơ \\(c\vec v\\) (\\(c\\) là số thực), tạo thành một không gian con của \\(\mathbb{R}^2\\).Tập hợp các vectơ này mô tả một đường thẳng qua \\(\begin{bmatrix}0 \\\ 0\end{bmatrix}\\) trong \\(\mathbb{R}^2\\) và được đóng kín đối với phép cộng.

Không gian vectơ con của \\(\mathbb{R}^2\\) là:

*   \\(\mathbb{R}^2\\)
*   \\(\theta =(0,0)\\)
*   đường thẳng qua \\(\begin{bmatrix}0 \\\ 0\end{bmatrix}\\)

Không gian vectơ con của \\(\mathbb{R}^3\\) là:

*   \\(\mathbb{R}^3\\)
*   \\(\theta =(0,0,0)\\)
*   đường thẳng qua gốc tọa độ
*   mặt phẳng qua gốc tọa độ

### Column space

Cho ma trận \\(A\\) với các cột thuộc \\(\mathbb{R}^3\\), các cột này và tổ hợp tuyến tính của chúng tạo thành một không gian vectơ con của \\(\mathbb{R}^3\\). Đây là không gian vectơ cột \\(C(A)\\). Nếu \\(A=\begin{bmatrix}1 & 3 \\\ 2 & 3 \\\ 4 & 1\end{bmatrix}\\), không gian vectơ cột của \\(A\\) là mặt phẳng đi qua gốc tọa độ của \\(\mathbb{R}^3\\) chứa \\(\begin{bmatrix}1 \\\ 2 \\\ 4\end{bmatrix}\\) và \\(\begin{bmatrix}3 \\\ 3 \\\ 1\end{bmatrix}\\).

---
> [MIT OpenCourseWare](https://ocw.mit.edu)
>
> **18.06SC Linear Algebra** / Fall 2011
>
> [Terms of Use](https://ocw.mit.edu/terms/)

---
