# 🌿 Echoes of Us: Family Archive & Legacy Tree

Echoes of Us is a modern family tree and legacy preservation platform. It allows families to document their history, map their lineage, and leave "Legacy Letters" — stories sealed until a specific future moment (like a birthday or a passing).

### 🚀 Live Application
*   **Frontend:** [https://family-tree-frontend-mocha.vercel.app](https://family-tree-frontend-mocha.vercel.app)
*   **Backend API:** [https://family-tree-backend-production-2630.up.railway.app](https://family-tree-backend-production-2630.up.railway.app)

---

### ✨ Key Features
*   **Interactive Family Tree:** Map relationships across generations with a dynamic, zoomable interface.
*   **Legacy Letters:** Write stories that stay sealed until a specific age or event (Death/Age triggers).
*   **Automated Reveals:** A background cron job automatically "unlocks" legacy letters and notifies family members via email.
*   **Family Groups:** Create private spaces to collaborate and share memories with specific branches of the family.
*   **Media Archive:** Attach photos, voice notes, and videos to stories for a rich historical record.

---

### 🛠 Tech Stack
*   **Frontend:** React (Vite), Tailwind CSS, Axios, React Router.
*   **Backend:** Node.js, Express.
*   **Database:** PostgreSQL (Railway).
*   **Cache:** Redis (Railway) for performance.
*   **Storage:** Cloudinary (Permanent media storage).
*   **Email:** Nodemailer (Gmail SMTP).

---

### 📡 Deployment Architecture
*   **Frontend Hosting:** Vercel (Auto-proxy to Railway API).
*   **Backend Hosting:** Railway.
*   **Database:** Hosted PostgreSQL on Railway.

---

### 🛠 Local Development
1.  **Clone the repositories:**
    ```bash
    git clone https://github.com/Catarina-Tornadoe/family-tree-backend.git
    git clone https://github.com/Catarina-Tornadoe/family-tree-frontend.git
    ```
2.  **Install dependencies:**
    ```bash
    npm install
    cd family-tree-ui && npm install
    ```
3.  **Setup Environment Variables:** Create a `.env` file in the root with `DATABASE_URL`, `REDIS_URL`, `JWT_SECRET`, and Cloudinary credentials.
4.  **Run Dev Server:**
    ```bash
    npm run dev
    ```

---

### 📜 Database Initialization
The full database schema is available in `schema.sql`. For existing databases, ensure the `has_seen_tutorial` column is added:
```sql
ALTER TABLE users ADD COLUMN IF NOT EXISTS has_seen_tutorial BOOLEAN DEFAULT FALSE;
```

---
*Created with ❤️ to preserve stories for generations to come.*
