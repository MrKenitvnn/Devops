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

>$ vagrant init geerlingguy/centos7

#### Sửa file ```Vagrantfile```: Nếu thay đổi cần chạy lệnh: ```vagrant reload```
để truy cập cổng ```80``` của máy server bằng cổng ```8080``` của máy developer
```
config.vm.network "forwarded_port", guest: 80, host: 8080
```

Synced folder ```/var/www/html``` của máy ảo server với folder ```/vmCentOS7/html``` của máy developer
```
config.vm.synced_folder "html/", "/var/www/html/"
```


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


### 4. Chia sẻ máy ảo 

Tạo tài khoản <a href="https://atlas.hashicorp.com/account/new">Atlas </a>

Đăng nhập vào Vagrant Cloud
>$ vagrant login

Chia sẻ máy ảo 
>$ vagrant share --ssh

```shell
==> default: Creating Vagrant Share session...
    default: Share will be at: intimidating-pony-6449
==> default: Your Vagrant Share is running! Name: intimidating-pony-6449
==> default: URL: http://intimidating-pony-6449.vagrantshare.com
```

Từ máy cài đặt ```Vagrant``` kết nối tới máy ảo server được chia sẻ
>$ vagrant connect intimidating-pony-6449

URL, cần start webserver lên 
> http://intimidating-pony-6449.vagrantshare.com
