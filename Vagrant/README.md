### 1. Cài đặt Vagrant

- Cài đặt <a href="https://www.virtualbox.org/wiki/Downloads"> Virtualbox</a>
- Tải về vargrant <a href="https://www.vagrantup.com/downloads.html">tại đây </a>
- Sau khi cài đặt xong thì có thể sử dụng ```vagrant``` trong command


### 2. Nạp box cho Vagrant

Danh sách các box xem tại: https://vagrantcloud.com/discover/featured

>$ vagrant box add geerlingguy/centos7

Để xem các box đang có trong máy
>$ vagrant box list 


### 3. Tạo một máy ảo mới

Tạo một thư mục riêng cho nó
>$ cd /Desktop
>$ mkdir vmCentOS7
>$ vagrant init centos7

Sửa file ```Vagrantfile```, thêm dòng ```config.vm.network "forwarded_port", guest: 80, host: 8080```
để forward cổng ```8080``` từ máy client sang cổng ```80``` của server

Start máy ảo 
>$ vagrant up 

Truy cập vào máy ảo 
>$ vagrant ssh 


- ```vagrant box add``` : nạp box 
- ```vagrant box list``` : xem danh sách box 
- ```vagrant suspend``` : cho máy ảo tạm nghỉ 
- ```vagrant halt``` : shutdown máy ảo 
- ```vagrant destroy``` : cho máy ảo ra đi 
- ```vagrant reload``` : tải lại thiết lập trong file Vagrantfile 




