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

10.  Cấu hình database  
10.1. Mở file settings.py bằng lệnh nano django/pawnshop/settings.py  
10.2. Tìm DATABASES -> sửa thành như sau
 <img width="748" height="479" alt="image" src="https://github.com/user-attachments/assets/5f01391e-0407-4a3a-9c10-ba1d446fed17" />
10.3. tìm INSTALLED_APPS -> thêm 'management'
<img width="735" height="468" alt="image" src="https://github.com/user-attachments/assets/b360a06d-784c-49be-8f33-e964d82826d9" />
  
11. Tạo database model  
chạy lệnh: nano django/management/models.py
<img width="1013" height="642" alt="image" src="https://github.com/user-attachments/assets/7f96a8de-b546-44c6-988c-a32578ef2f04" />  

12. Đăng ký model vào admin  
lệnh: nano /home/hue/camdo_hue/django/camdo/admin.py
<img width="1008" height="645" alt="image" src="https://github.com/user-attachments/assets/4eebe7d8-c912-44c9-8447-8ba7a9d4d7b4" />  

13. Tạo migration  
lệnh tạo docker compose exec web python manage.py makemigrations
<img width="746" height="508" alt="image" src="https://github.com/user-attachments/assets/20d37de7-28af-4495-81ab-95c523d9d57f" />  
13.1. Apply database   
lệnh docker compose exec web python manage.py migrate
<img width="1011" height="641" alt="image" src="https://github.com/user-attachments/assets/62048bce-1b22-4f66-83fd-5234d655ac4e" />  

14. Tạo superuser  
lệnh docker compose exec web python manage.py createsuperuser
<img width="1009" height="647" alt="image" src="https://github.com/user-attachments/assets/efa0020e-8657-4bf9-90db-b28d65968245" />
14.1. Thêm khách hàng
<img width="1774" height="970" alt="image" src="https://github.com/user-attachments/assets/02283691-a78a-4839-93d5-f7c7220e3350" />
14.2. Thêm tài sản
<img width="1799" height="970" alt="image" src="https://github.com/user-attachments/assets/01837d67-1362-4b2b-92dc-66aa2607db9d" />
14.3. Thêm phiếu cầm đồ
<img width="1764" height="967" alt="image" src="https://github.com/user-attachments/assets/5fd7077e-7069-48f7-a6ae-e7efa8bcb98f" />

15. Test PHP admin  
truy cập địa chỉ http://IP_UBUNTU:8081
<img width="1663" height="976" alt="image" src="https://github.com/user-attachments/assets/9de1020b-936d-4e22-b40d-f029e0508e38" />
15.1. Kiểm tra bảng khách hàng
<img width="1673" height="963" alt="image" src="https://github.com/user-attachments/assets/1ff1a261-82dc-4911-83ef-300bb11ba350" />
15.2. kiểm tra bảng tài sản
<img width="1757" height="966" alt="image" src="https://github.com/user-attachments/assets/8c0bbe64-7fd2-4cfd-b287-4637cbb054a0" />
15.3. Kiểm tra bảng phiếu cầm đồ
<img width="1790" height="967" alt="image" src="https://github.com/user-attachments/assets/566a39bc-22cf-4a25-9183-8487855dce61" />

16. Tạo template HTML  
16.1. Tạo thư mục template bằng lệnh mkdir django/templates  
16.2. Cấu hình file home.html sudo nano django/templates/home.html
<img width="1020" height="642" alt="image" src="https://github.com/user-attachments/assets/d910e6c5-7752-44a7-a570-1ab644ff7885" />
16.3. Tạo file víews.py   
lệnh nano django/camdo/views.py
<img width="1017" height="637" alt="image" src="https://github.com/user-attachments/assets/b9eb0e06-02b4-4e2e-8177-1376163d8a99" />
16.4. Tạo file urls.py   
lệnh nano django/config/urls.py
<img width="1017" height="649" alt="image" src="https://github.com/user-attachments/assets/5dce4564-2041-4f2b-a922-81760a1fb303" />

18. Test web  
truy cập http://ip_ubuntu:8000/
<img width="1779" height="963" alt="image" src="https://github.com/user-attachments/assets/f4368067-d99c-4335-9068-b4cb315f7452" />
18: Public django lên subdomain bằng claudfare tunnel  
18.1. Cài claudfared bằng lệnh sudo apt install cloudflared
<img width="904" height="583" alt="image" src="https://github.com/user-attachments/assets/1f334795-34cb-4d3a-b994-0a3a00d662b2" />
18.2. cài đặt sudo dpkg -i cloudflared-linux-amd64.deb
<img width="1013" height="641" alt="image" src="https://github.com/user-attachments/assets/169387fb-6db9-4ed6-806d-370195289ee0" />
18.3. kiểm tra bằng lệnh cloudflared --version
<img width="898" height="563" alt="image" src="https://github.com/user-attachments/assets/82f5e06c-0ad4-4606-859c-6b7be597d03a" />

19. Login 
chạy lệnh cloudflared tunnel login (sau khi chạy lệnh sẽ sinh ra 1 đường dẫn, copy đường dẫn đó lên trình duyệt để tiến hành login)
<img width="900" height="577" alt="image" src="https://github.com/user-attachments/assets/b874c354-5d5d-4f8b-8347-61d8561ca274" />
19.1. sau khi truy cập đường dẫn, chọn domain của bản thân -> Click "Authorize"
<img width="1544" height="728" alt="image" src="https://github.com/user-attachments/assets/b9021f7d-bf7b-4c99-b0c9-7c9d06256511" />
19.2 Sau khi click -> hệ thống sẽ báo "Success" đồng thời trong ubuntu sẽ tự động tạo ra file .pem
<img width="893" height="578" alt="image" src="https://github.com/user-attachments/assets/a5268ea9-db98-463b-b39c-0e56eeafe867" />
19.3. Vì website quản lý cầm đồ sẽ dùng chung id với website cũ nên chỉ cần tiến hành thêm hostname & service trong phần ingress
<img width="903" height="573" alt="image" src="https://github.com/user-attachments/assets/c3a992be-ad9b-4ae0-ad2d-a47a2d27f132" />

20. Chạy tunnel 
lệnh cloudflared tunnel --config /home/hue/.cloudflared/config.yml run
<img width="1011" height="636" alt="image" src="https://github.com/user-attachments/assets/d7c5678d-0c80-4974-b9cd-8f438a732773" />

20.1. Truy cập http://camdo.huek58.id.vn  
<img width="1779" height="963" alt="image" src="https://github.com/user-attachments/assets/76a437cf-e344-4d58-a1df-11aaca0fa345" />  




















 











