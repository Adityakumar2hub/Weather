# 🌤️ Weather Hub

Weather Hub is a full-stack weather forecasting web application that lets users search for weather information by city, view current conditions and forecasts, save favorite cities, and review search history.

The project combines a responsive **HTML/CSS/JavaScript frontend** with a **Node.js + Express.js backend**, **MongoDB/Mongoose** data storage, and a local JSON fallback store for improved reliability.

## ✨ Features

- 🌍 Search weather by city
- 🌡️ View current temperature and feels-like temperature
- 💧 Humidity and atmospheric pressure
- 💨 Wind speed and direction
- 👁️ Visibility and cloud coverage
- 🔺 Minimum and maximum temperature
- 📅 Multi-day weather forecast
- ⭐ Save and manage favorite cities
- 🔎 Store and view search history
- 👤 Create/select a user profile
- 🗄️ MongoDB integration with Mongoose
- 💾 Local JSON fallback storage when MongoDB is unavailable
- 🔌 REST API for weather, users, favorites, and search history
- 📱 Responsive user interface
- ⏳ Loading and error states
- ✅ Database connection status indicator
- ⚡ Quick-city search buttons

## 🛠️ Tech Stack

### Frontend
- HTML5
- CSS3
- Vanilla JavaScript

### Backend
- Node.js
- Express.js
- Axios
- CORS
- dotenv

### Database
- MongoDB
- Mongoose
- Local JSON fallback store

## 📁 Project Structure

```text
wapp/
│
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── weatherController.js
│   ├── data/
│   │   └── appdb.json
│   ├── models/
│   │   ├── Favorite.js
│   │   ├── User.js
│   │   └── Weather.js
│   ├── routes/
│   │   └── weatherRoutes.js
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
└── frontend/
    ├── index.html
    ├── script.js
    └── style.css
```

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd wapp
```

### 2. Install backend dependencies

```bash
cd backend
npm install
```

### 3. Configure environment variables

Create a `.env` file inside the `backend` folder based on `.env.example`.

Example:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/weather_app
WEATHER_API_KEY=your_api_key_here
```

Use the environment-variable names expected by `server.js` and `weatherController.js` in your project.

### 4. Start the backend

```bash
npm start
```

The backend will normally run at:

```text
http://localhost:5000
```

### 5. Open the frontend

You can open `frontend/index.html` directly in a browser, or use the **Live Server** extension in VS Code.

For the best experience, serve the frontend through a local web server while the backend is running.

## 🔌 API Endpoints

The backend exposes routes under:

```text
/api
```

### Health Check

```http
GET /api/health
```

### Weather

```http
GET /api/weather/:city
```

### User

```http
POST /api/users/register
GET /api/users/:userId
```

### Favorites

```http
GET /api/users/:userId/favorites
POST /api/users/:userId/favorites
DELETE /api/users/:userId/favorites/:city
```

### Search History

```http
GET /api/searches
```

## 🧪 How to Use

1. Open Weather Hub.
2. Create/save a user profile.
3. Search for a city such as **Mumbai, London, Tokyo, Paris, Sydney, or New York**.
4. View the current weather and forecast.
5. Save the city to favorites.
6. Refresh or revisit the Favorites section.
7. Check Search History to see previous searches.
8. Monitor the database status indicator to verify MongoDB or fallback storage.

## 💾 Database & Fallback Mode

Weather Hub is designed to work with MongoDB through Mongoose. The backend also includes a local JSON fallback mechanism.

If MongoDB cannot be reached, the application can switch to:

```text
backend/data/appdb.json
```

This fallback stores application data locally so core functionality can continue during development.

## 🔐 Environment & Security

Do not commit private credentials or API keys to GitHub.

Make sure your real `.env` file is included in `.gitignore` and publish only `.env.example` with placeholder values.

Example:

```gitignore
.env
node_modules/
```

## 📌 Current Limitations

- No full authentication system or password-based login
- Weather data depends on the configured weather API
- Frontend is a vanilla JavaScript application
- No automated test suite is currently configured
- Local fallback storage is intended mainly for development/demo use

## 🚀 Future Improvements

- Secure authentication with JWT
- User-specific dashboards
- Better MongoDB validation and indexing
- Weather charts and historical data
- Geolocation-based weather
- Interactive maps
- Automatic weather alerts and notifications
- Progressive Web App support
- Docker deployment
- Automated testing and CI/CD
- Production-grade API security and rate limiting

## 🎯 Project Objective

The objective of Weather Hub is to demonstrate a practical full-stack application that connects a responsive frontend with REST APIs and persistent data storage. It showcases concepts such as asynchronous JavaScript, API integration, CRUD operations, database connectivity, data caching, user data management, and responsive UI development.

## 📜 License

This project is intended for educational and portfolio purposes. Add your preferred open-source license here before publishing for public use.
