# CI - Continuous Integration

Tích hợp liên tục.


# Why Continuous Integration

1. __Các components của 1 software sẽ làm việc với nhau như cách chúng phải làm ?__ 
Đôi khi, hệ thống sẽ trở lên __phức tạp__ vì nó có rất nhiều intefaces cho mỗi 1 component. Cái điều quan trong là ``` Chúng ta phải đảm bảo các Components kết hợp hoạt động trơn chu với nhau ```.


2. __Code quá phức tạp cho mục đích ```Integration``` ?__
Nếu tiến trình ```CI``` thất bại, Có khả năng cao là do Code quá phức tạp. Và đây có thể là một tín hiệu để áp dụng các ```Design Partern ``` khác để giảm cái độ phức tạp của code.

3. __Kiểm tra xem code có tuân thủ một số chuẩn ```format code```  ?__
Các ```test case``` luôn test xem cái code có theo các chuẩn hay không. Tự động thực hiện việc ```test``` trước khi ```build```.
Có một số chuẩn ```format code``` như là ```eslint``` hay ```prettier``` sẽ hộ trợ phần này.
4. __Cái việc tự động test sẽ cover hết bao nhiêu phần code ?__
 Không có một điểm nào trong cái code đc test nếu mà cái ```test case``` ko cover hết được những cái chức năng cần thiết. vì vâỵ việc viết test khá là quan trọng.

5. __Có phải tất cả các ```test case``` đã thành công sau cái bản thay đổi ```latest``` ?__
Nếu một cái ```test case ``` thất bại, thì không cho ```deploy```. CI nó sẽ kiểm tra xem code này sẽ đc move tới cái ```deploy stage`` ko?

### Wordflow

<img src="https://www.tutorialspoint.com/continuous_integration/images/workflow.jpg" alt="work flow"  />

##### Luồng chính của CI :

1. Dev sẽ commit code lên ``` version control repository ``` (vd ```git```). Trong khi đó ```CI server``` sẽ kết hợp và build 1 cái máy để kiểm tra các sự thay đổi trong code vừa submit lên. (thường là sau vài phút)

2. Ngay sau khi commit, ```CI server``` sẽ phát hiện những cái sự thay đổi của cái ```repo``` đó. Nó sẽ lấy bản ``` latest copy``` từ cái ```repo``` đó và thực hiện build script rồi tích hợp với cái software.

3. ```CI server ``` sẽ gửi sinh ra các thông báo và gửi về cho các member.

4. ```Unit test``` sẽ được thực hiện nếu việc build đã thành công. nếu test thành công thì sẽ được ```deploy``` trên 2 server  ```Staging``` và```production``` .

5. ``` CI server ``` tiếp tục xem những cái sự thay đổi ở ``` repo``` , toàn bộ quá trình này được lặp lại


##### 2 môi trường ``` staging ``` và ```production ``` 

* ```Staging``` là cái môi trường gần giống với môi trường ``` production ``` nhất. các thử nghiệm sẽ được chạy trên đây.
* ``` Production ``` là cái môi trường cuối cùng, sản phẩm ngon nhất sẽ đc ném ra đây 