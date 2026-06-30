# Sync — A Modern Full-Stack Social Networking Platform

**Sync** is a premium, developer-focused, full-stack social networking platform designed to bring people together. Developed as a modern MERN-stack application, Sync facilitates real-time user interaction, connection request management, daily email reminders, image uploads, and post sharing.

---

## 🚀 Key Features

- **Robust User Authentication**: Fully integrated with **Clerk Auth** for seamless social sign-on and email verification.
- **Dynamic Post Feed**: Create, view, and interact with posts containing rich text and multi-image uploads.
- **24-Hour Stories**: Share temporary updates with your network that automatically expire after 24 hours.
- **Interactive Messaging**: Real-time chatting, connection status updates, and notification of unseen messages.
- **Connection Management**: Send, accept, or reject connection requests with global community members.
- **Background Jobs**: Integrated with **Inngest** to handle asynchronous tasks like deleting expired stories, sending connection request emails, and sending daily summaries.
- **Premium Media Hosting**: Fully configured to handle image storage and streaming via **ImageKit**.
- **Responsive Layout**: Stunning, desktop-to-mobile visual experience built using React and TailwindCSS.

---

## 🛠️ Tech Stack

### Frontend (Client)
- **Framework**: React 19 (Vite-powered)
- **Styling**: Tailwind CSS v4.0 (Modern styling engine)
- **State Management**: Redux Toolkit & React Redux
- **Routing**: React Router DOM v7
- **Authentication**: Clerk React
- **Icons**: Lucide React
- **Notifications**: React Hot Toast

### Backend (Server)
- **Runtime**: Node.js & Express
- **Database**: MongoDB (via Mongoose)
- **Async Execution**: Inngest
- **Authentication Middleware**: Clerk Express
- **Email Dispatch**: Nodemailer
- **Media CDN**: ImageKit
- **File Uploads**: Multer

---

## 📁 Repository Structure

```
sync-full-stack/
├── client/                 # React frontend application
│   ├── src/                # Component files, pages, and redux state logic
│   ├── public/             # Static public assets
│   ├── package.json        # Frontend configuration and scripts
│   └── vite.config.js      # Vite build configuration
├── server/                 # Express REST API & background workers
│   ├── configs/            # Database and SMTP transporter configs
│   ├── controllers/        # Request handlers for API routes
│   ├── models/             # Mongoose schemas (User, Post, Story, etc.)
│   ├── routes/             # Express routes
│   ├── inngest/            # Event-driven functions and background pipelines
│   └── package.json        # Backend configuration and scripts
└── README.md               # Main project documentation
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Node.js (v18 or higher)
- MongoDB Connection URI
- Clerk Developer Credentials
- ImageKit API Credentials
- SMTP Server Credentials (e.g., Mailtrap, Gmail app password)
- Inngest Dev Server

### Step 1: Clone the Repository
```bash
git clone https://github.com/garv3143/sync.git
cd sync
```

### Step 2: Configure Client Environments
Navigate to the `client/` directory, create a `.env` file, and populate the following keys:
```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_BACKEND_URL=http://localhost:4000
```

Install dependencies:
```bash
cd client
npm install
```

### Step 3: Configure Server Environments
Navigate to the `server/` directory, create a `.env` file, and populate:
```env
PORT=4000
MONGODB_URI=your_mongodb_connection_uri
CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
IMAGEKIT_PUBLIC_KEY=your_imagekit_public_key
IMAGEKIT_PRIVATE_KEY=your_imagekit_private_key
IMAGEKIT_URL_ENDPOINT=your_imagekit_url_endpoint
SENDER_EMAIL=your_smtp_sender_email
SENDER_PASSWORD=your_smtp_sender_password
FRONTEND_URL=http://localhost:5173
```

Install dependencies:
```bash
cd server
npm install
```

---

## 🏃 Running the Application

To run the application locally, you will need three terminal instances:

### 1. Start the Backend API Server
```bash
cd server
npm run server
```

### 2. Start the Inngest Dev Server (For background functions)
Inngest triggers functions locally via the Dev Server, which forwards events to your backend:
```bash
npx inngest-cli@latest dev -u http://localhost:4000/api/inngest
```

### 3. Start the Frontend Dev Server
```bash
cd client
npm run dev
```

Open your browser and navigate to `http://localhost:5173`.

---

## 👤 Developer

Developed and maintained by **[Garv Modi](https://github.com/garv3143)**. Feel free to reach out for collaboration or feedback!
