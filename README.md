# 🎉 Invitation Frontend (Monorepo)

Frontend monorepo untuk SaaS undangan digital dibangun menggunakan:

* Next.js (Apps)
* TurboRepo
* npm Workspaces
* TypeScript
* TailwindCSS

---

# 🧱 Struktur Project

```txt
invitation-frontend/
│
├── apps/
│   ├── landing/                # Marketing website (undanganlu.com)
│   ├── admin/                  # Admin panel (admin.undanganlu.com)
│   ├── dashboard/              # User dashboard (app.undanganlu.com)
│   ├── templates/              # Invitation templates (public facing)
│
├── packages/
│   ├── ui/                     # Shared UI components
│   ├── api-client/            # API wrapper layer
│   ├── types/                 # Shared TypeScript types
│   ├── hooks/                 # Shared React hooks
│   ├── utils/                 # Utility functions
│   ├── constants/             # Shared constants
│   └── auth/                  # Auth utilities & guards
│
├── turbo.json
├── package.json
└── README.md
```

---

# 🚀 Apps Overview

## 1. Landing Page

**Port:** `3002`

Fungsi:

* Marketing website
* SEO landing page
* Pricing & features
* Template showcase
* Login & register

---

## 2. Admin Panel

**Port:** `3000`

Role:

* Super Admin
* Admin

Fungsi:

* User management
* Template management
* Payment & revenue
* CMS landing page
* System settings

---

## 3. User Dashboard

**Port:** `3001`

Role:

* Customer

Fungsi:

* Manage invitations
* Guest management
* Gallery & story
* RSVP system
* Gift & payment tracking
* Theme & domain settings

---

## 4. Templates (Public Apps)

**Port:** `3003`

Dipakai oleh tamu undangan.

Contoh:

* classic
* modern
* premium

Fungsi:

* Render invitation page
* Public access via URL slug
* RSVP & guest view

---

# 📦 Shared Packages

## UI (`packages/ui`)

Reusable UI components seperti:

* Button
* Input
* Modal
* Card
* Table
* DatePicker

---

## API Client (`packages/api-client`)

Centralized API layer seperti:

```ts
AuthService.login()
InvitationService.create()
GuestService.getAll()
```

---

## Types (`packages/types`)

Shared TypeScript types:

* User
* Invitation
* Guest
* RSVP
* Transaction

---

## Hooks (`packages/hooks`)

Reusable hooks seperti:

* useAuth
* useInvitation
* useDebounce
* usePagination

---

## Utils (`packages/utils`)

Helper functions seperti:

* formatDate
* formatCurrency
* slugify
* generateInvitationUrl

---

## Constants (`packages/constants`)

Global constants seperti:

* USER_ROLE
* PAYMENT_STATUS
* INVITATION_STATUS

---

## Auth (`packages/auth`)

Authentication utilities seperti:

* Route guards
* Permission checks
* Token handling
* Session management

---

# 🧠 Architecture Principle

Project ini menggunakan **module-based architecture per app**, bukan global folder.

Contoh di dashboard:

```txt
modules/
├── invitations/
├── guests/
├── gallery/
├── rsvp/
└── settings/
```

Tujuannya:

* scalable
* mudah maintenance
* tidak berantakan saat project besar

---

# ⚙️ Running Project

Install dependencies:

```bash
npm install
```

Run semua apps:

```bash
npm run dev
```

Build semua apps:

```bash
npm run build
```

---

## 🌐 Port Mapping

Saat menjalankan monorepo, masing-masing app akan berjalan di port berikut:

```txt
admin        → localhost:3000
dashboard    → localhost:3001
landing      → localhost:3002
templates    → localhost:3003
```

---

## ▶️ Run per app (optional)

Kalau mau jalanin satu app saja:

### Admin

```bash
npm run dev --workspace=@invitation/admin
```

### Dashboard

```bash
npm run dev --workspace=@invitation/dashboard
```

### Landing

```bash
npm run dev --workspace=@invitation/landing
```

### Templates

```bash
npm run dev --workspace=@invitation/templates
```

---

# 🧩 Philosophy

* Shared logic masuk `packages/`
* Business logic masuk `apps/`
* UI reusable di `packages/ui`
* Semua app saling independent tapi terhubung via workspace

---

# 📌 Notes

* Gunakan npm workspace (jangan install per-app)
* Gunakan Turbo untuk build orchestration
* Semua shared module wajib di `packages/`

---

# 🚀 Goal

Membangun SaaS undangan digital yang scalable:

* Multiple template system
* Multi-tenant architecture
* High customization
* SEO-friendly public invitations
