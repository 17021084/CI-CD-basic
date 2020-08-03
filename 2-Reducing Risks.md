# CI Reducing Risks 
 Giảm thiểu rủi ro
<hr>
CI sẽ giúp ta có thể tìm ra những cái rủi ro, đánh giá và báo cáo tình trạng của project một cách dễ dàng. <br>

Bằng cách ước tính được cái rủi ro sớm trong cái vòng đời phát triển, sẽ có ít khả năng rủi ro sẽ thành vấn đề khi hệ thống thực sự go live.


### Risk 1 – Lack of Deployable Software

* _" nó chạy ngon trên máy tôi những ko chạy được trên máy khác "_ 
=> Giải pháp: sử dụng ``` container```

* _"ko có khả năng đồng bộ hóa với database"_ 
    1. sợ thay đổi hoặc refactor trên db
    2. Khó có thể thêm data với những tập data khác nhau để test.
    3. khó trong khâu maintain và test môi trường

### Risk 2 – Discovering Defects Late in the Lifecycle.

Vì có rất nhiều thay đổi xảy ra thường xuyên bởi dev  đối với code, nên luôn có khả năng một lỗi có thể được đưa vào trong code chỉ có thể được phát hiện ở giai đoạn sau. Trong những trường hợp như vậy, điều này có thể gây ra một tác động lớn bởi vì càng phát hiện ra lỗi trong phần mềm, thì càng tốn kém để loại bỏ lỗi.
<br>
=> Giải pháp.

1. ```Regression Testing ``` Kiểm thử hồi quy là test và test lại.Nếu có bất kỳ thay đổi lớn nào ở code, thì hoàn toàn bắt buộc phải đảm bảo rằng tất cả các ```test case``` đều được chạy.

2. ```Test Coverage ```  sẽ ko có điểm nào trong testing, nếu ```test case ``` ko cover đc hết các chức năng trong code. Điều quan trọng là ```test case``` đc tạo để test app thành công và toàn bộ các code paths đc test.

<br>
ví dụ: Test màn login. Đương nhiên ko có test case nào, mà chỉ có 1 cái kịch bản của việc login thành công. Mình phải có các ```testcase``` cho các trường hợp nhập id và password. 


### Risk 3 – Lack of Project Visibility

Cơ chế giao tiếp đòi hỏi nhiều sự kết hợp đề chắc rằng cái thông tin của project sẽ đến đúng lúc đúng người. <br>

Điểu gì  sẽ xảy ra khi dev cần một số thông tin nhưng chúng lại ko sẵn có? Nếu 1 serve toang thì làm thế nào để thông báo, ta có thể gửi mail một cách thủ công để giảm thiều điều đó.Nhưng nó ko thể chắc rằng thông tin đó có truyền đúng đến người cần nhận hay ko?

<br>
=> giải pháp : CI server sẽ tự động gửi mail bất cứ khi nào build fail. nó sẽ gửi hết cho các stakeholder. đảm bảo mọi người có thể nắm đc tình hình

### Risk 4 – Low Quality Software

Có những (khuyết điểm )```defects``` do là thiết kế tồi , or smell code or khó để maintain.

Việc tìm những đoạn smell code,có thể giảm độ phức tạp tiết kiệm thời gian tiền bạc và chất lượng pm cao.
<br>

các components để thực hiện kiểm tra format code có thể được tích hợp với phần mềm CI. Điều này có thể được chạy sau khi code đc build  để đảm bảo rằng code đã đc format
