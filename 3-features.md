# Features 

Những feature chính của CI :
<br>



* __Maintain a single source repository__
Tất cả các source code sẽ đc maintain ở 1 repo . tránh việc source code bị phân bố nhiều nơi. ```subversion``` hay ```git``` là các công cụ hay dùng


* __Automate the build__
 Build thương đc tự động. Ngoài ra nó có thể tùy chỉnh theo từng bước được.

* __Make your build self-testing__
Việc build nên đc test. Ngay sau khi quá trình  build xảy ra, các testcase  nên được chạy để đảm bảo rằng việc kiểm tra có thể được thực hiện đối với các chức năng khác nhau của phần mềm.


* __Every commit should build on an integration machine__
```integration machine``` là con server để build. Tất cả các components phải có ở server để builđ

* __Keep the build fast.__ 
Cái việc Build diễn ra nhanh trong vài phút,

* __Test in a clone of the production enviroment.__
Cái môi trường build phải gần giống với môi trường product. Nếu 2 mỗi trường này khác nhau, thì có thể dẫn tới việc build fail cho dù nó đã đc ném lên build server

* __everyone can see what happening__
Toàn bộ quá trình build , test , deploy sẽ hiển thị cho tất cả mọi người.

* __automate deployment__
CI dẫn tỡi CD. CI thật sự cần thiết để chắc rằng việc build sẽ phải đơn giản để deploy lên cả 2 môi trường staging or product
