# Tóm Tắt Kiến Thức Xác Suất Thống Kê

Tài liệu tổng hợp các công thức, định nghĩa và quy tắc quyết định trong môn Xác suất Thống kê.
## 1. Ước Lượng Tham Số

### Ước lượng điểm và tính chất
* **Ước lượng không chệch**: Thống kê $\hat{\theta}$ của mẫu là ước lượng không chệch cho tham số $\theta$ khi $E(\hat{\theta}) = \theta$.
  * Trung bình mẫu ($\bar{X}$) là ước lượng không chệch của trung bình tổng thể ($\mu$).
  * Tần suất mẫu ($f$) là ước lượng không chệch của tần suất tổng thể ($p$).
  * Phương sai mẫu hiệu chỉnh ($s^2$) là ước lượng không chệch của phương sai tổng thể ($\sigma^2$).
* **Ước lượng hợp lý tối đa**: $\hat{\theta}$ là ước lượng điểm hợp lý tối đa của tham số $\theta$ khi $\hat{\theta}$ là giá trị mà tại đó hàm hợp lý đạt cực đại.
* **Ước lượng vững**: Khi $\hat{\theta}$ hội tụ theo xác suất đến tham số $\theta$ khi $n \to \infty$ ($\hat{\theta} \xrightarrow{P} \theta$).

### Khoảng tin cậy (KTC)
* **$(G_1, G_2)$**: Khoảng tin cậy ngẫu nhiên (khi các giới hạn là các biến ngẫu nhiên).
* **$(g_1, g_2)$**: Khoảng tin cậy cụ thể (khi đã thay số liệu mẫu cụ thể).

## 2. Các Phân Phối Xác Suất Đặc Biệt

### Phân phối đều (Uniform Distribution)
Cho biến ngẫu nhiên $X \sim U(a, b)$ với $a, b$ lần lượt là giá trị nhỏ nhất (min) và lớn nhất (max):
* **Kỳ vọng**: $E(X) = \frac{a+b}{2}$
* **Phương sai**: $V(X) = \frac{(b-a)^2}{12}$
* **Xác suất**: $P(c < X < d) = \frac{d-c}{b-a}$ (với $a \le c < d \le b$)

### Phân phối Poisson
Cho biến ngẫu nhiên $X \sim P(\lambda)$:
* **Công thức**: $P(X = a) = \frac{e^{-\lambda} \cdot \lambda^a}{a!}$

## 3. Biến Ngẫu Nhiên Liên Tục

### Tính chất của hàm mật độ $f(x)$ và hàm phân phối $F(X)$
* $f(x) \ge 0$ với mọi $x$.
* $\int_{-\infty}^{+\infty} f(x) dx = 1$
* $F(X) = \int_{-\infty}^{x} f(t) dt$

### Các đặc trưng số (trong đoạn $[a, b]$)
* **Kỳ vọng**: $E(X) = \int_{a}^{b} x \cdot f(x) dx$
* **Phương sai**: $V(X) = \int_{a}^{b} x^2 \cdot f(x) dx - [E(X)]^2$

## 4. Mối Quan Hệ Giữa Các Biến Cố

* **Tính xung khắc**: Nếu $P(AB) \neq 0 \Rightarrow$ Hai biến cố **không** xung khắc.
* **Tính độc lập**: Nếu $P(AB) = P(A) \cdot P(B) \Rightarrow$ Hai biến cố độc lập.
* **Lưu ý định lý**: Khi $A$ và $B$ là hai biến cố có xác suất dương ($P(A)>0, P(B)>0$), chúng **không thể** vừa xung khắc vừa phụ thuộc nhau.
* **Biến cố đối ngẫu**: $P(\bar{A} \cdot \bar{B}) = 1 - P(A + B)$

## 5. Kiểm Định Giả Thuyết Thống Kê

### Giá trị chuẩn hóa và Tham số mẫu
* **Giá trị chuẩn hóa**: $Z = \frac{\bar{X} - \mu}{\sigma / \sqrt{n}}$
* **Phân phối của trung bình mẫu**: Có phương sai bằng phương sai tổng thể chia cho $n$ ($\sigma^2_{\bar{X}} = \frac{\sigma^2}{n}$).
* **Tần suất mẫu**: Có kỳ vọng $E(f) = p$ và phương sai $V(f) = \frac{p(1-p)}{n}$.

### Quy tắc quyết định theo P-value
* $P\text{-value} > \alpha \Rightarrow$ Chưa có cơ sở bác bỏ $H_0$.
* $P\text{-value} < \alpha \Rightarrow$ Bác bỏ $H_0$, chấp nhận $H_1$.

### Lựa chọn loại P-value và Trình tự kiểm định
* **Kiểm định 2 phía** (khác nhau $\neq$): Dùng $P_{\text{2-tail}}$.
* **Kiểm định 1 phía** ($>$ hoặc $<$): Dùng $P_{\text{1-tail}}$.
* **Công thức tính nhanh**: $P_{\text{1-tail}} = 1 - \Phi(|Z_{qs}|)$ (với $\Phi$ là hàm phân phối chuẩn Laplace).
* **Bảng gộp F-test và T-test**: Luôn tính toán kiểm định $F$ trước, sau đó mới tính kiểm định $T$.

### Điều kiện bác bỏ $H_0$ dựa trên giá trị quan sát (Miền bác bỏ $W_{qs}$)
1. $T_{qs} \in W_{qs}$: Dùng khi chưa biết phương sai tổng thể và cỡ mẫu nhỏ.
2. $F_{qs} \in W_{qs}$: Dùng khi so sánh 2 phương sai tổng thể (F-test).
3. $\chi^2_{qs} \in W_{qs}$ (Khi bình phương): Dùng khi kiểm định phương sai hoặc kiểm định tính độc lập.
4. $Z_{qs} \in W_{qs}$: Dùng khi kiểm định về giá trị trung bình và đã biết phương sai tổng thể.

### Bài toán ANOVA (Phân tích phương sai)
* Đặt giả thuyết:
  * $H_0$: Nhân tố không có tác động đến chỉ tiêu nghiên cứu.
  * $H_1$: Nhân tố có tác động đến chỉ tiêu nghiên cứu

## 6. Sai Lầm Trong Kiểm Định

| Loại sai lầm | Bản chất | Xác suất mắc phải | Điều kiện xảy ra |
| :--- | :--- | :--- | :--- |
| **Sai lầm loại 1** | Bác bỏ $H_0$ khi $H_0$ đang **Đúng** | $\alpha$ (Mức ý nghĩa) | Giá trị quan sát $T_{qs}$ thuộc miền bác bỏ $W_{qs}$ |
| **Sai lầm loại 2** | Chưa bác bỏ $H_0$ khi $H_0$ đang **Sai** | $\beta$ | $T_{qs} \notin W_{qs}$ hoặc $P\text{-value} > \alpha$ |
