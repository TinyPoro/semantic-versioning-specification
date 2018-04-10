### Đặc tả Semantic Versioning (SemVer)
Những từ khóa như “MUST”, “MUST NOT”, “REQUIRED”, “SHALL”, “SHALL NOT”, “SHOULD”, “SHOULD NOT”, “RECOMMENDED”, “MAY”, và “OPTIONAL” trong tài liệu này đã được giải thích như mô tả trong [RFC 2119](http://tools.ietf.org/html/rfc2119).

1. Phần mềm sử dụng Semantic Versioning phải khai báo một API công khai. API này nên được khai báo ngay trong code của nó hoặc tồn tại chặt chẽ trong tài liệu. Tuy nhiên, cuối cùng, nó nên được tóm lược và bao quát.

2. Một số phiên bản thông thường phải tuân theo dạng X.Y.Z trong đó X, Y, và Z là các số không âm, và phải không được bắt đầu bởi các số 0. X là phiên bản chính, Y là phiên bản phụ, và Z là phiên bản vá. Mỗi phẩn tử phải là các số tự tăng. Ví dụ: 1.9.0 -> 1.10.0 -> 1.11.0.

3. Một khi một gói phiên bản đã được phát hành, nội dung của phiên bản đó không được phép chỉnh sửa. Mọi chỉnh sửa phải được phát hành ở 1 phiên bản mới.

4. Phiên bản chính số 0 (0.y.z) là cho sự phát triển ban đầu. Mọi thứ có thể thay đổi bất cứ lúc nào.  API công khai không được coi là ổn định. 

5. Phiên bản 1.0.0 định nghĩa một API công khai. Cách thức số phiên bản được tăng lên sau khi bản phát hành này phụ thuộc vào API công khai này và cách nó thay đổi.

6. Phiên bản vá lỗi Z(x.y.z | x > 0) phải tăng chỉ sau khi một bản  sửa lỗi tương thích với cái hiện tại được giới thiệu. Sửa lỗi được định nghĩa là thay đổi nội bộ để khắc phục hành vi không chính xác.

7. Phiên bản phụ Y (x.Y.z | x > 0) phải được tăng nếu có một chức năng mới nhưng vẫn tương thích được giới thiệu đến API công khai. Nó phải được tăng nếu bất kỳ chức năng API công khai được đánh dấu yêu cầu. Nó có thể tăng nếu một chức năng hay cải tiển đáng kể được giới thiệu bên trong mã cá nhân. Nó cũng có thể bao gồm các thay đổi ở mức vá. Phiên bản vá phải được đặt lại về 0 khi một phiên bản phụ được tăng.

8. Phiên bản chính X (X.y.z | X > 0) phải được tăng nếu bất kỳ thay đối tương thích được giới thiệu đến API công khai. Nó có thể bao gồm các thay đổi mức phụ và vá. Phiên bản vá và phụ phải được đặt lại về 0 khi phiên bản chính tăng.

9. Một phiên bản tiền phát hành có thể được biểu thị bằng cách thêm dấu nối và một chuỗi các số nhận dạng dấu chấm ngay lập tức theo bản vá lỗi. Các định danh phải bao gồm các ký tự và gạch nối ASCII [0-9A-Za-z-]. Các định danh không được phép rỗng. Các định danh số không được phép bắt đầu bởi các số 0. Các phiên bản tiền phát hành có  ưu tiên thấp hơn so với phiên bản liên kết bình thường. Một phiên bản tiền phát hành chỉ định rằng phiên bản không ổn định và có thể không thỏa mãn các yêu cầu tương thích dự định như được biểu thị so với phiên bản bình thường liên quan. Ví dụ:  1.0.0-alpha, 1.0.0-alpha.1, 1.0.0-0.3.7, 1.0.0-x.7.z.92.

10. Xây dựng siêu dữ liệu CÓ THỂ được biểu thị bằng cách nối thêm một dấu cộng và một loạt các ký hiệu nhận dạng dấu chấm ngay sau bản vá hoặc phiên bản tiền phát hành. Các định danh phải bao gồm chỉ các ký tự và gạch nối ASCII [0-9A-Za-z-]. Các định danh không được phép rỗng. Xây dựng siêu dữ liệu dựng nên được loại bỏ khi xác định phiên bản ưu tiên. Vì vậy, hai phiên bản khác nhau chỉ trong xây dựng siêu dữ liệu, có cùng một ưu tiên. Ví dụ: 1.0.0-alpha+001, 1.0.0+20130313144700, 1.0.0-beta+exp.sha.5114f85.

11. Độ ưu tiên dùng để so sánh các phiên bản với nhau khi sắp xếp. Độ ưu tiên phải được tính toán bằng cách chia phiên bản thành các định danh chính, phụ, vá và tiền phát hành theo thứ tự. (Xây dựng siêu dữ liệu không được tính cho độ ưu tiên)
Độ ưu tiên được xác định bằng sự khác nhau đầu tiên khi so sánh mỗi định dang từ trái qua phải như sau: Các phiên bản chính, phụ và vá luôn được so sánh bằng số. Ví dụ  1.0.0 < 2.0.0 < 2.1.0 < 2.1.1. Khi bản chính, phụ và vá bằng nhau, phiên bản tiền phát hành có độ ưu tiên thấp hơn phiên bản bình thường. Ví dụ 1.0.0-alpha < 1.0.0. Độ ưu tiên cho 2 phiên bản tiền phát hành với cùng phiên bản lớn, nhỏ và vá phải được xác định bằng cách từng dấu chấm chia cách các định danh từ trái quá phải cho đến khi có 1 sự các biệt được tìm thấy như sau : các định danh chỉ bao gồm các chữ số được so sánh số học và các định danh với các chữ và các dấu nối được so sánh theo từ vựng theo thứ tự sắp xếp ASCII. Các định danh số học luôn có độ ưu tiên thấp hơn các định danh không phải số. Một tập các trường tiền phát hành có độ ưu tiên cao hơn các tập nhỏ, nếu tất cả các định danh phía trước là bằng nhau. Ví dụ : 1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-alpha.beta < 1.0.0-beta < 1.0.0-beta.2 < 1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0.

### Tại sao phải sử dụng Semantic Versioning?
Đây không phải là 1 ý kiến mới hay cuộc cách mạng nào cả. Trên thực tế, bạn hẳn là làm điều gì gần giống như vậy rồi. Vấn đề là "gần giống" ở đây không đủ tốt. Nếu không tuân thủ theo 1 tập các đặc tả chính thức, các số phiên bản thực chất sẽ vô nghĩa cho việc quản lý sự phụ thuộc. Bằng cách đặt tên và đưa ra định nghĩa rõ ràng cho các ý tưởng trên, nó trở nên dễ dàng trong việc liên kết các ý tưởng của bạn tới các người dùng phần mềm. Một khi các ý định này là rõ ràng, cuối cùng có thể được tạo ra các đặc điểm phụ thuộc (nhưng không quá linh hoạt).

Một ví dụ đơn giản sẽ mô tả cách Semantic Versioning có thể làm cho sự phụ thuộc kinh khủng là một điều của quá khứ. Xem xét 1 thư viện tên là "Filetruck". Nó yêu cầu 1 gói Semantically Versioned gọi là "Ladder". Tại thời điểm Firetruck được tạo ra, Ladder lúc đó đang ở phiên bản 3.1.0. Từ khi Firetruck sử dụng 1 vài chức năng được giới thiệu lần đầu trong phiên bản 3.1.0, bạn có thể đặc tả 1 cách an toàn các phụ thuộc Ladder tốt hơn hay bằng so với 3.1.0 nhưng tệ hơn so với 4.0.0. Bây giờ khi Ladder ở phiên bản 3.1.1 và 3.2.0 khả dụng, bạn có thể phát hành chúng tới các hệ thống quản lý gói (package) và biết rằng chúng sẽ tương thích với các phụ thuộc phần mềm hiện tại.

Với tư cách là một nhà phát triển có trách nhiệm, bạn sẽ muốn tất nhiên xác minh rằng bất kỳ chức năng nâng cấp gói nào được quảng cáo. Thế giới thực là một nơi lộn xộn; không có gì chúng ta có thể làm được về điều đó nhưng phải thận trọng. Những gì bạn có thể làm là để cho Semantic Versioning a cung cấp cho bạn một cách lành mạnh để phát hành và nâng cấp các gói mà không cần phải cuộn phiên bản mới của gói phụ thuộc, tiết kiệm thời gian và rắc rối

Điều này có vẻ nghe như mong muốn, tất cả những gì bạn cần làm là bắt đầu sử dụng Semantic Versioning để khai báo rằng bạn đang làm như thể và sau đó tuân theo các luật. Liên kết trang web này từ README cả bạn để những người khác biết luật và có thể tận dụng chúng.


