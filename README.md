# 🚀 Sales CRM — AI Marathon Practice Project

A full-stack Sales CRM ERP web app built with Node.js, Express, MySQL, and vanilla HTML/CSS/JS.

---

## 📁 Project Structure

```
sales-crm/
├── backend/
│   ├── config/
│   │   └── db.js           ← MySQL connection
│   ├── routes/
│   │   ├── leads.js        ← Leads API
│   │   ├── customers.js    ← Customers API
│   │   ├── orders.js       ← Orders API
│   │   └── dashboard.js    ← Stats API
│   ├── server.js           ← Express app entry point
│   ├── schema.sql          ← Database schema + sample data
│   ├── package.json
│   └── .env.example        ← Copy to .env and fill in values
├── frontend/
│   ├── css/
│   │   └── style.css
│   └── pages/
│       ├── dashboard.html
│       ├── leads.html
│       ├── customers.html
│       └── orders.html
├── Procfile                ← For Railway deployment
└── .gitignore
```

---

## ⚙️ Local Setup (Step by Step)

### 1. Set up the Database
Open MySQL Workbench or terminal and run:
```bash
mysql -u root -p < backend/schema.sql
```

### 2. Configure Environment
```bash
cd backend
cp .env.example .env
```
Open `.env` and fill in your MySQL password.

### 3. Install Dependencies
```bash
cd backend
npm install
```

### 4. Run the App
```bash
npm run dev       # development (auto-restarts)
# OR
npm start         # production
```

### 5. Open in Browser
```
http://localhost:3000
```

---

## 🌐 Deploy to Railway

1. Push your project to GitHub
2. Go to https://railway.app and sign in
3. Click **New Project → Deploy from GitHub**
4. Select your repo
5. Add a **MySQL** plugin from the Railway dashboard
6. Go to **Variables** and add:
   - `DB_HOST` → from Railway MySQL plugin
   - `DB_USER` → from Railway MySQL plugin
   - `DB_PASSWORD` → from Railway MySQL plugin
   - `DB_NAME` → `sales_crm`
   - `DB_PORT` → `3306`
7. Railway will auto-deploy — copy your public URL!
8. Run your schema.sql on the Railway MySQL instance using the Railway shell

---

## 🔌 API Endpoints

| Method | Endpoint                  | Description            |
|--------|---------------------------|------------------------|
| GET    | /api/leads                | Get all leads          |
| POST   | /api/leads                | Create a lead          |
| PUT    | /api/leads/:id            | Update a lead          |
| DELETE | /api/leads/:id            | Delete a lead          |
| POST   | /api/leads/:id/convert    | Convert lead → customer|
| GET    | /api/customers            | Get all customers      |
| PUT    | /api/customers/:id        | Update a customer      |
| DELETE | /api/customers/:id        | Delete a customer      |
| GET    | /api/orders               | Get all orders         |
| POST   | /api/orders               | Create an order        |
| PUT    | /api/orders/:id           | Update an order        |
| DELETE | /api/orders/:id           | Delete an order        |
| GET    | /api/dashboard            | Get summary stats      |
