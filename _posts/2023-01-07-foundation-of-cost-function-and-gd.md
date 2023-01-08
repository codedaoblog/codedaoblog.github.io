---
title: Gradient Descent and Loss function in a Intuitive way
author: hoanglinh
categories: [Machine Learning, Deep Learning]
tags: [optimization algorithms]
math: true
img_path: posts_media/2023-01-07-posts/
---

Trong bài viết này, chúng ta sẽ cùng nhau tìm hiểu về nguồn gốc cơ bản của thuật toán Gradient descent (GD) trong machine learning (ML) và hàm loss (tính toán mất mát) một cách cơ bản nhất. Giả sử rằng, bạn đã có kiến thức nền tảng cơ bản về hình học 2D hoặc 3D nhưng nếu không thì cũng không có vấn đề gì lớn.

Giả sử rằng, trong một mặt phẳng, ta được cho 3 điểm với tọa độ là $(1, 1), (2, 2), (3, 3)$, biểu diễn dưới mặt phẳng 2D, ta có hình như dưới:

![3-points](plot-3-points.svg)

Bây giờ, nếu ta được yêu cầu là tìm phương trình thỏa mãn 3 điểm đó, hay nói cách khác là từ phương trình, ta có thể kẻ được một đường thẳng đi qua 3 điểm đó. Phương trình cần có dạng:
$$
y = f(X) = a \mathbf{X}+ b \tag{1}
$$
Trong đó, $a$ và $b$ là hai hệ số của đườn thẳng, $\mathbf{X}$ là vector tọa độ theo trục $x$ và $y$ là vector tọa độ theo trục $y$. Nhiệm vụ của chúng ta là tìm hệ số $a, b$ sao cho thỏa mãn phương trình. Trong trường hợp này, ta có thể nhẩm ngay ra hệ số của $a=0$ và $b=1$. Hãy thử với trường hợp khác xem sao:

![no-solution](3-lines-no-solution.png){: width="450"}

