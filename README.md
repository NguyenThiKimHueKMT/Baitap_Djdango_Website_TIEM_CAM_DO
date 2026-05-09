# Baitap_Djdango_Website_TIEM_CAM_DO  
# PHÁT TRIỂN ỨNG DỤNG VỚI MÃ NGUỒN MỞ (DJANGO + XÂY DỰNG WEBSITE QUẢN LÝ TIỆM CẦM ĐỒ)  
# HỌ TÊN: NGUYỄN THỊ KIM HUỆ   
# LỚP: K58KTP  
# MSSV: K225480106026 

# TỔ CHỨC CSDL CHO HỆ THỐNG QUẢN LÝ TIỆM CẦM ĐỒ  
<img width="780" height="520" alt="image" src="https://github.com/user-attachments/assets/670c0311-124e-4b76-91e3-105111027fd3" />  

# 1: CHUẨN BỊ UBUNTU  
Kiểm tra phiên bản Docker docker --version  
Kiểm tra phiên bản Docker Compose docker compose version  
<img width="814" height="472" alt="image" src="https://github.com/user-attachments/assets/27776bd4-9c71-42ef-b4dc-b9c18266d204" />   

# 2: TẠO PROJECT  
Bước 1: Tạo thư mục mkdir camdo_project  
Bước 2: Vào thư mục cd camdo_project  
<img width="811" height="474" alt="image" src="https://github.com/user-attachments/assets/839e9922-6ad0-4958-b9c8-c3846075d223" />  
Bước 3: Tạo thư mục django trong camdo_project    

# 3: TẠO DOCKERFILE  
Bước 1: Vào thư mục Django: cd django  
Bước 2: Tạo file DockerFile nano Dockerfile  
Bước 3: Thêm nội dung cho File dockerfile  
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/c912a2a1-98a6-4928-b81b-42fa683a093b" />  

# 4: TẠO FILE requirements.txt  
Bước 1: Tạo file requirements.txt nano requirements.txt  
Bước 2: Dán nội dung sau  
<img width="780" height="474" alt="image" src="https://github.com/user-attachments/assets/1b39924d-4128-4bcd-a168-031bd3a2a913" />  

# 5. Tạo file docker-compose.yml  
5.1. về thư mục gốc bằng lệnh cd ..  
5.2. chạy lệnh sudo nano docker-compose.yml  
<img width="1112" height="646" alt="image" src="https://github.com/user-attachments/assets/68ab70fa-191e-47da-909b-2170290e5c3a" />  

# 6. Run hệ thống
chạy lệnh: docker compose up --build    
<img width="1014" height="636" alt="image" src="https://github.com/user-attachments/assets/2e115274-f8c8-4511-b1b3-6218078e0690" />
  
# 7. kiểm tra   
lệnh ls
<img width="746" height="471" alt="image" src="https://github.com/user-attachments/assets/ff6f747b-e536-4389-914b-b2309e619f94" />
 
# 8. Tạo django project  
lệnh docker compose run web django-admin startproject pawnshop
<img width="1010" height="637" alt="image" src="https://github.com/user-attachments/assets/a5e66f85-ded2-4138-8d69-2d46e2b76742" />  


# 9. Kiểm tra file  
docker compose exec web ls   
<img width="1010" height="637" alt="image" src="https://github.com/user-attachments/assets/23dc73d1-02a2-4385-a612-3efa93551516" />m  

# 10.  Cấu hình database  
10.1. Mở file settings.py bằng lệnh nano django/pawnshop/settings.py  
10.2. Tìm DATABASES -> sửa thành như sau
 <img width="748" height="479" alt="image" src="https://github.com/user-attachments/assets/5f01391e-0407-4a3a-9c10-ba1d446fed17" />
10.3. tìm INSTALLED_APPS -> thêm 'management'
<img width="735" height="468" alt="image" src="https://github.com/user-attachments/assets/b360a06d-784c-49be-8f33-e964d82826d9" />
  
# 11. Tạo database model  
chạy lệnh: nano django/management/models.py
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/97cd5323-cf0f-45c3-85b2-9d7503e6d1e1" />  

# 12. Đăng ký model vào admin  
lệnh: nano /home/hue/camdo_hue/django/camdo/admin.py
<img width="1008" height="645" alt="image" src="https://github.com/user-attachments/assets/4eebe7d8-c912-44c9-8447-8ba7a9d4d7b4" />  

# 13. Tạo migration  
lệnh tạo docker compose exec web python manage.py makemigrations
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/06a09dab-5f8b-499a-b906-70a0e26a9ac8" />  
13.1. Apply database   
lệnh docker compose exec web python manage.py migrate
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/24091c20-d184-4cc5-aea0-c5e1d9b25d35" />    

# 14. Tạo superuser  
lệnh docker compose exec web python manage.py createsuperuser
<img width="1009" height="647" alt="image" src="https://github.com/user-attachments/assets/efa0020e-8657-4bf9-90db-b28d65968245" />
14.1. Thêm khách hàng
<img width="1774" height="970" alt="image" src="https://github.com/user-attachments/assets/02283691-a78a-4839-93d5-f7c7220e3350" />
14.2. Thêm tài sản
<img width="1799" height="970" alt="image" src="https://github.com/user-attachments/assets/01837d67-1362-4b2b-92dc-66aa2607db9d" />
14.3. Thêm phiếu cầm đồ
<img width="1764" height="967" alt="image" src="https://github.com/user-attachments/assets/5fd7077e-7069-48f7-a6ae-e7efa8bcb98f" />

# 15. Test PHP admin  
truy cập địa chỉ http://IP_UBUNTU:8081
<img width="1663" height="976" alt="image" src="https://github.com/user-attachments/assets/9de1020b-936d-4e22-b40d-f029e0508e38" />
15.1. Kiểm tra bảng khách hàng
<img width="780" height="436" alt="image" src="https://github.com/user-attachments/assets/8f88fb42-21e0-4622-b4d6-86acd4ea313f" />  
<img width="780" height="441" alt="image" src="https://github.com/user-attachments/assets/ed141965-e5f4-466b-9ce8-b70bcd92ef0f" />

Bảng Khách hàng (camdo_khachhang)
 
PK (id): Mỗi khách hàng khi được thêm vào hệ thống sẽ tự động nhận một ID (ví dụ: 1, 2, 3...).

Vai trò: Lưu trữ thông tin gốc của chủ tài sản.  
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/4976f31c-f3dd-4eb0-8283-8e9d0aaee27c" />    

15.2. kiểm tra bảng tài sản
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/c03708c2-1985-4b9b-b57d-0ca6dbed32bb" />   
<img width="780" height="434" alt="image" src="https://github.com/user-attachments/assets/1906c02d-3743-4fd0-ad0d-4bdc67759bc3" />   
Bảng Tài sản (camdo_taisan)  

PK (id): Định danh duy nhất cho món đồ được cầm (xe máy, điện thoại...).  

Vai trò: Lưu trữ thông tin về vật phẩm thế chấp.  
<img width="780" height="440" alt="image" src="https://github.com/user-attachments/assets/8531b5fc-1fcf-4878-82aa-82a4bec7bb71" />   

15.3. Kiểm tra bảng phiếu cầm đồ
<img width="780" height="437" alt="image" src="https://github.com/user-attachments/assets/715824f3-bd0c-4fce-aaa0-bbdf659eb56f" />  
<img width="780" height="437" alt="image" src="https://github.com/user-attachments/assets/52e6f2ef-00b2-4c01-8aff-e579165b43ae" />   
Bảng Phiếu cầm đồ (camdo_phieucamdo) - Bảng liên kết  

Đây là nơi thể hiện mối quan hệ 1-nhiều (One-to-Many): Một khách hàng có thể có nhiều phiếu cầm đồ.  

PK (id): Mã số của phiếu cầm.  

FK (khach_hang_id): Lưu ID của khách hàng từ bảng khachhang.  

FK (tai_san_id): Lưu ID của tài sản từ bảng taisan  
<img width="780" height="443" alt="image" src="https://github.com/user-attachments/assets/cbb8bc63-1f75-4eb7-bbe9-9cc2705326c4" />  
15.4.Kiểm chứng 
a)  Mục tiêu kiểm chứng  
- Chứng minh rằng:  
Trên Django Admin: Người dùng chọn Khách hàng/Tài sản bằng tên (Text).  
Trong MariaDB: Hệ thống chỉ lưu ID (Số) của bản ghi đó.

b) Các thành phần tham chiếu  
- Primary Key (PK) - Khóa chính   
+ Là mã định danh duy nhất của mỗi thực thể trong bảng của nó.  
Bảng Khách hàng: Cột id (Ví dụ: 1 đại diện cho Nguyễn Thị Kim Huệ).  
Bảng Tài sản: Cột id (Ví dụ: 1 đại diện cho Xe máy Honda).

 Foreign Key (FK) - Khóa ngoại  
+ Là cột trong bảng Phiếu cầm đồ dùng để trỏ tới PK của bảng khác.  
khach_hang_id: Lưu số ID từ bảng Khách hàng.  
tai_san_id: Lưu số ID từ bảng Tài sản.
<img width="780" height="441" alt="image" src="https://github.com/user-attachments/assets/dea22214-a83b-4f5a-bc00-2f4a70c7db16" />  

# 16. Tạo template HTML   
16.1. Tạo thư mục template bằng lệnh mkdir django/templates  
16.2. Cấu hình file home.html sudo nano django/templates/home.html
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/747ef7b4-76c7-4ec5-8e7c-524c43465abc" />  
16.3. Tạo file víews.py   
lệnh nano django/camdo/views.py
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/f5c0a353-cba8-49c3-b7b8-6d2b93658def" />  
16.4. Tạo file urls.py   
lệnh nano django/config/urls.py
<img width="780" height="439" alt="image" src="https://github.com/user-attachments/assets/72df202f-7977-4b5c-9d51-69e21557ccf8" />  

# 17. Test web  
truy cập http://ip_ubuntu:8000/
<img width="1779" height="963" alt="image" src="https://github.com/user-attachments/assets/f4368067-d99c-4335-9068-b4cb315f7452" />

# 18 Public django lên subdomain bằng claudfare tunnel  
18.1. Cài claudfared bằng lệnh sudo apt install cloudflared
<img width="904" height="583" alt="image" src="https://github.com/user-attachments/assets/1f334795-34cb-4d3a-b994-0a3a00d662b2" />
18.2. cài đặt sudo dpkg -i cloudflared-linux-amd64.deb
<img width="1013" height="641" alt="image" src="https://github.com/user-attachments/assets/169387fb-6db9-4ed6-806d-370195289ee0" />
18.3. kiểm tra bằng lệnh cloudflared --version
<img width="898" height="563" alt="image" src="https://github.com/user-attachments/assets/82f5e06c-0ad4-4606-859c-6b7be597d03a" />

# 19. Login 
chạy lệnh cloudflared tunnel login (sau khi chạy lệnh sẽ sinh ra 1 đường dẫn, copy đường dẫn đó lên trình duyệt để tiến hành login)
<img width="900" height="577" alt="image" src="https://github.com/user-attachments/assets/b874c354-5d5d-4f8b-8347-61d8561ca274" />
19.1. sau khi truy cập đường dẫn, chọn domain của bản thân -> Click "Authorize"
<img width="1544" height="728" alt="image" src="https://github.com/user-attachments/assets/b9021f7d-bf7b-4c99-b0c9-7c9d06256511" />
19.2 Sau khi click -> hệ thống sẽ báo "Success" đồng thời trong ubuntu sẽ tự động tạo ra file .pem
<img width="893" height="578" alt="image" src="https://github.com/user-attachments/assets/a5268ea9-db98-463b-b39c-0e56eeafe867" />
19.3. Vì website quản lý cầm đồ sẽ dùng chung id với website cũ nên chỉ cần tiến hành thêm hostname & service trong phần ingress
<img width="903" height="573" alt="image" src="https://github.com/user-attachments/assets/c3a992be-ad9b-4ae0-ad2d-a47a2d27f132" />

# 20. Chạy tunnel 
lệnh cloudflared tunnel --config /home/hue/.cloudflared/config.yml run
<img width="1011" height="636" alt="image" src="https://github.com/user-attachments/assets/d7c5678d-0c80-4974-b9cd-8f438a732773" />

20.1. Truy cập http://camdo.huek58.id.vn    
<img width="780" height="438" alt="image" src="https://github.com/user-attachments/assets/0e47bd41-5f2d-4384-9a5d-bd89f116ba28" />  

<img width="780" height="437" alt="image" src="https://github.com/user-attachments/assets/ea985359-f124-422d-a7bf-27faa9a4d185" />  




















 











