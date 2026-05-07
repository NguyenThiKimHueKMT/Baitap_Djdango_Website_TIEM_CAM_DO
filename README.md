# Baitap_Djdango_Website_TIEM_CAM_DO
Baitap_Djdango_Website_TIEM_CAM_DO  
PHÁT TRIỂN ỨNG DỤNG VỚI MÃ NGUỒN MỞ (DJANGO + XÂY DỰNG WEBSITE QUẢN LÝ TIỆM CẦM ĐỒ)  
HỌ TÊN: NGUYỄN THỊ KIM HUỆ   
LỚP: K58KTP  
MSSV: K225480106026  
1: CHUẨN BỊ UBUNTU  
Kiểm tra phiên bản Docker docker --version  
Kiểm tra phiên bản Docker Compose docker compose version  
<img width="814" height="472" alt="image" src="https://github.com/user-attachments/assets/27776bd4-9c71-42ef-b4dc-b9c18266d204" />   

2: TẠO PROJECT  
Bước 1: Tạo thư mục mkdir camdo_project  
Bước 2: Vào thư mục cd camdo_project  
<img width="811" height="474" alt="image" src="https://github.com/user-attachments/assets/839e9922-6ad0-4958-b9c8-c3846075d223" />  
Bước 3: Tạo thư mục django trong camdo_project    

3: TẠO DOCKERFILE  
Bước 1: Vào thư mục Django: cd django  
Bước 2: Tạo file DockerFile nano Dockerfile  
Bước 3: Thêm nội dung cho File dockerfile  
<img width="1103" height="638" alt="image" src="https://github.com/user-attachments/assets/61363ca6-5e55-419a-abe2-300b37f4edb8" />    

4: TẠO FILE requirements.txt  
Bước 1: Tạo file requirements.txt nano requirements.txt  
Bước 2: Dán nội dung sau  
<img width="1113" height="640" alt="image" src="https://github.com/user-attachments/assets/3c7df328-9358-4525-bad1-aa8b2593752f" />    

5. Tạo file docker-compose.yml  
5.1. về thư mục gốc bằng lệnh cd ..  
5.2. chạy lệnh sudo nano docker-compose.yml  
<img width="1112" height="646" alt="image" src="https://github.com/user-attachments/assets/68ab70fa-191e-47da-909b-2170290e5c3a" />  
6. Run hệ thống
chạy lệnh: docker compose up --build    
<img width="1014" height="636" alt="image" src="https://github.com/user-attachments/assets/2e115274-f8c8-4511-b1b3-6218078e0690" />  

7: TẠO DJANGO PROJECT  
Bước1: chạy lệnh docker compose exec django django-admin startproject pawnshop .   

8: TẠO APP  
Bước 1: Chạy lệnh docker compose exec django_app python manage.py startapp management  
Bước 2: Kiểm tra ls django  

9: CẤU HÌNH DATABASE  
Bước 1: Mở settings.py nano django/pawnshop/settings.py  
Bước 2: Tìm DATABASES -> Trong nano bấm Ctrl + M -> Gõ DATABASES    
Bước 3: Tìm đến và sửa thành như sau  
<img width="1010" height="637" alt="image" src="https://github.com/user-attachments/assets/23dc73d1-02a2-4385-a612-3efa93551516" />m  

10: TẠO DATABASE MODEl  
Bước 1: Mở model.py bằng lệnh nano django/management/models.py  
Bước 2: Thêm nội dung  
11: TẠO MIGRATION  
Chạy lệnh: docker compose exec django python manage.py makemigrations  
12: TẠO SUPERUSER
Chạy lệnh docker compose exec django python manage.py createsuperuser  
13: CHẠY WEB  
Truy cập django admin bằng địa chỉ: http://IP_UBUNTU:8000/admin  
14: TEST CRUD  
Bước 1: Thêm dữ liệu  
Thêm khách hàng  











