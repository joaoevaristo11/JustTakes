# 🎬 JustTakes - Your Hub of Reviews

A modern, full-stack web application for discovering and sharing honest reviews on movies, series, books, and video games. Built with React and Node.js, JustTakes provides an engaging platform for entertainment enthusiasts to express their opinions and explore community ratings.

## 🌟 Features

### ✅ Implemented
- **User Authentication System**
  - Secure registration and login with JWT
  - Email verification system with resend functionality
  - Refresh token rotation for enhanced security
  - Password hashing with bcrypt
  - Remember me functionality
  
- **Reviews System**
  - Create and view reviews with ratings (1-5 stars)
  - User profile integration
  - Real-time review display
  - Authenticated user reviews

- **Landing Page**
  - Dynamic hero section with automatic image slider
  - Smooth animations using Framer Motion
  - Responsive navigation bar
  - Multiple sections: About, Categories, Reviews, Contact

- **Contact System**
  - Contact form with CSV storage
  - Excel export functionality
  - Message tracking and management

- **UI/UX Features**
  - Modern, animated interface
  - Toast notifications
  - Responsive design
  - Loading states and error handling
  - Password visibility toggle

### 🚧 In Development
- **Movies Page** - Browse and filter movies catalog
- **User Profile Page** - User dashboard and settings
- **Advanced Search** - Filter reviews by category and rating
- **Social Features** - Like, comment, and share reviews

## 🛠️ Tech Stack

### Frontend
- **React 19** - Modern UI library with latest features
- **Vite 7** - Lightning-fast build tool and dev server
- **React Router DOM 7** - Client-side routing
- **Framer Motion 12** - Smooth animations and transitions
- **Swiper 12** - Touch-enabled slider component
- **React Icons 5** - Comprehensive icon library
- **ExcelJS 4** - Excel file generation

### Backend
- **Node.js** - JavaScript runtime
- **Express 4** - Fast web framework
- **MongoDB + Mongoose 8** - NoSQL database and ODM
- **JWT (jsonwebtoken 9)** - Secure authentication
- **bcrypt 5** - Password hashing
- **Nodemailer 7** - Email sending service
- **CORS** - Cross-origin resource sharing
- **dotenv** - Environment configuration

### Development Tools
- **ESLint 9** - Code linting
- **Nodemon 3** - Auto-restart dev server
- **Vercel** - Deployment platform

## 📁 Project Structure

```
mymediashelf/
├── src/                          # Frontend source
│   ├── components/
│   │   ├── MainPage/            # Landing page components
│   │   │   ├── HomePage.jsx
│   │   │   ├── NavBar.jsx
│   │   │   ├── Authentication.jsx
│   │   │   ├── AboutSection.jsx
│   │   │   ├── CategoriesSection.jsx
│   │   │   ├── ReviewsSection.jsx
│   │   │   ├── ContactSection.jsx
│   │   │   └── VerifyEmail.jsx
│   │   ├── MoviesPage/          # Movies page (in progress)
│   │   └── AddReviewForm.jsx
│   ├── App.jsx
│   └── main.jsx
│
├── mymediashelf-server/         # Backend API
│   ├── controllers/
│   │   └── authController.js
│   ├── middleware/
│   │   └── authMiddleware.js
│   ├── models/
│   │   ├── User.js
│   │   ├── Reviews.js
│   │   └── Contact.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── reviewRoutes.js
│   │   └── contactRoutes.js
│   ├── utils/
│   │   ├── generateVerificationToken.js
│   │   ├── createVerificationLink.js
│   │   └── sendVerificationEmail.js
│   └── server.js
│
└── public/                      # Static assets
    └── images/
```

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **MongoDB** (local or Atlas cloud)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd mymediashelf
   ```

2. **Install frontend dependencies**
   ```bash
   npm install
   ```

3. **Install backend dependencies**
   ```bash
   cd mymediashelf-server
   npm install
   cd ..
   ```

4. **Configure environment variables**
   
   Create a `.env` file in the `mymediashelf-server/` directory:
   ```env
   # MongoDB Connection
   MONGO_URI=your_mongodb_connection_string
   
   # JWT Configuration
   JWT_SECRET=your_jwt_secret_key
   JWT_REFRESH_SECRET=your_jwt_refresh_secret_key
   
   # Email Configuration (Nodemailer)
   EMAIL_USER=your_email@example.com
   EMAIL_PASS=your_email_password
   BREVO_API_KEY=your_brevo_api_key  # If using Brevo
   
   # Server Configuration
   PORT=5000
   FRONTEND_URL=http://localhost:5173
   ```

### Running the Application

1. **Start the backend server**
   ```bash
   cd mymediashelf-server
   npm start
   ```
   
   For development with auto-reload:
   ```bash
   npm run dev
   ```

2. **Start the frontend** (in a new terminal)
   ```bash
   npm run dev
   ```

3. **Access the application**
   - Frontend: `http://localhost:5173`
   - Backend API: `http://localhost:5000`

## 📝 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user (protected)
- `GET /api/auth/verify` - Verify email
- `POST /api/auth/resend-verification` - Resend verification email
- `POST /api/auth/refresh` - Refresh access token
- `POST /api/auth/logout` - User logout (protected)

### Reviews
- `GET /api/reviews` - Get all reviews
- `POST /api/reviews` - Create review (protected)
- `GET /api/reviews/:id` - Get specific review
- `PUT /api/reviews/:id` - Update review (protected)
- `DELETE /api/reviews/:id` - Delete review (protected)

### Contact
- `POST /api/contact` - Submit contact form
- `GET /api/contact` - Get all messages (admin)

## 🎯 Roadmap & Future Improvements

### High Priority
- [ ] Complete Movies Page with TMDb API integration
- [ ] User Profile page with edit capabilities
- [ ] Review editing and deletion by author
- [ ] Image upload for reviews

### Features to Add
- [ ] Rating system improvements (half-stars, detailed categories)
- [ ] Search and filter functionality
- [ ] Categories expansion (Books, Video Games)
- [ ] User following system
- [ ] Review comments and discussions
- [ ] Bookmarking/Favorites system
- [ ] Admin dashboard
- [ ] Content moderation tools

### Technical Improvements
- [ ] Migrate to TypeScript for better type safety
- [ ] Implement comprehensive testing (Jest, React Testing Library)
- [ ] Add API rate limiting
- [ ] Implement pagination for reviews
- [ ] Add image optimization and CDN
- [ ] Implement Redis for caching
- [ ] Add WebSocket for real-time features
- [ ] Improve error handling and logging
- [ ] Add API documentation (Swagger/OpenAPI)
- [ ] Implement CI/CD pipeline
- [ ] Add performance monitoring
- [ ] Implement SEO optimization

### Security Enhancements
- [ ] Add two-factor authentication
- [ ] Implement CAPTCHA on forms
- [ ] Add account recovery flow
- [ ] Enhance password requirements
- [ ] Add security audit logging

### UX/UI Improvements
- [ ] Dark/Light theme toggle
- [ ] Accessibility improvements (WCAG 2.1)
- [ ] Mobile app version
- [ ] Progressive Web App (PWA) features
- [ ] Improved loading states and skeletons
- [ ] Internationalization (i18n)

## 🐛 Known Issues

- Some security vulnerabilities in dependencies (run `npm audit fix`)
- MongoDB connection error handling needs improvement
- Email verification requires proper SMTP configuration
- CSS organization could be improved with CSS modules or styled-components

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is currently unlicensed. Please contact the repository owner for usage rights.

## 👥 Authors

- **Your Name** - *Initial work*

## 🙏 Acknowledgments

- React team for the amazing framework
- MongoDB for the flexible database
- Framer Motion for smooth animations
- All open-source contributors

---

**Note:** This is an active development project. Features and documentation are continuously being updated. For the latest changes, check the commit history.
