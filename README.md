# 🎬 Movie Time & Ticket Booking System

A full-stack web application for browsing movies, booking tickets, and managing showtimes. Built with React.js frontend and Express.js backend with MongoDB database.

## ✨ Features

### 👥 For Users
- 🔍 Browse and search movies
- 🎟️ Book movie tickets with seat selection
- 📅 View available showtimes
- 📜 Access booking history
- 👤 Manage user profile
- 💬 Live chat support with admin
- 📧 Contact support form

### 👨‍💼 For Admins
- 🎬 Full movie management (Create, Edit, Delete)
- ⏰ Manage showtimes and pricing
- 📊 View all bookings and users
- 💬 Real-time chat with users
- 📨 Respond to support messages
- 📈 Dashboard with analytics

## 🛠️ Tech Stack

### Frontend
- **React.js** - UI library
- **Material-UI (MUI)** - Component library
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **Socket.io Client** - Real-time chat
- **Context API** - State management

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **JWT** - Authentication
- **Bcrypt.js** - Password hashing
- **Socket.io** - Real-time communication

## 📋 Prerequisites

- Node.js (v14 or higher)
- MongoDB Atlas account or local MongoDB
- npm or yarn

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/Komal-Disanayaka/Movie-Times-And-Ticket-Booking-Web-Application.git
cd Movie-Times-And-Ticket-Booking-Web-Application
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create `.env` file in backend directory:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secure_jwt_secret_here
```

Start the backend server:

```bash
# Development mode with auto-reload
npm run dev

# Production mode
npm start
```

Backend runs on `http://localhost:5000`

### 3. Frontend Setup

```bash
cd frontend
npm install
```

(Optional) Create `.env` file in frontend directory:

```env
REACT_APP_API_URL=http://localhost:5000/api
```

Start the frontend application:

```bash
npm start
```

Frontend runs on `http://localhost:3000`

### 4. Seed Admin Account (Optional)

```bash
cd backend
node seedAdmin.js
```

Default admin credentials:
- Email: `admin@movietime.com`
- Password: `admin123`

## 📁 Project Structure

```
Movie-Ticket-Booking-System/
├── backend/
│   ├── config/          # Database configuration
│   ├── controllers/     # Request handlers
│   ├── middleware/      # Auth & validation middleware
│   ├── models/          # MongoDB schemas
│   ├── routes/          # API routes
│   ├── server.js        # Entry point
│   └── package.json
│
├── frontend/
│   ├── public/          # Static files
│   ├── src/
│   │   ├── components/  # Reusable components
│   │   ├── context/     # React Context
│   │   ├── pages/       # Page components
│   │   ├── services/    # API services
│   │   ├── App.js       # Main component
│   │   └── index.js     # Entry point
│   └── package.json
│
├── ARCHITECTURE.md      # System architecture documentation
├── LICENSE             # MIT License
└── README.md           # This file
```

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile (protected)

### Movies
- `GET /api/movies` - Get all movies
- `GET /api/movies/:id` - Get movie by ID
- `POST /api/movies` - Create movie (admin)
- `PUT /api/movies/:id` - Update movie (admin)
- `DELETE /api/movies/:id` - Delete movie (admin)

### Showtimes
- `GET /api/showtimes` - Get all showtimes
- `GET /api/showtimes/movie/:movieId` - Get showtimes by movie
- `POST /api/showtimes` - Create showtime (admin)
- `PUT /api/showtimes/:id` - Update showtime (admin)
- `DELETE /api/showtimes/:id` - Delete showtime (admin)

### Bookings
- `POST /api/bookings` - Create booking (protected)
- `GET /api/bookings/user` - Get user bookings (protected)
- `GET /api/bookings` - Get all bookings (admin)

### Support
- `POST /api/support` - Send support message
- `GET /api/support` - Get all messages (admin)
- `PUT /api/support/:id/reply` - Reply to message (admin)

### Chat
- `GET /api/chat/messages` - Get chat messages
- `POST /api/chat/messages` - Send chat message
- `Socket.io` - Real-time chat events

## 🔐 Authentication & Authorization

The application uses JWT (JSON Web Tokens) for authentication:

1. User registers or logs in
2. Server generates JWT token
3. Token stored in localStorage
4. Token sent with each API request
5. Server validates token and authorizes access

**User Roles:**
- `user` - Regular users (can book tickets)
- `admin` - Administrators (full access)

## 🎨 Key Pages

| Route | Page | Access |
|-------|------|--------|
| `/` | Home | Public |
| `/movies` | Movie Listing | Public |
| `/movies/:id` | Movie Details | Public |
| `/login` | Login | Public |
| `/register` | Register | Public |
| `/profile` | User Profile | Protected |
| `/booking-history` | Booking History | Protected |
| `/payment/:showtimeId` | Payment | Protected |
| `/contact` | Contact Us | Public |
| `/support` | Support Chat | Protected |
| `/admin` | Admin Panel | Admin Only |

## 🧪 Testing

The application can be tested manually:

1. Register a new user account
2. Browse available movies
3. Select a movie and showtime
4. Complete booking with seat selection
5. View booking history
6. Test chat functionality
7. Login as admin to manage content

## 🚢 Deployment

### Backend Deployment (Heroku/Railway)

```bash
cd backend
# Ensure environment variables are set
# Deploy using platform-specific commands
```

### Frontend Deployment (Vercel/Netlify)

```bash
cd frontend
npm run build
# Deploy the build folder
```

### Environment Variables

**Backend:**
- `PORT` - Server port
- `MONGO_URI` - MongoDB connection string
- `JWT_SECRET` - JWT signing secret

**Frontend:**
- `REACT_APP_API_URL` - Backend API URL

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Komal Dissanayaka**

- GitHub: [@Komal-Disanayaka](https://github.com/Komal-Disanayaka)

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For support, email or create an issue in the GitHub repository.

## 🙏 Acknowledgments

- Material-UI for the beautiful components
- MongoDB Atlas for database hosting
- All contributors and testers

---

⭐ Star this repo if you find it helpful!
