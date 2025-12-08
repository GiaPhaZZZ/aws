---
title: "Blog 1"
date: 2025-09-12
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

# Khám Phá Quantum Measurements, Observables và Operators: Góc nhìn thực tiễn với Amazon Braket

Sudarsan Srinivasan và Charunethran Panchalam Govindarajan
| 12 THÁNG 9 2025 | Amazon Braket, Quantum Technologies |


## Giới Thiệu

Trong bài viết này, chúng ta sẽ lần lượt khai mở nền tảng toán học và ứng dụng thực tế của các kỹ thuật quantum measurement bằng Amazon Braket.
Cùng nhau xem xét đề tài qua nhiều góc nhìn, chẳng hạn: dùng action of gates như một basis transformation, projection như inner product, projector formalism và observable formalism.
Điểm quan trọng mà chúng ta đang muốn hướng đến đó là hiểu được basis transformations như một công cụ cho việc chuyển đổi phase information thành amplitude information – khái niệm trọng tâm của nhiều thuật toán lượng tử.

Mục tiêu của bài viết này là cung cấp cái nhìn trực quan cùng các ý tưởng có thể triển khai cho những ai đang muốn tìm tòi học hỏi nhằm hiểu rõ hơn về các kỹ thuật quantum measurement.

![](/images/3-TranslatedBlogs/blog1/fig2.jpg)


## Superposition và Measurement trong Arbitrary Basis

Một one-qubit state tổng quát có thể được viết dưới dạng tổng hợp trong cơ sở tính toán { |0⟩, |1⟩ }:

$$
|ψ⟩ = α_0|0⟩ + α_1|1⟩
$$

trong đó α₀ và α₁ là các biên độ xác suất thỏa mãn:

$$
|α_0|^2 + |α_1|^2 = 1
$$

Các biên độ này đo lường độ projection (hoặc độ trùng lặp) của trạng thái lên các basis vectors.

Quantum measurement xác định mức độ projection của trạng thái lên cơ sở đo lường. Giờ hãy cùng xem xét việc đo lường trạng thái này trong một orthonormal basis khác { |u_0⟩, |u_1⟩ }.
Để biểu diễn trạng thái trong arbitrary basis này dưới dạng:

$$
|ψ⟩ = β_0|u_0⟩ + β_1|u_1⟩
$$

chúng ta cần tìm các hệ số β₀ và β₁.

Xem xét ma trận đơn vị U với { |u_0⟩, |u_1⟩ } là các cột:

$$
U = [|u_0⟩ \ |u_1⟩]
$$

Để tìm β₀ và β₁ trong:

$$
|ψ⟩ = β_0|u_0⟩ + β_1|u_1⟩,
$$

chúng ta biểu diễn các basis vectors mới theo cơ sở tính toán.
Lưu ý rằng:

$$
U|0⟩ = |u_0⟩, \quad U|1⟩ = |u_1⟩
$$

Khi đó:

$$
|ψ⟩ = β_0U|0⟩ + β_1U|1⟩ = U(β_0|0⟩ + β_1|1⟩)
$$

Vì U là phép biến đổi đơn vị, áp dụng U† cho cả hai bên cho kết quả:

$$
U†|ψ⟩ = β_0|0⟩ + β_1|1⟩
$$

Các hệ số β₀ và β₁ là các projection của U†|ψ⟩ lên các trạng thái cơ sở tính toán.
Do đó, đo U†|ψ⟩ trong cơ sở tính toán cho kết quả tương tự như đo trạng thái ban đầu |ψ⟩ trong cơ sở { |u_0⟩, |u_1⟩ }.

Nguyên lý này mở rộng tự nhiên cho n-qubit system.
Hệ thống n-qubit tồn tại trong không gian Hilbert có chiều N = 2^n (với 2^n basis vectors). Trong cơ sở tính toán, 2^n basis vectors này được biểu diễn bằng các chuỗi nhị phân từ 0 đến 2^(n - 1): |00…0⟩, |00…1⟩, …, |11…1⟩.

Một trạng thái tổng quát |ψ⟩ có thể được biểu diễn trong cơ sở tính toán dưới dạng:

$$
|ψ⟩ = α_0|00…0⟩ + α_1|00…1⟩ + … + α_{N-1}|11…1⟩ = \sum_k α_k|k⟩
$$

trong đó 0 ≤ k ≤ 2^n - 1 và:

$$
\sum_k |α_k|^2 = 1
$$

Giả sử bây giờ chúng ta muốn đo trạng thái này trong bất kỳ arbitrary orthonormal basis nào { |u_0⟩, |u_1⟩, …, |u_k⟩, …, |u_{N-1}⟩ }.
Khi đo |ψ⟩ trong basis này, chúng ta thực chất đang hỏi: “Xác suất tìm thấy hệ thống ở trạng thái |u_k⟩ là bao nhiêu?”

Trạng thái |ψ⟩ có thể được biểu diễn trong basis này như sau:

$$
|ψ⟩ = β_0|u_0⟩ + β_1|u_1⟩ + … + β_{N-1}|u_{N-1}⟩
$$

trong đó β_k = ⟨u_k|ψ⟩ là biên độ của trạng thái được chiếu lên cơ sở |u_k⟩.

Như trước đây, nếu U là ma trận đơn vị có các cột là { |u_0⟩, |u_1⟩, …, |u_{N-1}⟩ }, thì:

$$
U†|ψ⟩ = \sum_k β_k|k⟩ = β_0|00…0⟩ + β_1|00…1⟩ + … + β_{N-1}|11…1⟩
$$

Đo trạng thái |ψ⟩ trong basis { |u_k⟩ } tương đương với áp dụng U† lên trạng thái và đo trong cơ sở tính toán.

Ngược lại, giả sử V là bất kỳ phép toán đơn vị (quantum gate) nào. Khi áp dụng cổng V lên trạng thái |ψ⟩ và đo kết quả V|ψ⟩ trong cơ sở tính toán, điều này tương đương với việc đo trạng thái ban đầu |ψ⟩ trong basis được hình thành bởi các cột của V†.

Đây là một nguyên lý quan trọng của quantum measurement.
Các thiết bị vật lý cho phép thực hiện phép đo trong Z basis (cơ sở tính toán).
Khái niệm về phép đo trong một cơ sở khác được thực hiện thông qua một biến đổi đơn vị tương đương.

Hãy cùng suy ngẫm điều này qua ví dụ. Trong sơ đồ sau (hình 1), trạng thái lượng tử của một qubit duy nhất |\ψ⟩ được biểu diễn trong không gian vectơ 2D thực (với các biên độ xác suất là số thực).

{{< figure 
    src="/images/3-TranslatedBlogs/blog1/fig1.png" 
    caption="**Hình 1:** Biểu diễn trạng thái theo các basis khác nhau trên mặt phẳng 2D thực. |0⟩ và |1⟩ đại diện cho cơ sở tính toán, trong khi |u_0⟩ và |u_1⟩ đại diện cho bất kỳ arbitrary basis nào. |\ψ⟩ đại diện cho trạng thái của một qubit duy nhất. Các phép chiếu của trạng thái lên mỗi basis vectors là inner products của trạng thái đó với các basis vectors tương ứng.."
>}}

Xem xét vectơ trạng thái |\ψ⟩ được định hướng ở góc π/6 (30°) từ |0⟩.
Sau đó, trạng thái có thể được biểu diễn trong cơ sở tính toán như sau:

$$
|\psi⟩ = \cos(\pi/6)|0⟩ + \sin(\pi/6)|1⟩ = \frac{\sqrt{3}}{2}|0⟩ + \frac{1}{2}|1⟩
$$

Trong cơ sở tính toán { |0⟩, |1⟩ }:

* Xác suất đo được |0⟩: ( | cos(π/6)|^2 = 3/4 = 75% )
* Xác suất đo được |1⟩: ( | sin(π/6)|^2 = 1/4 = 25% )

Giờ hãy xem xét việc đo trạng thái này trong một arbitrary orthonormal basis { |u_0⟩, |u_1⟩ } nằm ở góc π/8 (22,5°) so với cơ sở tính toán { |0⟩, |1⟩ }:

$$
|u_0⟩ = \cos(\pi/8)|0⟩ + \sin(\pi/8)|1⟩
$$

$$
|u_1⟩ = -\sin(\pi/8)|0⟩ + \cos(\pi/8)|1⟩
$$

Kết quả đo lường sẽ phụ thuộc vào phép chiếu của trạng thái |\ψ⟩ lên các basis vectors này.

Như đã phân tích, chúng ta có thể thấy rằng:

$$
|\psi⟩ = \cos(\pi/24)|u_0⟩ + \sin(\pi/24)|u_1⟩
$$

Trong arbitrary orthonormal basis { |u_0⟩, |u_1⟩ }:

* Xác suất đo được |u_0⟩: ( | cos(π/24)|^2 ~ 0.983 = 98.3% )
* Xác suất đo được |u_1⟩: ( | sin(π/24)|^2 ~ 0.017 = 1.7% )

## Ghi chú về biểu diễn trên Bloch Sphere

Trên **Bloch Sphere**, các thông số góc là **gấp đôi** các góc vật lý trong không gian trạng thái. Một phép quay với góc θ trong không gian trạng thái tương ứng với phép quay với góc 2θ trên Bloch Sphere.
Điều này liên quan đến nhóm **SU(2)** là một **lớp phủ kép** của **SO(3)** (xem các tài liệu tham khảo để biết chi tiết).

Hãy xem điều này bằng cách sử dụng **Amazon Braket**.

Như được thể hiện trong đoạn code dưới đây, trước tiên, chúng ta tạo một **instance của Local Simulator** và một **Circuit**.
Amazon Braket khởi tạo các qubit trong trạng thái |0⟩ (hướng theo trục Z của Bloch Sphere).
Sau đó, chúng ta xoay trạng thái với góc 30° (π/6) theo trục Y.
Lưu ý rằng một vòng xoay vật lý (π/6) tương ứng với một vòng xoay (π/3) trên hình Bloch Sphere.

Trạng thái qubit nằm trong mặt phẳng XZ của Bloch Sphere. Điều này tương ứng với biểu diễn trong **Hình 1**.

Chúng ta tạo ra hai vectơ **u_0** và **u_1** để biểu thị cơ sở đo lường mà chúng ta quan tâm.
Dễ dàng nhận thấy rằng hai vectơ này vuông góc với nhau (inner product bằng 0).
Sau đó, chúng ta tạo ra một **ma trận** với hai vectơ này làm **cột**.
Đối với các chiều cao hơn, mô hình tương tự được áp dụng.

Tiếp theo, chúng ta lấy **ma trận đối ngẫu** của ma trận này – do tình huống của chúng ta sử dụng giá trị thực, ta lấy **ma trận chuyển vị** của ma trận này (điều này tương đương với ma trận đối ngẫu).
Ma trận kết quả cũng sẽ là **ma trận đơn vị**.

Toán tử đơn vị này sau đó được áp dụng cho trạng thái (**Circuit object**) bằng phương thức `Circuit.unitary`.
Sau đó, chúng ta đo trạng thái trong **cơ sở tính toán**.
Lưu ý rằng phương pháp đo lường trong Amazon Braket mặc định được thực hiện trên **cơ sở tính toán**.


### Code: Đo lường trong arbitrary basis

```python
import numpy as np
from braket.circuits import Circuit
from braket.devices import LocalSimulator

device = LocalSimulator()
circuit = Circuit()

# Số lượng qubit trong Braket được khởi tạo ở trạng thái |0⟩ và thẳng hàng với trục Z.
# Sau đó, ta xoay qubit quanh trục Y một góc (tính bằng radian).
# Mặc dù ta biết rõ hướng và trạng thái chính xác của qubit,
# nhưng trong ví dụ này ta sẽ giả vờ như không biết và tìm cách xác định trạng thái đó
# thông qua các phép đo — đây chính là mục đích của ví dụ này.

state_angle = np.pi / 3
circuit.ry(0, state_angle)

# Định nghĩa một vector cơ sở có góc lệch là π/8 so với cơ sở tính toán |0⟩
u_0 = np.array([[np.cos(np.pi/8)], [np.sin(np.pi/8)]])

# Định nghĩa một vector cơ sở khác có góc lệch là π/8 so với cơ sở tính toán |1⟩
u_1 = np.array([[-np.sin(np.pi/8)], [np.cos(np.pi/8)]])

# Tạo một ma trận mà các cột của nó là các vector cơ sở dùng để đo
matrix_formed_from_basis_vectors = np.hstack((u_0, u_1))

# Cổng đơn vị (unitary gate) là phép liên hợp (adjoint) của ma trận vừa tạo
# Với ma trận thực, phép liên hợp (adjoint) chính là chuyển vị (transpose)
basis_rotation_gate = matrix_formed_from_basis_vectors.T

# Áp dụng cổng đơn vị này vào mạch lượng tử — về bản chất, đây là một phép quay hệ tọa độ
circuit.unitary(matrix=basis_rotation_gate, targets=[0])
circuit.probability(target=0)

task = device.run(circuit, shots=1000)
taskResult = task.result()

measurement_probabilties = taskResult.values[0]
counts = taskResult.measurement_counts

print("Probability : ", measurement_probabilties)
print("Counts : ", counts)
```

Khi chạy đoạn code trên, bạn sẽ nhận được kết quả tương tự như sau
(lưu ý rằng bạn có thể nhận được một con số hơi khác, nhưng kết quả sẽ gần và có xu hướng tiến tới giá trị này):

```python
Probability :  [0.983 0.017]
Counts :  Counter({'0': 983, '1': 17})
```

Kết quả này trùng khớp với các giá trị được tính toán trước đó.


## Tại sao lại đo lường trên một basis khác?

Các cơ sở đo lường khác nhau tiết lộ các khía cạnh bổ sung của quantum states. Sự bổ sung này xuất phát từ bản chất xác suất của  quantum measurement: chúng ta quan sát các kết quả với xác suất cụ thể thông qua quy tắc Born, chứ không phải các biên độ phức tạp cơ bản trực tiếp.

Xem xét một trạng thái tổng quát |ψ⟩ = α|0⟩ + β|1⟩, trong đó α và β là các số phức. Đo lường trong cơ sở tính toán tiết lộ |α|² và |β|² (xác suất của các kết quả |0⟩ và |1⟩), nhưng không tiết lộ pha tương đối giữa α và β. Thông tin pha này vẫn được mã hóa trong quantum state và không thể truy cập thông qua các phép đo trong basis đó. Các trạng thái chỉ khác nhau về pha tương đối sẽ cho ra thống kê đo lường giống hệt nhau trong basis đó, mặc dù chúng là các quantum states khác nhau.

Ví dụ: Truy Cập Thông Tin Pha Ẩn

Xét |+⟩ = (|0⟩ + |1⟩)/ √2 và |−⟩ = (|0⟩ − |1⟩)/ √2. Các trạng thái này chỉ khác nhau ở pha tương đối giữa các thành phần |0⟩ và |1⟩ của chúng. Đáng chú ý, mặc dù cả hai đều là các trạng thái chồng chập bằng nhau, |+⟩ và |−⟩ là các orthogonal states — tức là có thể phân biệt tối đa với nhau như |0⟩ và |1⟩.

Trong các phép đo cơ sở tính toán, cả hai trạng thái đều cho kết quả 50% |0⟩ và 50% |1⟩. Mối quan hệ pha ± không thể quan sát được. Tuy nhiên, trong cơ sở {|+⟩, |−⟩}, |+⟩ luôn cho kết quả |+⟩ và |−⟩ luôn cho kết quả |−⟩ (cả hai đều với xác suất = 1). Thông tin pha trở nên có thể quan sát trực tiếp.

Điều này minh họa tính bổ sung trong đo lường lượng tử: việc mô tả đầy đủ một trạng thái lượng tử yêu cầu thực hiện đo lường trong nhiều cơ sở không tương thích — các cơ sở mà các toán tử đo lường của chúng không giao hoán, ngăn cản việc đo lường chính xác đồng thời. Mỗi cơ sở đo lường truy cập vào thông tin lượng tử cụ thể trong khi làm cho các khía cạnh khác không thể quan sát được.

## Làm cách nào sự thay đổi của basis tiết lộ các khía cạnh của quantum information?

Hãy quay lại với nguyên lý đo lường. Xác suất của kết quả phụ thuộc vào phép chiếu của trạng thái lượng tử lên các trạng thái basis (vectơ hoặc không gian con). Điều này có thể được hình dung rõ ràng hơn trong trường hợp 1 qubit trên Bloch sphere. Một trạng thái tùy ý là một điểm trên Bloch sphere và phép chiếu của trạng thái đó lên trục Z xác định xác suất trạng thái đó cho ra trạng thái |0⟩ hoặc |1⟩ khi đo lường. Các trạng thái nằm trên cùng một vĩ độ có cùng giá trị xác suất. Các điểm khác nhau trên quả cầu Bloch ở cùng một vĩ độ chỉ khác nhau về pha tương đối.

Khi chúng ta đo trạng thái từ các basis khác nhau, chúng ta đang tìm hiểu về hình chiếu của cùng một vectơ trạng thái lên một vectơ hoặc hướng khác với cơ sở tính toán. Các trạng thái chỉ khác nhau về pha so với cơ sở tính toán (và có cùng hình chiếu trên trục Z) sẽ có hình chiếu khác nhau trên cơ sở đo lường / trục khác với cơ sở tính toán.

Lấy một ví dụ minh họa, hãy xem xét hai thành phố trên một quả địa cầu có cùng vĩ độ. Chúng sẽ có cùng một hình chiếu dọc theo trục bắc-nam, nhưng nếu chúng ta xoay và định hướng lại quả địa cầu theo trục xích đạo, những thành phố này sẽ có các hình chiếu khác nhau dọc theo trục mới này.

Điểm mấu chốt là những gì xuất hiện dưới dạng “phase” trong cơ sở tính toán sẽ thể hiện dưới dạng “amplitude” trong một cơ sở khác. Vì amplitude quyết định kết quả đo lường, việc biến đổi cơ sở có thể được xem như cơ chế cho phép sự chuyển đổi từ phase sang amplitude.

Đây là lý do tại sao Hadamard transform đóng vai trò quan trọng trong các thuật toán lượng tử. Như chúng ta đã thấy trong phần trước, bất kỳ biến đổi đơn vị (như Hadamard) nào cũng có thể được xem và giải thích như một basis transformation (xoay tọa độ). Biến đổi Hadamard thay đổi góc nhìn của cơ sở tính toán { |0⟩, |1⟩ } sang góc nhìn { |+⟩, |−⟩ }. Thông tin được mã hóa trong pha (trong các thuật toán như Simon’s, Shor’s và bất kỳ quy trình phụ thuộc vào phản hồi pha nào) sử dụng phương pháp biến đổi cơ sở để phát hiện mẫu trong thông tin lượng tử.

Chúng ta có thể rút ra một số điểm chính từ phân tích này:

* Lựa chọn cơ sở đo lường cung cấp cho chúng ta những góc nhìn duy nhất mà có thể không có sẵn từ một cơ sở khác; và chúng ta không thể có được tất cả các góc nhìn cùng một lúc. Một độ chắc chắn cao hơn trong phép đo ở một tập cơ sở có thể dẫn đến độ không chắc chắn cao hơn trong cơ sở tương ứng từ một tập khác.
* Chúng ta có thể giải thích hoạt động của ma trận Unitary trên một trạng thái theo hai cách – hoặc là ma trận Unitary thay đổi trạng thái của hệ thống, hoặc là biến đổi cơ sở cho phép phép đo (hoặc góc nhìn) trên qubit từ một hệ tọa độ khác.


## Công thức projector để đo trạng thái trong một arbitrary basis

Trong cơ học lượng tử, các phép đo vật lý được mô tả bằng các Observables. Phép đo này nhằm xác định lượng trạng thái lượng tử “chiếu lên” mỗi basis vector. Khái niệm này được thể hiện thông qua khái niệm các phép chiếu, đóng vai trò là các khối xây dựng cơ bản cho việc hiểu những phép đo sử dụng các Observables.

Chúng ta đã thấy rằng xác suất của trạng thái |ψ⟩, khi được đo trong một arbitrary basis { |u₀⟩, |u₁⟩, …, |u_k⟩, …, |u_{N−1}⟩ }, được quan sát trong trạng thái |u_k⟩ là

$$
|\langle u_k | ψ \rangle|^2 = \langle u_k | ψ \rangle \langle u_k | ψ \rangle^* = \langle u_k | ψ \rangle \langle ψ | u_k \rangle = \langle ψ | u_k \rangle \langle u_k | ψ \rangle
$$

Biểu thức tích ngoài |u_k⟩⟨u_k| được gọi là phép chiếu cho basis state |u_k⟩. Hãy ký hiệu nó bằng P_k. Do đó, xác suất thu được trạng thái kết quả |u_k⟩ khi |ψ⟩ được đo trong cơ sở { |u₀⟩, |u₁⟩, …, |u_k⟩, …, |u_{N−1}⟩ } là

$$
\langle ψ | P_k | ψ \rangle
$$

Phép chiếu P_k có thể được hiểu là một phép toán trích xuất thành phần của |ψ⟩ nằm dọc theo hướng |u_k⟩:

$$
P_k | ψ \rangle = |u_k⟩ \langle u_k | ψ \rangle
$$

⟨u_k|ψ⟩ là biên độ phức tạp đo lường sự “trùng lặp” giữa |ψ⟩ và |u_k⟩, và P_k|ψ⟩ nhân |u_k⟩ với biên độ này, cho ra thành phần của |ψ⟩ nằm dọc theo |u_k⟩.

Các phép chiếu có thể được xem là các khối xây dựng cơ bản của các đại lượng quantum observables. Hành động của một phép chiếu đại diện cho loại đo lường cơ bản nhất trong cơ học lượng tử. Một phép chiếu P đặt ra câu hỏi cơ bản (“có”/“không”): “Hệ thống có ở trạng thái được định nghĩa bởi phép chiếu không?”. Chúng ta sẽ nhận được câu trả lời “Có” với xác suất

$$
\langle ψ | P | ψ \rangle
$$

Projectors là các toán tử Hermitian có các giá trị riêng là 0 và 1. Chúng bảo toàn các thành phần trong không gian con đích (giá trị riêng 1) đồng thời loại bỏ các thành phần vuông góc (giá trị riêng 0).

## Từ Projectors đến Observables

Các phép chiếu trả lời các câu hỏi nhị phân “có/không” về trạng thái lượng tử trong một hướng hoặc không gian con cụ thể. Một Observable mở rộng khái niệm này bằng cách gán các giá trị số cho các kết quả đo lường khác nhau.

Một Observable về cơ bản là một cấu trúc đo lường trạng thái lượng tử trong cơ sở được xác định bởi các vectơ riêng của nó. Mỗi observable ngầm định một cơ sở đo lường – eigenbasis của nó – xác định “reference frame” mà trong đó trạng thái lượng tử được quan sát.

Cụ thể, một observable là tổng có trọng số của các projector vuông góc:

$$
A = \lambda_0 P_0 + \lambda_1 P_1 + \dots + \lambda_{n-1} P_{n-1}
$$

(Spectral Decomposition của một observable)

trong đó mỗi λᵢ là một eigenvalue và Pᵢ là phép chiếu lên không gian riêng tương ứng.

Khi đo lường một observable A trong trạng thái |ψ⟩, mỗi phép đo cho ra chính xác một trong các giá trị riêng λᵢ. Xác suất thu được λᵢ là

$$
\langle ψ | P_i | ψ \rangle
$$

Khi đo lường, trạng thái “collapses” thành một trạng thái mới:

$$
\frac{P_i | ψ \rangle}{\sqrt{\langle ψ | P_i | ψ \rangle}}
$$

Phần tử mẫu là hệ số chuẩn hóa để đáp ứng yêu cầu chuẩn hóa đơn vị của trạng thái lượng tử.

Nói cách khác, một đại lượng quan sát cung cấp một mô hình đo lường sử dụng các vectơ riêng của nó làm cơ sở đo lường và tạo ra các giá trị riêng làm kết quả đo lường.

Ví dụ: đo lường với đại lượng quan sát Pauli X tương đương với đo lường trong cơ sở {|+⟩, |−⟩}, và đo lường với Pauli Z chỉ đơn giản là đo lường trong cơ sở {|0⟩, |1⟩}. (|+⟩ và |−⟩ là các vectơ riêng của X, còn |0⟩ và |1⟩ là các vectơ riêng của Z).

Kết quả đo tuân theo phân phối xác suất được xác định bởi sự chiếu của trạng thái lượng tử lên từng không gian riêng.

Mỗi lần đo trên thiết bị (máy mô phỏng hoặc quantum hardware thực) đại diện cho một lần đo lường riêng lẻ, khiến trạng thái lượng tử sụp đổ vào một trong các không gian riêng đồng thời cho ra giá trị riêng tương ứng làm kết quả đo lường.

Giá trị kỳ vọng của một phép đo là tổng có trọng số của tất cả các lần đo lường. Cần nhấn mạnh rằng mỗi lần đo lường luôn cho ra một trong các giá trị riêng. Chúng ta không bao giờ thấy "giá trị kỳ vọng" trong bất kỳ quan sát cụ thể nào. Đây là giá trị trung bình thống kê được tính toán sau từ kết quả của các lần đo lường riêng lẻ.

Một projector operator có thể được xem là observable cơ bản nhất chỉ có một giá trị riêng và giá trị của nó là 1. Nói cách khác, nó là observable chỉ có một thành phần trong spectral decomposition của nó.

Một Observable, nói chung, cho giá trị kỳ vọng – đây là giá trị trung bình thống kê của các giá trị riêng mà chúng ta gán cho từng cơ sở đo lường (eigenstate – lưu ý rằng khi sử dụng một observable, chúng ta đang ngầm đo lường trạng thái trong vectơ riêng của observable). Một phép đo sử dụng phép chiếu cơ bản (như observable) sẽ cho xác suất trực tiếp – điều này là do giá trị riêng của phép chiếu là 1 và giá trị đơn vị này không ảnh hưởng đến thống kê của phép đo.


## Observable dưới dạng tổng của Pauli Terms

Theo nguyên tắc chung, bất kỳ toán tử Hermitian A nào có các vectơ riêng vuông góc đều có thể đóng vai trò là quantum observable, nơi các phép đo được chiếu lên các eigenstates này với các giá trị riêng tương ứng λᵢ.

Observable

$$
A = \sum_i \lambda_i |u_i⟩⟨u_i|
$$

đại diện cho phép đo hoàn chỉnh trong custom basis này.

Hầu hết các thiết bị lượng tử chỉ có thể thực hiện phép đo trong một cơ sở tính toán cố định duy nhất — Z-basis (|0⟩, |1⟩).

Các Quantum computing frameworks giải quyết vấn đề này thông qua quá trình phân tích hệ thống:

Bất kỳ toán tử Hermitian đơn qubit A nào cũng có thể được phân tích độc nhất thành:

$$
A = a_0 I + a_1 X + a_2 Y + a_3 Z
$$

Ở đây, aᵢ là các hệ số số thực và X, Y, Z là ba ma trận Pauli (Observables) cùng với ma trận đơn vị I.

![](/images/3-TranslatedBlogs/blog1/fig3.png)

Các phép đo Pauli sử dụng ma trận Pauli làm các Observables. Khi sử dụng một phép toán Hermitian tùy chỉnh làm Observables, Amazon Braket phân tích nó thành tổ hợp tuyến tính của các đại lượng quan sát Pauli.

Mỗi phép đo Pauli có thể được tái diễn giải thông qua các phép đo cơ sở tính toán Pauli-Z bằng cách sử dụng các phép basis rotations thích hợp, hoàn thành việc chuyển đổi từ các phép đo arbitrary sang các phép toán có thể thực hiện được về mặt vật lý.

Phép đo Pauli X được thực hiện bằng cách áp dụng cổng Hadamard (H) trước phép đo Z basis; phép đo Pauli Y được thực hiện bằng cách áp dụng S† (phase gate) trước, sau đó là Hadamard gate và cuối cùng là phép đo Z basis.

![](/images/3-TranslatedBlogs/blog1/fig4.png)

## Đo lường trong arbitrary basis bằng cách sử dụng Observable của Amazon Braket

Đoạn code sau minh họa việc sử dụng một phép chiếu để đo trạng thái của hệ thống trong basis { |u_0⟩, |u_1⟩ } như ví dụ trước.

Đầu tiên, chúng ta định nghĩa một phương thức để tạo phép chiếu, dựa trên một basis vector. Phép chiếu ở dạng cơ bản nhất là **outer product** của basis vector với chính nó. Projector này cho xác suất trạng thái được quan sát trong basis được định nghĩa bởi vectơ được sử dụng để tạo ra nó.

Chúng ta định nghĩa hai basis vectors như trước đây và xây dựng các toán tử projector cho chúng. Như đã từng làm, chúng ta khởi tạo và xoay state vector bằng cổng RY. Sau đó, chúng ta sử dụng phương thức `expectation` trên Circuit để chỉ định các observable quan tâm – trong trường hợp này là hai projector.

Một điểm cần lưu ý là trong Braket, chúng ta chỉ có thể áp dụng một observable duy nhất không phải là hằng số cho mỗi qubit (trừ khi shots được đặt là 0). Để minh họa tác động của cả hai phép chiếu (mỗi phép chiếu là một đại lượng quan sát) tương ứng với hai basis vectors, chúng ta đặt `shots=0` ở đây, mặc dù chúng ta có thể đặt shots không bằng 0 cho từng phép chiếu riêng lẻ để xem kết quả đó.

### Code: Sử dụng Projector làm Observable cho đo đạc trong arbitrary basis

```python
import numpy as np
from braket.circuits import Circuit
from braket.devices import LocalSimulator
from braket.circuits import observables

# Projector là toán tử Hermitian được tạo bằng tích ngoài (outer product) của một vector với chính nó. 
# Một projector như vậy là một observable cơ bản
def get_projector(basis_vector):
    projector = np.linalg.outer(basis_vector, basis_vector)
    return observables.Hermitian(projector)

# Định nghĩa một vector cơ sở có hướng lệch là π/8 so với cơ sở tính toán |0⟩.
basis_u0 = np.array([np.cos(np.pi/8), np.sin(np.pi/8)])

# Định nghĩa một vector cơ sở có hướng lệch là π/8 so với cơ sở tính toán |1⟩. 
# Cơ sở này trực chuẩn (orthonormal) với basis_u0. 
basis_u1 = np.array([-np.sin(np.pi/8), np.cos(np.pi/8)])

# Tạo projector cho (basis) vector thứ nhất
projector_u0 = get_projector(basis_u0)

# Tạo projector cho (basis) vector thứ hai
projector_u1 = get_projector(basis_u1)

circ = Circuit()
device = LocalSimulator()

# Các qubit trong Braket được khởi tạo ở trạng thái |0⟩ và thẳng hàng với trục Z. 
# Xoay qubit quanh trục Y một góc (tính bằng radian).
state_angle = np.pi / 3
circ.ry(0, state_angle)

# Giá trị kỳ vọng (expectation value) của một projector cho ta xác suất đo được trong cơ sở mà projector đó tạo ra — trong trường hợp này là u_0
circ.expectation(projector_u0)

# Giá trị kỳ vọng (expectation value) của projector khác cho ta xác suất đo được trong cơ sở u_1
circ.expectation(projector_u1)

# Chạy mạch
task = device.run(circ, shots=0)
taskResult = task.result()

counts = taskResult.measurement_counts
probability_u0 = taskResult.values[0]
probability_u1 = taskResult.values[1]

print("Probability that state is in basis u_0 : ", np.round(probability_u0, 4))
print("Probability that state is in basis u_1 : ", np.round(probability_u1, 4))
```

Kết quả khi chạy đoạn code trên:

```python
Probability that state is in basis u_0 :  [0.983]
Probability that state is in basis u_1 :  [0.017]
```

Do đó, chúng ta thấy rằng các xác suất thu được từ phương pháp biểu diễn bằng phép chiếu trùng khớp với các giá trị từ phép xoay tọa độ (sử dụng các cổng đơn vị).
Về mặt toán học, hai phương pháp này là tương đương. Việc sử dụng phương pháp này hay phương pháp kia phụ thuộc vào perspective và intuition mà chúng ta muốn áp dụng.

## Tổng Kết

Quantum measurement liên quan đến việc chiếu các trạng thái lượng tử lên các bases khác nhau, cho ra các kết quả xác suất mô tả hệ thống.
Chúng ta đã thấy rằng việc đo lường trong một arbitrary basis về mặt toán học tương đương với việc áp dụng một phép quay đơn vị tiếp theo là đo lường trong cơ sở tính toán.
Sau đó, chúng ta đã khám phá cách chuyển đổi cơ sở này hoạt động như một công cụ để chuyển đổi thông tin pha không quan sát được thành thông tin biên độ có thể đo lường được.
Chúng ta đã xem xét các phép chiếu như các observables cơ bản, lưu ý vai trò của chúng trong việc đo lường xác suất trạng thái trong các cơ sở cụ thể.
Cuối cùng, chúng ta đã xem xét cách các observables tổng quát có thể được phân tích thành các toán tử Pauli, tạo nền tảng cho quantum measurement trong Amazon Braket.

Tài liệu tham khảo

“Bloch Sphere.” Wikipedia, [https://en.wikipedia.org/wiki/Bloch_sphere](https://en.wikipedia.org/wiki/Bloch_sphere). Truy cập [20/8/2025].

“Pauli matrices.” Wikipedia, [https://en.wikipedia.org/wiki/Pauli_matrices](https://en.wikipedia.org/wiki/Pauli_matrices). Truy cập [20/7/2025].

Townsend, J. S. (2012). *A Modern Approach to Quantum Mechanics* (2nd ed.). University Science Books, Chapter 2: Rotation of Basis States and Matrix Mechanics.

---

TAGS: Amazon Braket , quantum algorithms , quantum computing , Quantum Technologies

---

* Sudarsan Srinivasan

Sudarsan Srinivasan là Senior Solutions Architect tại AWS. Anh có niềm đam mê đặc biệt với Vật lý, Toán học và Triết học, điều này đã dẫn anh đến lĩnh vực Quantum Computing. Sudarsan có kinh nghiệm trong lĩnh vực kiến trúc doanh nghiệp và kiến trúc giải pháp, với chuyên môn về thiết kế khả năng phục hồi và hiện đại hóa ứng dụng.

* Charunethran Panchalam Govindarajan

Charunethran Panchalam Govindarajan là Sr. Product Marketing Manager tại AWS, chuyên về High-Performance Computing and Quantum Technologies. Anh đã làm việc trong nhiều lĩnh vực công nghệ khác nhau, với sự quan tâm chính vào sự giao thoa giữa nghiên cứu và phát triển (R&D) và phát triển sản phẩm. Charunethran có bằng Thạc sĩ Electrical Engineering từ Đại học Stanford. Ngoài công việc, anh thích vẽ phác thảo và tham gia vào các cuộc trò chuyện triết học.
