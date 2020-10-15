# Câu trả lời cho các câu hỏi trong bài học

## Chúng ta có thể luôn sử dụng một mẫu ngẫu nhiên cho một tập hợp xác thực không? Tại sao hoặc tại sao không

Tập hợp kiểm tra hoặc xác thực tốt phải đại diện cho dữ liệu mới mà bạn sẽ thấy trong tương lai. Đôi khi điều này không đúng nếu sử dụng mẫu ngẫu nhiên. Ví dụ: đối với dữ liệu chuỗi thời gian, việc chọn các bộ một cách ngẫu nhiên không có ý nghĩa. Thay vào đó, xác định các khoảng thời gian khác nhau cho tập huấn luyện, xác thực và thử nghiệm là một cách tiếp cận tốt hơn.

## Overfitting là gì? Cung cấp một ví dụ

Overfitting là vấn đề thách thức nhất khi nói đến đào tạo mô hình học máy. Overfitting đề cập đến khi mô hình phù hợp quá chặt chẽ với một tập hợp dữ liệu giới hạn nhưng không tổng quát hóa tốt cho dữ liệu không chưa xuất hiện trong tập huấn luyện. Điều này đặc biệt quan trọng khi nói đến mạng nơ-ron, vì mạng nơ-ron có khả năng “ghi nhớ” tập dữ liệu mà mô hình đã được đào tạo và sẽ hoạt động không tốt trên dữ liệu không nhìn thấy vì nó không “ghi nhớ” các giá trị chân lý cơ bản cho dữ liệu đó. Đây là lý do tại sao cần có một khung xác thực thích hợp bằng cách chia nhỏ dữ liệu thành các tập huấn luyện, xác thực và thử nghiệm.

## Metric là gì? Nó khác với "loss"

Metric là một hàm đo lường chất lượng của các mô hình dự đoán bằng cách sử dụng tập hợp xác thực. Điều này tương tự với loss, cũng là một thước đo hiệu suất của mô hình. Tuy nhiên, loss được sử dụng bởi thuật toán tối ưu hóa (như SGD) để cập nhật hiệu quả các thông số mô hình, trong khi metric là các thước đo hiệu suất có thể hiểu của con người. Đôi khi, một metric cũng có thể là một lựa chọn tốt cho loss

## Các mô hình tiền chế (pretrained model) có thể giúp ích như thế nào

Các mô hình tiền chế đã được đào tạo về các vấn đề khác có thể khá giống với nhiệm vụ hiện tại. Ví dụ, các mô hình nhận dạng hình ảnh được đào tạo trước thường được đào tạo trên tập dữ liệu ImageNet, tập dữ liệu này có 1000 lớp tập trung vào nhiều loại đối tượng trực quan khác nhau. Các mô hình tiền chế rất hữu ích vì chúng đã học cách xử lý rất nhiều tính năng đơn giản như phát hiện cạnh và màu. Tuy nhiên, vì mô hình được huấn luyện cho một nhiệm vụ khác với nhiệm vụ hiện tại nên chúng khó có thể được sử dụng ngay cho nhiệm vụ hiện tại

## "Head" của một model là gì

Khi sử dụng mô hình được đào tạo trước, các lớp sau của mô hình, hữu ích cho nhiệm vụ mà mô hình được đào tạo ban đầu, được thay thế bằng một hoặc nhiều lớp mới với trọng số ngẫu nhiên, có kích thước thích hợp cho tập dữ liệu bạn đang làm việc . Các lớp mới này được gọi là “phần đầu” của mô hình.

## Các lớp đầu tiên của CNN trích xuấ những loại tính năng nào? Còn các lớp sau thì sao

Các lớp trước đó học các tính năng đơn giản như cạnh chéo, ngang và dọc. Các lớp sau sẽ học các tính năng nâng cao hơn như bánh xe ô tô, cánh hoa và thậm chí cả đường viền của động vật.

## Các mô hình hình ảnh chỉ hữu ích cho ảnh

Không! Mô hình hình ảnh có thể hữu ích cho các loại hình ảnh khác như bản phác thảo, dữ liệu y tế, v.v.

Tuy nhiên, nhiều thông tin có thể được biểu diễn dưới dạng hình ảnh. Ví dụ, một âm thanh có thể được chuyển đổi thành một biểu đồ quang phổ, là một cách diễn giải trực quan của âm thanh. Chuỗi thời gian (ví dụ: dữ liệu tài chính) có thể được chuyển đổi thành hình ảnh bằng cách vẽ trên biểu đồ. Thậm chí tốt hơn, có nhiều phép biến đổi khác nhau tạo ra hình ảnh từ chuỗi thời gian và đã đạt được kết quả tốt cho việc phân loại chuỗi thời gian. Có rất nhiều ví dụ khác, và bằng cách sáng tạo, bạn có thể hình thành vấn đề của mình như một bài toán phân loại hình ảnh và sử dụng các mô hình hình ảnh được xử lý trước để có được kết quả hiện đại!

## "Architecture" là gì

Kiến trúc (architecture) là khuôn mẫu hoặc cấu trúc của mô hình mà chúng tôi đang cố gắng phù hợp. Nó xác định mô hình toán học mà chúng ta đang cố gắng điều chỉnh.

## Segmentation là gì

Về cốt lõi, phân đoạn (segmentation) là một vấn đề phân loại theo pixel. Chúng tôi cố gắng dự đoán một nhãn cho mỗi pixel trong hình ảnh. Điều này cung cấp một mặt nạ cho các phần của hình ảnh tương ứng với nhãn đã cho.

## Y_range được sử dụng để làm gì? Khi nào chúng ta cần nó

Y_range đang được sử dụng để giới hạn các giá trị được dự đoán khi vấn đề của chúng tôi tập trung vào việc dự đoán một giá trị số trong một phạm vi nhất định (ví dụ: dự đoán xếp hạng phim, phạm vi 0,5-5).

## "Hyperparameters" là gì

Các mô hình đào tạo yêu cầu nhiều tham số khác nhau xác định cách mô hình được đào tạo. Ví dụ: chúng ta cần xác định thời gian chúng ta đào tạo, hoặc tốc độ học tập (tốc độ các tham số mô hình được phép thay đổi) được sử dụng. Các loại tham số này là siêu tham số (hyperparameters).

## Cách tốt nhất để tránh thất bại khi sử dụng AI trong tổ chức

- Đảm bảo rằng tập hợp đào tạo, xác nhận và thử nghiệm được xác định đúng cách để đánh giá mô hình theo cách thích hợp.
- Hãy thử các phương pháp đơn giản, mà các mô hình trong tương lai hy vọng sẽ đánh bại. Hoặc thậm chí các phương pháp giản này có thể là đủ trong một số trường hợp.

## p-value là gì

Trị số P là một con số xác suất, tức là viết tắt chữ “probability value”. Chúng ta thường gặp những phát biểu được kèm theo con số, chẳng hạn như “Kết quả phân tích cho thấy tỉ lệ gãy xương trong nhóm bệnh nhân được điều trị bằng thuốc Alendronate là 2%, thấp hơn tỉ lệ trong nhóm bệnh nhân không được chữa trị (5%), và mức độ khác biệt này có ý nghĩa thống kê (p = 0.01)”, hay một phát biểu như “Sau 3 tháng điều trị, mức độ giảm áp suất máu trong nhóm bệnh nhân là 10% (p < 0.05)”. Trong văn cảnh trên đây, đại đa số nhà khoa học hiểu rằng trị số P phản ánh xác suất sự hiệu nghiệm của thuốc Alendronate hay một thuật điều trị. Có nhiều người hiểu rằng câu văn trên có nghĩa là “xác suất mà thuốc Alendronate tốt hơn giả dược là 0.99” (lấy 1 trừ cho 0.01). Nhưng cách hiểu đó hoàn toàn sai.  

## Prior là gì

## Cung cấp một ví dụ về nơi mà mô hình phân loại gấu có thể hoạt động kém, do sự khác biệt về cấu trúc hoặc kiểu dáng đối với dữ liệu huấn luyện.

Có nhiều trường hợp mô hình phân loại gấu có thể không thành công, đặc biệt nếu những trường hợp này không được thể hiện trong dữ liệu đào tạo:
- Con gấu bị cản trở một phần
- Hình ảnh ban đêm được chuyển vào mô hình
- Hình ảnh có độ phân giải thấp được chuyển vào mô hình
- Con gấu ở xa máy ảnh
- Tập dữ liệu huấn luyện gấu rất thiên về một loại tính năng (ví dụ: màu sắc)

## Do đâu mà các mô hình văn bản hiện đang có sự thiếu hụt lớn

Các mô hình văn bản có thể tạo ra văn bản phù hợp với ngữ cảnh (như câu trả lời hoặc bắt chước phong cách tác giả). Tuy nhiên, các mô hình văn bản vẫn gặp khó khăn với các phản hồi chính xác. Với thông tin thực tế (chẳng hạn như cơ sở kiến thức), vẫn khó để tạo ra các câu trả lời sử dụng thông tin này để tạo ra các câu trả lời đúng thực tế, mặc dù văn bản có vẻ rất hấp dẫn. Điều này có thể rất nguy hiểm, vì giáo dân có thể không đánh giá được tính chính xác thực tế của văn bản được tạo.

## Những tác động xã hội tiêu cực có thể có của các mô hình tạo văn bản

Khả năng tạo ra các mô hình tạo văn bản để tạo ra các câu trả lời có tính thuyết phục cao, phù hợp ngữ cảnh có thể được sử dụng ở quy mô lớn để truyền bá thông tin sai lệch (“tin giả”) và khuyến khích xung đột. Các mô hình củng cố thành kiến (như thành kiến về giới tính, thành kiến về chủng tộc) trong dữ liệu đào tạo và tạo ra một vòng luẩn quẩn của kết quả đầu ra thành kiến.

## Trong các tình huống mà một mô hình có thể mắc lỗi và những sai lầm đó có thể gây hại, thì đâu là giải pháp tốt để tự động hóa quy trình

Các dự đoán của mô hình có thể được các chuyên gia về con người xem xét để họ đánh giá kết quả và xác định đâu là bước tốt nhất tiếp theo. Điều này đặc biệt đúng khi áp dụng học máy cho các chẩn đoán y khoa. Ví dụ: mô hình máy học để xác định đột quỵ trong chụp CT có thể cảnh báo các trường hợp ưu tiên cao để xem xét nhanh, trong khi các trường hợp khác vẫn được gửi đến bác sĩ X quang để xem xét. Hoặc các mô hình khác cũng có thể nâng cao khả năng của chuyên gia y tế, giảm rủi ro nhưng vẫn nâng cao hiệu quả của quy trình làm việc. Ví dụ, mô hình học sâu có thể cung cấp các phép đo hữu ích cho bác sĩ X quang hoặc nhà nghiên cứu bệnh học.

## Học sâu đặc biệt giỏi ở loại dữ liệu dạng bảng nào

Học sâu rất tốt trong việc phân tích dữ liệu dạng bảng bao gồm ngôn ngữ tự nhiên hoặc các cột phân loại có bản số cao (chứa nhiều lựa chọn rời rạc hơn như mã zip).

## Nhược điểm chính của việc sử dụng trực tiếp mô hình học sâu cho hệ thống đề xuất là gì?

Các phương pháp tiếp cận máy học cho hệ thống đề xuất thường sẽ chỉ cho biết người dùng có thể thích sản phẩm nào và có thể không phải là các đề xuất hữu ích cho người dùng. Ví dụ: nếu người dùng quen thuộc với các sách khác của cùng một tác giả, thì việc giới thiệu các sản phẩm đó sẽ không hữu ích ngay cả khi người dùng đã mua sách của tác giả đó. Hoặc, giới thiệu các sản phẩm mà người dùng có thể đã mua.

## Các bước của Phương pháp Tiếp cận Hệ thống Truyền lực (Drivetrain Approach) là gì

![](https://forums.fast.ai/uploads/default/original/2X/b/b4fcf03eeeca3ebe8d5948067509784f8f0c2351.png)

## Làm thế nào để các bước của phương pháp Hệ thống truyền lực ánh xạ đến hệ thống khuyến nghị?

Mục tiêu của công cụ đề xuất là thúc đẩy doanh số bán hàng bổ sung bằng cách làm khách hàng ngạc nhiên và thích thú với các đề xuất về các mặt hàng mà họ sẽ không mua nếu không có đề xuất. Đòn bẩy là thứ hạng của các khuyến nghị. Dữ liệu mới phải được thu thập để tạo ra các đề xuất sẽ gây ra doanh số bán hàng mới. Điều này sẽ yêu cầu tiến hành nhiều thử nghiệm ngẫu nhiên để thu thập dữ liệu về một loạt các đề xuất cho nhiều khách hàng. Đây là một bước mà ít tổ chức thực hiện; nhưng nếu không có nó, bạn không có thông tin cần thiết để thực sự tối ưu hóa các đề xuất dựa trên mục tiêu thực sự của bạn (bán hàng nhiều hơn!)

## Tạo mô hình nhận dạng hình ảnh bằng cách sử dụng dữ liệu bạn sắp xếp và triển khai nó trên web

## DataLoaders là gì

Lớp DataLoaders là lớp truyền dữ liệu đến mô hình fastai. Về cơ bản nó là một lớp lưu trữ các đối tượng Dataloader được yêu cầu (thường dành cho các tập xác nhận và đào tạo).

## Bốn điều chúng ta cần nói với fastai để tạo DataLoaders

- Chúng tôi đang làm việc với những loại dữ liệu nào
- cách lấy danh sách các phần của dữ liệu
- Làm thế nào để gắn nhãn cho các mẫu của dữ liệu
- Cách tạo bộ xác thực

## Tham số bộ chia thành DataBlock được sử dụng làm gì

Trong fastai DataBlock, bạn cung cấp đối số bộ tách một cách để fastai chia tập dữ liệu thành các tập con (thường là tập hợp đào tạo và xác nhận). Ví dụ: để phân chia dữ liệu một cách ngẫu nhiên, bạn có thể sử dụng lớp RandomSplitter được xác định trước của fastai, cung cấp cho nó tỷ lệ dữ liệu được sử dụng để xác thực.

## Làm cách nào để chúng tôi đảm bảo phân tách ngẫu nhiên luôn cung cấp cùng một tập hợp xác thực

Hóa ra là máy tính của chúng ta không thể tạo ra những con số thực sự ngẫu nhiên. Thay vào đó, họ sử dụng một quy trình được gọi là trình tạo giả ngẫu nhiên. Tuy nhiên, quá trình này có thể được kiểm soát bằng cách sử dụng một hạt giống ngẫu nhiên. Bằng cách đặt giá trị seed ngẫu nhiên, trình tạo giả ngẫu nhiên sẽ tạo ra các số “ngẫu nhiên” theo cách cố định và nó sẽ giống nhau cho mọi lần chạy. Sử dụng một seed ngẫu nhiên, chúng ta có thể tạo một phân tách ngẫu nhiên luôn cung cấp cùng một bộ xác thực.
