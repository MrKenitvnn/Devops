### Các lệnh cơ bản

##### Tải về 1 image. Ví dụ tải về ubuntu  
>$ docker pull library/ubuntu 

##### Xem danh sách images được pull sẵn trong máy 
>$ docker images 

##### Chạy 1 container từ images
>$ docker run -i -t REPOSITORY:TAG /bin/bash

hoặc

>$ docker run -i -t ID /bin/bash


##### Map cổng từ container về máy
>$ docker run -d -P ID

map host port 1234 vào port 4567 của ```container```
>$ docker run -d -p "1234:4567" yourImage # Map the host port 1234 to the container port 4567

xem địa chỉ vừa được map ở PORTS
>$ docker ps 

ngắt 1 container
>$ docker stop CONTAINER_ID 

### Demo scala
###### Tải về image docker-scala của lão lukasz từ docker hub 
>$ docker pull lukasz/docker-scala

###### Lấy code từ github về lưu ở thư mục ScalaDocker
>$ git clone https://github.com/huydx/scalresume.git /Users/HN/Desktop/ScalaDocker

###### Tạo môi trường ảo(```container```) từ image vừa pull về ở trên, và liên kết thư mục ```ScalaDocker```
của máy tính với thư mục ```/src``` của container
>$ docker run -v /Users/HN/Desktop/ScalaDocker:/src -it fb3320c81cb2 /bin/bash

> Ý nghĩa của câu lệnh trên:
 - <b>docker run</b> : lệnh tạo một container cho Docker
 - <b>tham số -v /Users/HN/Desktop/ScalaDocker:/src</b> : để liên kết thư mục /Users/HN/Desktop/ScalaDocker ở máy tính hiện tại, vào thư mục /src của container.
 - <b>tham số -it fb3320c81cb2 /bin/bash</b>: Để chỉ định images cần tạo có id là fb3320c81cb2
   và tự động chạy lệnh ```/bin/bash``` sau khi khởi tạo xong, nhờ đó chúng ta sẽ truy cập được vào chế độ dòng lệnh của container
   và quản lý nó giống như một máy tính thông thường.

 
### Mongodb

>$ docker pull mongo


>$ docker images


>$ docker run -d -p 127.0.0.1:27017:27017 IMAGE_ID  
 - Mở trình duyệt lên vào ```127.0.0.1:27017``` để check xem connect được chưa.


>$ docker ps   -- để xem danh sách container


>$ docker exec -it CONTAINER_ID bash     -- kết nối tới container

 
>$ mongo để test như bình thường
