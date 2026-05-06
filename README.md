# Golf Bookr ⛳

Golf Bookr is a comprehensive golf course management and tee time booking platform. It features a modern React-based frontend, a robust Node.js/Express backend with MySQL, and an integrated AI chatbot powered by Google's Gemini API.

## 🚀 Features

### For Users
- **Dynamic Booking System**: Real-time tee time availability and booking.
- **AI Chatbot**: Intelligent golf assistant powered by Gemini AI to help with rules, bookings, and course info.
- **User Profiles**: Manage personal information and view booking history.
- **Responsive Design**: Modern UI built with Material UI and Bootstrap, supporting light/dark modes.

### For Admins
- **Dashboard**: Real-time statistics and booking overview using Chart.js.
- **Course Management**: Add and update golf course details, facilities, and difficulty levels.
- **Tee Time Manager**: Create and manage available slots for different dates.
- **Booking Viewer**: Track and manage all customer bookings.

## 🛠️ Tech Stack

- **Frontend**: React 18, Vite, Material UI (MUI), Bootstrap 5, Chart.js, Axios.
- **Backend**: Node.js, Express, MySQL (mysql2), JWT Authentication, WebSocket (`ws`).
- **AI Integration**: Google Generative AI (Gemini Pro).
- **Database**: MySQL with indexing for optimized performance.

## 📋 Prerequisites

- Node.js (v16+)
- MySQL (v8+)
- Gemini API Key (from Google AI Studio)

## ⚙️ Setup & Installation

### 1. Clone the repository
```bash
git clone https://github.com/TayZa9/Golf-Booking.git
cd golf-booking
```

### 2. Database Setup
1. Create a MySQL database named `golf_bookr`.
2. Import the schema found in `server/db/schema.sql`.
   ```bash
   mysql -u root -p golf_bookr < server/db/schema.sql
   ```

### 3. Server Configuration
1. Navigate to the server directory:
   ```bash
   cd server
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file based on `.env.example` and fill in your database credentials and Gemini API Key:
   ```env
   PORT=3000
   DB_HOST=localhost
   DB_USER=root
   DB_PASSWORD=your_password
   DB_NAME=golf_bookr
   JWT_SECRET=your_jwt_secret
   GEMINI_API_KEY=your_gemini_api_key
   ```
4. (Optional) Initialize admin accounts:
   ```bash
   node scripts/createAdmin.js
   ```
5. Start the server:
   ```bash
   npm run dev
   ```

### 4. Client Configuration
1. Navigate to the client directory:
   ```bash
   cd ../client
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file:
   ```env
   VITE_API_URL=http://localhost:3000/api/v1
   ```
4. Start the development server:
   ```bash
   npm run dev
   ```

## 🔐 Admin Credentials (Default)
If you ran `node scripts/createAdmin.js`, you can use:
- **Email**: `manager@golfbookr.com`
- **Password**: `manager123`

## 📡 API Endpoints (v1)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/auth/signup` | Register new user |
| POST | `/api/v1/auth/login` | Login user |
| GET | `/api/v1/bookings` | Get available tee times |
| POST | `/api/v1/bookings` | Book a tee time |
| POST | `/api/v1/chat` | Chat with Gemini AI |
| GET | `/api/v1/admin/dashboard` | Admin stats |

## 📄 License
This project is licensed under the MIT License.
