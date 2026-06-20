# Struktur Repo

```txt
invitation-frontend/
│
├── apps/
│   ├── landing/
│   ├── admin/
│   ├── dashboard/
│   ├── templates
│
├── packages/
│   ├── ui/
│   ├── api-client/
│   ├── types/
│   ├── hooks/
│   ├── utils/
│   ├── constants/
│   └── auth/
│
├── turbo.json
├── pnpm-workspace.yaml
└── package.json
```

---

# Apps

## 1. Landing App

```txt
apps/landing
```

Domain:

```txt
undanganlu.com
```

Tujuan:

* Marketing website
* SEO
* Akuisisi customer
* Menampilkan template
* Menampilkan pricing
* Register/Login

Fitur:

```txt
Home
Features
Pricing
Template Showcase
Testimonials
FAQ
Contact
Login
Register
```

---

## 2. Admin App

```txt
apps/admin
```

Domain:

```txt
admin.undanganlu.com
```

Role:

```txt
Super Admin
Admin
```

Fitur:

```txt
Dashboard
User Management
Invitation Management
Template Management
Revenue Report
Payment Report
Landing Content Management
Coupon Management
System Settings
```

Module:

```txt
dashboard/
users/
templates/
payments/
analytics/
settings/
cms/
```

---

## 3. User Dashboard App

```txt
apps/dashboard
```

Domain:

```txt
app.undanganlu.com
```

Role:

```txt
Customer
```

Fitur:

```txt
Dashboard
My Invitations
Template Selection
Guest Management
Gallery
Story Timeline
RSVP
Gift Information
Music
Theme Settings
Domain Settings
Transaction History
```

Module:

```txt
dashboard/
invitations/
guests/
gallery/
story/
rsvp/
gift/
music/
settings/
transactions/
```

---

# Invitation Apps

Ini website yang nanti dibuka tamu undangan.

---

## 4. Classic Template

```txt
apps/invitation-classic
```

Contoh URL:

```txt
classic.undanganlu.com/john-jane
```

Atau

```txt
john-jane.undanganlu.com
```

Fitur:

```txt
Cover
Bride & Groom
Story
Gallery
Location
RSVP
Gift
```

---

## 5. Modern Template

```txt
apps/invitation-modern
```

Fitur:

```txt
Animasi lebih banyak
Parallax
Video Background
Custom Theme
```

---

## 6. Premium Template

```txt
apps/invitation-premium
```

Fitur:

```txt
Advanced Animation
Custom Layout
Premium Components
```

---

# Shared Packages

---

## packages/ui

Komponen reusable.

```txt
Button
Input
Textarea
Modal
Drawer
Card
Badge
Table
Pagination
DatePicker
```

Dipakai:

```txt
Landing
Admin
Dashboard
Semua Template
```

---

## packages/api-client

Wrapper API.

```ts
AuthService
UserService
InvitationService
TemplateService
GuestService
PaymentService
```

Contoh:

```ts
AuthService.login()
InvitationService.create()
GuestService.getAll()
```

Semua app pakai package ini.

---

## packages/types

Shared types.

```ts
User
Invitation
Template
Guest
RSVP
Transaction
```

---

## packages/hooks

Reusable hooks.

```ts
useAuth()
useInvitation()
useDebounce()
usePagination()
```

---

## packages/utils

Utility.

```ts
formatDate()
formatCurrency()
slugify()
generateInvitationUrl()
```

---

## packages/constants

```ts
USER_ROLE
PAYMENT_STATUS
INVITATION_STATUS
PACKAGE_TYPE
```

---

## packages/auth

Auth helper.

```txt
Route Guard
Permission Guard
Token Handler
Session Handler
```

Dipakai:

```txt
Admin
Dashboard
```

---

# Struktur Internal Tiap App

Misal `apps/dashboard`:

```txt
dashboard/
│
├── src/
│   ├── app/
│   ├── modules/
│   │
│   ├── modules/invitations/
│   │   ├── pages/
│   │   ├── components/
│   │   ├── services/
│   │   ├── hooks/
│   │   └── types/
│   │
│   ├── modules/guests/
│   ├── modules/gallery/
│   ├── modules/rsvp/
│   └── modules/settings/
│
│   ├── layouts/
│   ├── providers/
│   └── middleware.ts
```

Jadi bukan berdasarkan:

```txt
components/
services/
hooks/
```

secara global yang lama-lama jadi berantakan.

Tapi berdasarkan **feature/module**:

```txt
modules/
├── invitations/
├── guests/
├── gallery/
├── rsvp/
└── settings/
```

yang jauh lebih gampang di-maintain ketika project mulai besar.

---

Kalau target lu SaaS undangan digital yang bisa berkembang, gua bakal pakai:

```txt
Frontend Monorepo (TurboRepo)
│
├── apps/
│   ├── landing
│   ├── admin
│   ├── dashboard
│   ├── invitation-classic
│   ├── invitation-modern
│   └── invitation-premium
│
└── packages/
    ├── ui
    ├── api-client
    ├── types
    ├── hooks
    ├── auth
    ├── utils
    └── constants
```

Karena struktur ini masih nyaman walaupun nanti lu punya 20+ template dan ribuan user.
