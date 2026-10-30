# Session14_Ex02 – Hybrid Workflow & Cloud Sync

## 1. Báo cáo phân tích I/O

### 1.1. Luồng dữ liệu khi nhấn Ctrl + S

Khi lập trình viên nhấn `Ctrl + S` trong VS Code, dữ liệu đi qua các bước sau:

1.  **Input:** Lập trình viên sửa code và nhấn `Ctrl + S`.
    
2.  **Local Storage:** File được lưu vào SSD trên máy tính.
    
3.  **Cloud Sync:** Phần mềm đồng bộ phát hiện thay đổi và tải file lên Cloud.
    
4.  **Cloud Storage:** File được cập nhật trên dịch vụ lưu trữ trực tuyến.
    
5.  **Output:** Biểu tượng tích xanh xuất hiện khi file đã đồng bộ thành công theo trạng thái của dịch vụ.
    

### 1.2. Vấn đề với thư mục node_modules

Thư mục `node_modules` chứa nhiều file thư viện được cài đặt bằng npm. Nếu đồng bộ toàn bộ thư mục này, quá trình đồng bộ có thể chậm, tiêu tốn dung lượng Cloud và gây quá tải.

**Cách xử lý:** Loại trừ `node_modules` khỏi Cloud Sync, nhưng vẫn đồng bộ source code và các file cần thiết như `package.json` và `package-lock.json`.

Khi cần cài lại thư viện, lập trình viên chạy:

```
npm install
```

Lệnh này cài đặt lại các thư viện được khai báo trong file quản lý dự án.

## 2. Thiết kế Hybrid Workflow

### 2.1. Sơ đồ tổ chức thư mục Cloud

```
Cloud/
└── Projects/
    └── SmartFood/
        ├── Code/
        │   ├── src/
        │   ├── package.json
        │   ├── package-lock.json
        │   └── .gitignore
        ├── Docs/
        │   ├── README.md
        │   └── report.md
        └── Assets/
            ├── images/
            ├── icons/
            └── designs/
```

Thư mục `node_modules` không đưa vào vùng đồng bộ Cloud.

### 2.2. Quy trình đồng bộ

1.  Lưu source code trên SSD Local để chỉnh sửa và chạy chương trình nhanh.
    
2.  Đồng bộ các thư mục `Code`, `Docs` và `Assets` lên Cloud.
    
3.  Thêm `node_modules` vào file `.gitignore` để Git không đưa thư mục này vào các commit thông thường.
    
4.  Không đồng bộ `node_modules` lên Cloud; khi cần, sử dụng `npm install` để tạo lại thư mục.
    
5.  Bật **Files On-Demand** trên OneDrive để các file ít dùng có thể chỉ lưu trực tuyến, giúp tiết kiệm dung lượng SSD. Khi cần sử dụng, file sẽ được tải xuống thiết bị.
    

Hybrid Workflow giúp lập trình viên chạy code nhanh trên SSD, bảo vệ source code trên Cloud và tiết kiệm dung lượng máy tính bằng Files On-Demand. Việc loại trừ `node_modules` giúp giảm số lượng file cần đồng bộ mà vẫn giữ lại các file cần thiết để cài đặt lại thư viện.
