# TCK React Learning – Quản lý Nghi lễ

Ứng dụng web quản lý và tra cứu nghi lễ (rituals) được xây dựng bằng React + TypeScript, phục vụ mục đích học tập và thực hành.

---

## 📦 Công nghệ sử dụng

| Thành phần | Công nghệ |
|------------|-----------|
| Framework | React 19 + TypeScript |
| Build tool | Vite 7 |
| Styling | Tailwind CSS 4 |
| Routing | React Router v7 |
| State | Zustand |
| Data fetching | TanStack React Query |
| Form | React Hook Form + Zod |
| HTTP client | Axios |
| UI components | Radix UI, shadcn/ui |
| Toast | Sonner |

---

## 🏗️ Cấu trúc dự án

```
src/
├── app/              # Cấu hình app, router, providers
├── features/         # Các module theo tính năng
│   ├── auth/         # Đăng nhập, đăng ký
│   ├── dashboard/    # Trang tổng quan admin
│   ├── landing/      # Trang chủ, hero
│   ├── rituals/      # Nghi lễ – catalog, chi tiết, CRUD
│   └── users/        # Hồ sơ, quản lý người dùng
├── shared/           # Component, layout, hooks dùng chung
├── lib/              # Axios, env, utils
└── styles/           # CSS toàn cục
```

---

## ✨ Tính năng chính

### Công khai (không cần đăng nhập)

- **Trang chủ** (`/`) – Hero, giới thiệu
- **Danh mục nghi lễ** (`/rituals`) – Tìm kiếm, lọc, phân trang
- **Chi tiết nghi lễ** (`/rituals/:id`) – Xem thông tin chi tiết
- **Đăng nhập / Đăng ký** (`/login`, `/register`)

### Yêu cầu đăng nhập

- **Hồ sơ cá nhân** (`/profile`)

### Chỉ Admin

- **Dashboard** (`/admin`) – Trang tổng quan
- **Quản lý nghi lễ** (`/admin/rituals`) – Danh sách, thêm, sửa
- **Quản lý người dùng** (`/admin/users`)

---

## 📋 Mô hình Nghi lễ (Ritual)

Mỗi nghi lễ gồm:

- Thông tin cơ bản: tên, ngày âm/dương lịch, thời gian thực hiện
- Độ khó: dễ, trung bình, khó, rất khó
- Mô tả, nội dung, tham khảo
- Danh mục, lời cầu nguyện, media, lễ vật, tags
- Trạng thái nổi bật (isHot)

---

## 🚀 Chạy dự án

### Yêu cầu

- Node.js
- pnpm (hoặc npm/yarn)

### Cài đặt

```bash
pnpm install
```

### Biến môi trường

Tạo file `.env` với nội dung:

```
VITE_API_URL=http://localhost:3000
```

### Chạy development

```bash
pnpm dev
```

### Build production

```bash
pnpm build
```

### Xem bản build

```bash
pnpm preview
```

---

## 📁 Scripts

| Lệnh | Mô tả |
|------|-------|
| `pnpm dev` | Chạy dev server |
| `pnpm build` | Build production |
| `pnpm lint` | Chạy ESLint |
| `pnpm preview` | Xem bản build |

---

## 🔐 Phân quyền

- **GuestRoute**: Chỉ cho phép khi chưa đăng nhập (login, register)
- **ProtectedRoute**: Yêu cầu đăng nhập
- **ProtectedRoute (admin)**: Chỉ cho phép role `admin` truy cập `/admin/*`

---

## 📄 License

Private – Dự án học tập.
