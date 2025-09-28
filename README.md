# 📦 Dự án Quản Lý Hệ Thống

Repo này là **repo chính** dùng để quản lý 2 repo con:

- [qlht-backend](./qlht-backend) – Backend (Node.js/Express, MongoDB, …)  
- [qlht-frontend](./qlht-frontend) – Frontend (React.js, Redux, …)  

---

## 🛠 Cách clone dự án

Repo này sử dụng **Git Submodules** để liên kết tới 2 repo con.  
Khi clone, hãy chạy:

```bash
git clone --recurse-submodules <URL_REPO_MAIN>
```

Nếu đã clone nhưng thư mục submodule (`qlht-backend`, `qlht-frontend`) trống, hãy chạy:

```bash
git submodule update --init --recursive
```

---

## 📂 Cấu trúc thư mục

```
my-project/
│
├── qlht-backend/       # Submodule: Backend repo
├── qlht-frontend/      # Submodule: Frontend repo
├── docker-compose.yml  # File docker-compose dùng để chạy cả stack
└── README.md           # Tài liệu này
```

---

## 🚀 Chạy dự án bằng Docker

Dự án hỗ trợ chạy toàn bộ backend + frontend bằng **docker-compose**.  

1. Cài đặt Docker & Docker Compose  
2. Chạy lệnh:

```bash
docker-compose up --build
```

3. Truy cập:  
   - **Frontend**: http://localhost:3000  
   - **Backend API**: http://localhost:5000  

---

## 🔄 Cập nhật submodules

Nếu backend hoặc frontend có thay đổi mới và bạn muốn pull về:

```bash
# Vào từng submodule và pull code mới nhất
cd qlht-backend
git pull origin main

cd ../qlht-frontend
git pull origin main

# Quay lại repo chính, commit lại reference
cd ..
git add qlht-backend qlht-frontend
git commit -m "Update submodules to latest commits"
git push
```

---

## 👨‍💻 Cách làm việc với repo

- **Backend developer**: code trong repo `qlht-backend`  
- **Frontend developer**: code trong repo `qlht-frontend`  
- **Repo chính**: quản lý CI/CD, docker-compose, tài liệu, script setup  

---

## ✅ Checklist cho thành viên mới

1. Clone repo chính kèm submodules (`--recurse-submodules`)  
2. Cài đặt Docker  
3. Chạy `docker-compose up --build`  
4. Truy cập app qua browser  

---

## 📄 License

Dự án dùng cho mục đích nội bộ. Không chia sẻ bên ngoài nếu chưa được phép.  
