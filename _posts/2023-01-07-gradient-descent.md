---
title: Thuật toán Gradient Descent (GD) với Python
author: hoanglinh
categories: [Machine Learning, Deep Learning]
tags: [optimization algorithms]
math: true
img_path: posts_media/2023-01-07-posts/
---

## Giới thiệu về thuật toán Gradient Descent (GD)
Thông thường, các thuật toán machine learning (ML) sẽ sử dụng các attributes hay còn gọi là features trong dataset để học và dự đoán output $y$. Tuy nhiên, có thể một vài features thể hiện nhiều thông tin hơn so với các features khác. Ví dụ như giá nhà chủ yếu dựa vào features về khoảng cách so với trung tâm, nhà trong ngõ hay mặt đường, vv. Rõ ràng, ta phải sắp xếp mức độ quan trọng của từng feature sao cho ML model hiểu và tập trung vào học các features đó. Từ đó sinh ra khái niệm weights of features, weight lớn đồng nghĩa với feature đó quan trọng. 

> Câu hỏi đặt ra là làm sao tìm được optimal weights sao cho ML model có thể dự đoán được chính xác output nhất. Gradient descent được sinh ra để giải quyết vấn đề này.
{: .prompt-info }

Gradient descent (GD) là thuật toán tối ưu nhằm tìm kiếm optimal weights của các features cho ML model. Hiểu cơ bản, đầu tiên ta chọn ngẫu nhiên weight cho các features, predict output, tính loss bằng cách so sánh giá trị predict với actual, và cuối cùng là update weight bằng cách tính đạo hàm riêng của từng weight với loss. Loss càng nhỏ càng chứng tỏ là ML model predict càng gần với actual. Có nhiều phương pháp tính loss, tiêu biểu là Mean square error (MSE):

$$
{\displaystyle \operatorname {MSE} ={\frac {1}{n}}\sum _{i=1}^{n}\left(Y_{i}-{\hat {Y_{i}}}\right)^{2}}
$$

Trong đó, $n$ là số lượng sample dùng để tính loss, $\hat{Y}_i$ là giá trị predict cho sample $i$. $\hat{Y}_i$ có thể được tính bởi công thức:

$$
\hat{Y}_i = \beta + \theta X_i
$$

Trong đó, $\beta$ là bias cho model, $\theta$ là weight vector cho từng feature của input $X_i$

![gradient-descent](gradient-descent.png)