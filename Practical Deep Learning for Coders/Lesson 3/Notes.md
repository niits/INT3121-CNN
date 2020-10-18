# Câu trả lời cho các câu hỏi trong bài học

## Những chữ cái nào thường được sử dụng để ký hiệu các biến độc lập và các biến phụ thuộc

x là độc lập. y là phụ thuộc.

## Sự khác biệt giữa các phương pháp thay đổi kích thước crop, pad và squish là gì? Khi nào bạn có thể chọn một trong những thứ khác

crop là phương thức Resize () mặc định và nó cắt các hình ảnh để vừa với hình vuông có kích thước được yêu cầu, sử dụng toàn bộ chiều rộng hoặc chiều cao. Điều này có thể làm mất một số chi tiết quan trọng. Ví dụ, nếu chúng ta đang cố gắng nhận ra giống chó hoặc mèo, chúng ta có thể sẽ cắt bỏ một phần chính của cơ thể hoặc khuôn mặt cần thiết để phân biệt giữa các giống chó tương tự.

pad là một phương thức Resize() khác, đặt ma trận các pixel của hình ảnh bằng các số không (hiển thị là màu đen khi xem hình ảnh). Nếu chúng ta chèn các hình ảnh thì chúng ta có rất nhiều không gian trống, điều này chỉ lãng phí tính toán cho mô hình của chúng ta và dẫn đến độ phân giải hiệu quả thấp hơn cho phần hình ảnh mà chúng ta thực sự sử dụng.

squish là một phương thức thay thế Resize () khác, có thể thu nhỏ hoặc kéo giãn hình ảnh. Điều này có thể khiến hình ảnh có shape không thực tế, dẫn đến mô hình học rằng mọi thứ trông khác với thực tế, thứ mà chúng ta mong đợi sẽ dẫn đến độ chính xác thấp hơn.

Do đó, sử dụng phương pháp thay đổi kích thước nào tùy thuộc vào vấn đề cơ bản và tập dữ liệu. Ví dụ: nếu các đặc trưng trong hình ảnh tập dữ liệu chiếm toàn bộ hình ảnh và việc cắt xén có thể dẫn đến mất thông tin, việc thu nhỏ hoặc đệm có thể hữu ích hơn.

Một phương pháp khác tốt hơn là RandomResizedCrop, trong đó chúng ta cắt trên một vùng được chọn ngẫu nhiên của hình ảnh. Vì vậy, mỗi epoch, mô hình sẽ nhìn thấy một phần khác nhau của hình ảnh và sẽ học theo.

## Tăng dữ liệu (data augmentation) là gì? Tại sao nó cần

Tăng dữ liệu đề cập đến việc tạo ra các biến thể ngẫu nhiên của dữ liệu đầu vào của chúng ta, sao cho chúng có vẻ khác nhau, nhưng không khác biệt đến mức thay đổi ý nghĩa của dữ liệu. Ví dụ bao gồm lật, xoay, cong vênh phối cảnh, thay đổi độ sáng, v.v. Việc tăng dữ liệu rất hữu ích để mô hình hiểu rõ hơn khái niệm cơ bản về đối tượng là gì và cách các đối tượng quan tâm được thể hiện trong hình ảnh. Do đó, tăng dữ liệu cho phép các mô hình học máy tổng quát hóa. Điều này đặc biệt quan trọng khi việc ghi nhãn dữ liệu có thể chậm và tốn kém.

## Sự khác biệt giữa item_tfms và batch_tfms là gì

item_tfms là các phép biến đổi được áp dụng cho một mẫu dữ liệu x trên CPU. Thay đổi kích thước () là một phép biến đổi phổ biến vì loạt ảnh đầu vào cho một cnn phải có cùng kích thước. Giả sử hình ảnh là RGB với 3 kênh, thì Resize() dưới dạng item_tfms sẽ đảm bảo hình ảnh có cùng chiều rộng và chiều cao

batch_tfms được áp dụng cho các mẫu dữ liệu theo lô (hay còn gọi là các mẫu riêng lẻ đã được đối chiếu thành một lô nhỏ) trên GPU. Chúng nhanh hơn và hiệu quả hơn item_tfms. Một ví dụ điển hình trong số này là những cái được cung cấp bởi aug_transforms(). Bên trong là một số bổ sung cấp độ hàng loạt giúp ích cho nhiều mô hình.

## Ma trận nhầm lẫn (confusion matrix) là gì

Ma trận nhầm lẫn lớp là một đại diện của các dự đoán được thực hiện so với các nhãn chính xác. Các hàng của ma trận đại diện cho các nhãn thực trong khi các cột đại diện cho các dự đoán. Do đó, số lượng hình ảnh trong phần tử đường chéo thể hiện số lượng hình ảnh được phân loại chính xác, trong khi phần tử nằm ngoài đường chéo là hình ảnh được phân loại không chính xác. Ma trận nhầm lẫn lớp cung cấp thông tin hữu ích về mức độ hoạt động của mô hình và những lớp nào mà mô hình có thể gây nhầm lẫn.

## Export làm gì

Export tiết kiệm cả kiến trúc, cũng như các tham số được đào tạo của kiến trúc mạng thần kinh. Nó cũng lưu cách định nghĩa DataLoaders.

## Cái tên nào được sử dụng mà khi chúng ta sử dụng một mô hình để nhận dự đoán, thay vì đào tạo

Inference

## IPython widgets là gì

IPython widgets là các chức năng kết hợp giữa JavaScript và Python cho phép chúng ta xây dựng và tương tác với các thành phần GUI trực tiếp trong sổ ghi chép Jupyter. Ví dụ về điều này sẽ là nút tải lên, có thể được tạo bằng các widget của hàm Python.FileUpload().

## Khi nào bạn có thể muốn sử dụng CPU để triển khai? Khi nào GPU có thể tốt hơn

GPU là tốt nhất để thực hiện song song các công việc giống hệt nhau. Nếu bạn sẽ phân tích các phần dữ liệu đơn lẻ tại một thời điểm (như một hình ảnh hoặc một câu đơn lẻ), thì thay vào đó, CPU có thể tiết kiệm chi phí hơn, đặc biệt là với sự cạnh tranh thị trường nhiều hơn cho máy chủ CPU so với máy chủ GPU. GPU có thể được sử dụng nếu bạn thu thập phản hồi của người dùng thành một lô tại một thời điểm và thực hiện suy luận trên lô. Điều này có thể yêu cầu người dùng chờ các dự đoán về mô hình. Ngoài ra, có nhiều phức tạp khác khi nói đến suy luận GPU, như quản lý bộ nhớ và xếp hàng các lô.

## Nhược điểm của việc triển khai ứng dụng của bạn lên máy chủ thay vì tới thiết bị khách (hoặc thiết bị cạnh) như điện thoại hoặc PC

Ứng dụng sẽ yêu cầu kết nối mạng và sẽ có thêm thời gian chờ mạng khi gửi đầu vào và trả kết quả. Ngoài ra, việc gửi dữ liệu cá nhân đến máy chủ mạng có thể dẫn đến các mối lo ngại về bảo mật

## Ba ví dụ về các vấn đề có thể xảy ra khi triển khai hệ thống cảnh báo gấu trong thực tế

Mô hình mà chúng tôi đã đào tạo có thể sẽ hoạt động kém khi:

- Xử lý hình ảnh ban đêm
- Xử lý hình ảnh có độ phân giải thấp (ví dụ: một số hình ảnh trên điện thoại thông minh)
- Mô hình trả về dự đoán quá chậm để hữu ích

## "out-of-domain data" là gì

Dữ liệu khác về cơ bản ở một số khía cạnh so với dữ liệu đào tạo của mô hình. Ví dụ, một máy dò vật thể được huấn luyện riêng với ảnh chụp ban ngày bên ngoài sẽ được cung cấp ảnh chụp vào ban đêm.

## "domain shift" là gì

Đây là khi loại dữ liệu thay đổi dần theo thời gian. Ví dụ: một công ty bảo hiểm đang sử dụng mô hình học sâu như một phần trong thuật toán định giá của họ, nhưng theo thời gian, khách hàng của họ sẽ khác, với dữ liệu đào tạo ban đầu không đại diện cho dữ liệu hiện tại và mô hình học sâu được áp dụng hiệu quả của miền dữ liệu.

## Ba bước trong quy trình triển khai là gì

- Quy trình thủ công - mô hình được chạy song song và không trực tiếp điều khiển bất kỳ hành động nào, với con người vẫn kiểm tra kết quả đầu ra của mô hình.
- Triển khai phạm vi hạn chế - Phạm vi của mô hình bị giới hạn và được giám sát cẩn thận. Ví dụ, thực hiện thử nghiệm triển khai mô hình có giới hạn về mặt địa lý và thời gian, được giám sát cẩn thận.
- Mở rộng dần dần - Phạm vi mô hình được tăng dần, trong khi các hệ thống báo cáo tốt được triển khai để kiểm tra bất kỳ thay đổi đáng kể nào đối với các hành động được thực hiện so với quy trình thủ công (nghĩa là các mô hình phải thực hiện tương tự như con người, trừ khi nó đã được dự đoán trước để tốt hơn).

## Hình ảnh thang độ xám được biểu diễn như thế nào trên máy tính? Làm thế nào về một hình ảnh màu

Hình ảnh thang độ xám được biểu thị bằng ma trận /tensor hạng 2 /lưới pixel với giá trị từ 0 đến 255. Hình ảnh màu là tenxơ hạng 3, chiều cao và chiều rộng dọc theo hai chiều và chiều thứ ba đại diện cho các giá trị từ 0 đến 255 cho màu đỏ, màu xanh lá cây và màu xanh lam.

## Các tệp và thư mục trong tập dữ liệu MNIST_SAMPLE được cấu trúc như thế nào? Tại sao

Có hai thư mục: /train và /valid, mỗi thư mục chứa hai thư mục: /3 và /7. Bên trong các thư mục đó là hình ảnh của chữ số tương ứng. Thư mục /train chứa phần lớn hình ảnh được sử dụng để huấn luyện một mô hình tương tự như vậy, thư mục /valid chứa các hình ảnh để xác thực mô hình. Ngoài ra còn có một tệp label.csv có khả năng chứa ánh xạ giữa tên tệp và nhãn chữ số.

## Giải thích cách hoạt động của phương pháp "độ tương đồng pixel (pixel similarity)" để phân loại chữ số

Ý tưởng đằng sau cách tiếp cận này là xem xét tất cả các hình ảnh để tìm một chữ số nhất định và tính giá trị trung bình cho mỗi pixel trên tất cả các hình ảnh. Sau đó, bằng cách so sánh một chữ số không được gắn nhãn với chữ số "trung bình" đó, chúng tôi có thể xác định mức độ giống hoặc khác của hình ảnh không xác định với mức trung bình đã biết.

## list comprehension là gì? Tạo một ngay bây giờ chọn các số lẻ từ danh sách và nhân đôi chúng

[i * 2 for i in range(20) if i % 2 == 0]

## "rank-3 tensor" là gì

Một tensor bậc 3 là một tensor có ba chiều, chẳng hạn như ảnh màu.

## Sự khác biệt giữa rank và shape tensor là gì? Làm thế nào để bạn có được rank từ shape

rank của tensor tương đương với số thứ nguyên mà tensor có. shape là số lượng giá trị tồn tại trong mỗi thứ nguyên. Vì shape cho chúng ta biết số lượng giá trị trên mỗi chiều, chúng ta có thể xác định số lượng giá trị được trả về để xác định rank.

## RMSE và L1 norm là gì

RMSE, hoặc lỗi bình phương căn bậc hai là sự khác biệt trung bình của dự đoán và bình phương nhãn và sau đó căn bậc hai?

```python
def mse (y, yhat): ((y - yhat) ** 2) .mean (). sqrt ()
```

Chuẩn L1 là giá trị trung bình của giá trị tuyệt đối của sự khác biệt giữa y và yhat

```python
def l1 (y, yhat): (y - yhat) .abs (). mean ()
```

## Làm thế nào bạn có thể áp dụng một phép tính trên hàng nghìn số cùng một lúc, nhanh hơn nhiều nghìn lần so với vòng lặp Python

Broadcasting

## Tạo một tensor 3x3 hoặc mảng chứa các số từ 1 đến 9. Nhân đôi nó. Chọn 4 số dưới cùng bên phải

```python
(torch.reshape (torch.arrange (1, 10), (3, 3)) * 2) [- 2:, - 2:]
```

## Broadcasting là gì

Broadcasting thường được sử dụng để hỗ trợ tính toán giữa hai tensor không bằng nhau với tác dụng phụ là không cần sao chép bất kỳ dữ liệu nào. Tác dụng phụ này có thể được lợi dụng để áp dụng tính toán cho hai tensor ngay cả khi chúng có thứ hạng bằng nhau. Điều này xảy ra ngầm trong Pytorch khi hoạt động của hai vectơ, ví dụ:

Không Broadcasting: chậm

```bash
>>> a = [1, 1, 1]
>>> b = [1, 1, 1]
>>> c = [x + y for x, y in zip(a, b)]
[2, 2, 2]
```

Broadcasting: nhanh

```bash
>>> a = tensor([1, 1, 1])
>>> b = tensor([1, 1, 1])
>>> a + b
tensor([2, 2, 2])
```

## Các chỉ số thường được tính bằng cách sử dụng tập hợp đào tạo hay tập hợp xác thực? Tại sao

SGD, hay stochastic gradient descent, là một thuật toán tối ưu hóa. Cụ thể, SGD là một thuật toán sẽ cập nhật các tham số của một mô hình để giảm thiểu một hàm tổn thất nhất định đã được đánh giá trên các dự đoán và mục tiêu. Ý tưởng chính đằng sau SGD (và nhiều thuật toán tối ưu hóa, cho vấn đề đó) là gradient của hàm mất mát cung cấp một dấu hiệu về cách hàm mất mát đó thay đổi trong không gian tham số, chúng ta có thể sử dụng để xác định cách tốt nhất để cập nhật các tham số trong để giảm thiểu hàm mất mát. Đây là những gì SGD làm.

## Tại sao SGD lại sử dụng mini-batches

Chúng ta cần tính toán hàm mất mát (và đạo hàm của chúng ta) trên một hoặc nhiều điểm dữ liệu. Chúng ta không thể tính toán trên toàn bộ tập dữ liệu do giới hạn tính toán và thời gian. Tuy nhiên, nếu chúng ta lặp lại từng điểm dữ liệu, gradient sẽ không ổn định và không chính xác, và không phù hợp để đào tạo. Như một thỏa hiệp, chúng ta tính toán tổn thất trung bình cho một tập hợp con nhỏ của tập dữ liệu tại một thời điểm. Tập hợp con này được gọi là một lô nhỏ. Sử dụng các lô nhỏ cũng hiệu quả hơn về mặt tính toán so với các mục đơn lẻ trên GPU.

## 7 bước trong SGD cho học máy là gì

- Khởi tạo các tham số - Giá trị ngẫu nhiên thường hoạt động tốt nhất.
- Tính toán các dự đoán - Điều này được thực hiện trên tập huấn luyện, mỗi lần một lô nhỏ.
- Tính toán tổn thất - Tổn thất trung bình trên quy mô nhỏ được tính
- Tính toán đạo hàm - đây là phép tính gần đúng về cách các thông số cần thay đổi để giảm thiểu hàm mất mát
- Bước cập nhật weights  - cập nhật thông số dựa trên trọng lượng đã tính Lặp lại quá trình
- Dừng - Trong thực tế, điều này dựa trên các ràng buộc về thời gian hoặc thường dựa trên thời điểm các mất mát trong đào tạo / xác nhận và các chỉ số ngừng cải thiện.

## Làm cách nào để chúng ta khởi tạo các trọng số trong một mô hình

Trọng lượng ngẫu nhiên hoạt động khá tốt.

## "loss" là gì

Hàm mất mát sẽ trả về một giá trị dựa trên các dự đoán và mục tiêu đã cho, trong đó các giá trị thấp hơn tương ứng với các dự đoán mô hình tốt hơn.

## Tại sao chúng ta không thể luôn sử dụng learning rate cao

Sự mất mát có thể "nảy" xung quanh (dao động) hoặc thậm chí phân kỳ, vì trình tối ưu hóa đang thực hiện các bước quá lớn và cập nhật các tham số nhanh hơn mức cần thiết.

## "Gradient" là gì

Các gradient cho chúng ta biết chúng ta phải thay đổi trọng lượng bao nhiêu để làm cho mô hình của chúng ta tốt hơn. Về cơ bản, nó là một phép đo hàm mất mát thay đổi như thế nào với những thay đổi của trọng số của mô hình (đạo hàm)