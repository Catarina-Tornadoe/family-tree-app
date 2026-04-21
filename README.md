# 🌿 Hirloom — Family Archive

> *Every family has a story. Hirloom is where it lives.*

Hirloom is a private digital archive for families — a place to preserve voices, photographs, stories, and memories across generations. It is built on the belief that the most important histories are not the ones in textbooks, but the ones passed quietly between grandparents and grandchildren, across kitchen tables and long phone calls.

---

## 🔗 Live Demo

> [VERCEL](https://family-tree-frontend-mocha.vercel.app/)

---

## 📸 Screenshots

> Screenshots will be added upon deployment

| Dashboard | Family Tree | Person Portal |
|---|---|---|
| `coming soon` | `coming soon` | `coming soon` |

| Stories Feed | Write a Story | Settings |
|---|---|---|
| `coming soon` | `coming soon` | `coming soon` |

---

## 🌱 The Vision

Most family memories are fragile. They live in aging photo albums, in the minds of elders, in WhatsApp threads that get buried. When someone passes, those stories often go with them.

Hirloom changes that.

It gives families a shared, structured space to:
- Build an interactive family tree spanning multiple generations
- Record and store voice notes, photos, and videos tied to real people
- Write stories — ordinary and extraordinary — that will outlast the people who lived them
- Leave **legacy letters**: sealed messages that open only when a condition is met — a birthday, a death, a coming of age

It is not a social network. It is not a public platform. It is a private archive, built for the long term, designed to feel like a family heirloom.

---

## ✨ Key Features

### 🌳 Interactive Family Tree
- Visual, zoomable tree built with react-d3-tree
- Click any node to open that person's full archive portal
- Supports complex relationships — parents, siblings, partners, step-parents, half-siblings
- Living and deceased members styled distinctly
- Bridge nodes highlight people who connect multiple family branches

### 👤 Person Portals
- Every person in the tree has their own dedicated portal
- Tabbed interface: Info, Stories, Gallery, Audio, Video
- Profile photo, biography, birth details, relationship map
- All media tied to that person in one place

### 📖 Stories & Voice Notes
- Rich text story creation with title, date, tags, and visibility control
- In-browser voice recording — record a story directly, no external app needed
- Drag-and-drop file attachments — photos, audio, video, PDFs
- Stories can be marked **private**, **family-only**, or **public**

### ✉️ Legacy Letters
- Write a sealed letter to be opened in the future
- Reveal conditions: immediately, at a specific age, upon death, or manually released
- Sealed letters appear as envelope icons — contents hidden until conditions are met
- On-death letters automatically unseal when a person is marked as deceased

### 🏡 Family Groups
- Organise your archive into named family branches
- Granular access control: owner, admin, contributor, viewer
- Invite family members via email with branded invite links
- Each group has its own access scope — stories shared to a group are only visible to members

### 🔍 People Search with Duplicate Detection
- Smart search with confidence scoring before adding a new person
- Matches on name, date of birth, and email hint
- Prevents accidental duplicate entries in the tree

### 🎨 Appearance
- Warm parchment light theme and deep dark mode
- Cormorant Garamond typography throughout
- Amber/gold design system — feels like a family heirloom, not a tech product

---

## 🛠 Tech Stack

### Backend
| Layer | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express.js |
| Database | PostgreSQL |
| Caching | Redis (node-cache fallback) |
| Authentication | JWT (JSON Web Tokens) |
| File handling | Multer (local) → Cloudinary (production) |
| Email | Nodemailer + Gmail SMTP |
| Media streaming | HTTP range requests (206 Partial Content) |

### Frontend
| Layer | Technology |
|---|---|
| Framework | React (Vite) |
| Styling | Tailwind CSS |
| Routing | React Router v6 |
| Tree visualisation | react-d3-tree |
| HTTP client | Axios |
| Voice recording | MediaRecorder API |
| State management | React Context (Auth + Theme) |

### Infrastructure (Production)
| Service | Provider |
|---|---|
| Frontend hosting | Vercel |
| Backend hosting | Railway |
| Database hosting | Railway PostgreSQL |
| Media storage | Cloudinary |
| Domain | TBD |

---

## 🗄 Database Schema (Overview)

```
users               — registered accounts
people              — every person in the archive (linked or unlinked to a user)
relationships       — family connections between people
stories             — written stories and legacy letters
media               — photos, audio, video attached to stories or people
family_groups       — named family branches
family_group_members — people belonging to a group
family_group_access  — user permissions per group (owner/admin/contributor/viewer)
family_group_invites — email invitations with token-based acceptance
story_access        — fine-grained story sharing
```

---

## 🚀 Running Locally

### Prerequisites
- Node.js v18+
- PostgreSQL 14+
- Redis (or Memurai on Windows)
- A Gmail account with App Password enabled

### Backend setup
```bash
git clone https://github.com/Catarina-Tornadoe/family-tree-backend
cd family_tree
npm install
```

Create a `.env` file:
```
PORT=3000
DATABASE_URL=postgresql://USER:PASSWORD@localhost:5432/family_tree
JWT_SECRET=your_jwt_secret_here
APP_URL=http://localhost:5173
GMAIL_USER=your@gmail.com
GMAIL_APP_PASSWORD=your_app_password
REDIS_URL=redis://localhost:6379
```

Run database migrations (create tables in pgAdmin or psql using your schema).

```bash
npm run dev
```

### Frontend setup
```bash
git clone https://github.com/Catarina-Tornadoe/family-tree-frontend
cd family-tree-ui
npm install
npm run dev
```

Visit `http://localhost:5173`

---

## 🗺 Roadmap

- [x] Authentication (register, login, JWT)
- [x] Family tree with relationship management
- [x] Person portals with tabbed media
- [x] Story creation with voice recording
- [x] Legacy letters with reveal conditions
- [x] Family groups with invite system
- [x] Stories feed with filtering and tags
- [x] Dark mode
- [x] Redis caching layer
- [x] Cloudinary media storage
- [x] Legacy letter email notifications (cron-based)
- [ ] Progressive Web App (PWA) support
- [ ] Android app (Capacitor)
- [ ] Tag management
- [ ] Public family landing pages

---

## 👤 Built By Nonye Ezeh (@Catarina-Tornadoe)

Designed and developed as a personal project — a full-stack family archive application built from scratch.

**Stack decisions, architecture, database design, UI/UX, and all feature development** by the author.

> *Built for every family that has more history than it has space to keep it.*

---

## 📬 Contact

Have questions or want to collaborate?

- GitHub: [@Catarina-Tornadoe](https://github.com/Catarina-Tornadoe)
- Email: `nonyeconstace61@gmail.com`

---

<p align="center">
  <em>In memory of every voice that deserved to be recorded.</em>
</p>
