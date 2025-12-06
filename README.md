# 📖 CoWrite - Collaborative Storytelling Platform

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

**A community-driven platform where writers collaborate to create amazing stories together!**

</div>

---

## 🌟 Overview

**CoWrite** is a full-stack web application that enables collaborative storytelling. Writers can create stories, invite contributions from the community, vote on the best additions, and build narratives together. Whether you're crafting a fantasy epic, a thrilling mystery, or a heartfelt romance, CoWrite brings writers together to create something unique.

---

## ✨ Features

### 📚 Story Management
- **Create Stories** - Start a new story with a title, genre, and opening text
- **Multiple Genres** - Support for Fantasy, Sci-Fi, Romance, Thriller, Mystery, Horror, Comedy, Drama, Adventure, and Historical genres
- **Open/Closed States** - Control when your story accepts new contributions
- **Search & Filter** - Find stories by title, author, genre, or status

### ✍️ Collaborative Contributions
- **Add Contributions** - Submit your continuation of any open story
- **Voting System** - Upvote or downvote contributions to highlight the best additions
- **Selection by Author** - Story creators can select the best contributions to add to the canonical storyline
- **Contribution Tracking** - View all your contributions across different stories

### 🔔 Notifications
- **Real-time Alerts** - Get notified when your contribution is selected
- **Story Updates** - Stay informed about the stories you're involved in

### 👤 User Features
- **User Authentication** - Secure registration and login with JWT tokens
- **User Profiles** - View your created stories and contributions
- **My Stories** - Dashboard to manage all your created stories
- **My Contributions** - Track all contributions you've made

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|------------|---------|
| **Node.js** | Runtime environment |
| **Express.js 5** | Web framework |
| **MongoDB** | Database |
| **Mongoose** | ODM for MongoDB |
| **JWT** | Authentication |
| **bcryptjs** | Password hashing |
| **CORS** | Cross-origin resource sharing |

### Frontend
| Technology | Purpose |
|------------|---------|
| **React 19** | UI library |
| **Vite** | Build tool |
| **React Router DOM** | Client-side routing |
| **Tailwind CSS 4** | Styling |
| **Framer Motion** | Animations |
| **Axios** | HTTP client |

---

## 📁 Project Structure

```
CoWrite/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   │   ├── contributionController.js
│   │   │   ├── notificationController.js
│   │   │   ├── storyController.js
│   │   │   └── userController.js
│   │   ├── middlewares/
│   │   │   └── auth.js
│   │   ├── models/
│   │   │   ├── contribution.model.js
│   │   │   ├── notification.model.js
│   │   │   ├── story.model.js
│   │   │   └── user.model.js
│   │   └── routes/
│   │       ├── contributionRoutes.js
│   │       ├── notificationRoutes.js
│   │       ├── storyRoutes.js
│   │       └── userRoutes.js
│   ├── index.js
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── Components/
│   │   │   ├── Header/
│   │   │   └── Footer/
│   │   ├── Context/
│   │   ├── layout/
│   │   │   └── Layout.jsx
│   │   ├── pages/
│   │   │   ├── CreateStoryPage.jsx
│   │   │   ├── HomePage.jsx
│   │   │   ├── LoginPage.jsx
│   │   │   ├── MyContributions.jsx
│   │   │   ├── MyStories.jsx
│   │   │   ├── NotificationIcon.jsx
│   │   │   ├── RegisterPage.jsx
│   │   │   ├── StoryDetails.jsx
│   │   │   ├── StoryPage.jsx
│   │   │   └── UserProfile.jsx
│   │   ├── router/
│   │   │   ├── ProtectedRoute.jsx
│   │   │   └── Router.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   └── package.json
│
├── .gitignore
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v18 or higher recommended)
- **MongoDB** (local installation or MongoDB Atlas account)
- **npm** or **yarn**

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/CoWrite.git
   cd CoWrite
   ```

2. **Set up the Backend**
   ```bash
   cd backend
   npm install
   ```

3. **Configure environment variables**
   
   Create a `.env` file in the `backend` directory:
   ```env
   PORT=3000
   MONGO_URI=mongodb://localhost:27017/cowrite
   JWT_SECRET=your_super_secret_jwt_key
   ```

4. **Set up the Frontend**
   ```bash
   cd ../frontend
   npm install
   ```

5. **Configure the API URL**
   
   Update `frontend/axiosConfig.js` if your backend runs on a different port:
   ```javascript
   import axios from 'axios';
   
   axios.defaults.baseURL = 'http://localhost:3000';
   
   export default axios;
   ```

### Running the Application

1. **Start the Backend Server**
   ```bash
   cd backend
   npm run dev
   ```
   The server will start at `http://localhost:3000`

2. **Start the Frontend Development Server**
   ```bash
   cd frontend
   npm run dev
   ```
   The frontend will start at `http://localhost:5173`

---

## 📡 API Endpoints

### Stories
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/stories` | Get all stories |
| `GET` | `/api/stories/:id` | Get story by ID |
| `POST` | `/api/stories` | Create a new story |
| `POST` | `/api/stories/:id/contribute` | Add contribution to story |
| `POST` | `/api/stories/:id/select/:contributionId` | Select a contribution |
| `PATCH` | `/api/stories/:id/status` | Update story status |
| `GET` | `/api/stories/user?user=:userId` | Get stories by user |

### Contributions
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/contributions/story/:storyId` | Get contributions for a story |
| `GET` | `/api/contributions/user/:userId` | Get contributions by user |
| `POST` | `/api/contributions/:id/upvote` | Upvote a contribution |
| `POST` | `/api/contributions/:id/downvote` | Downvote a contribution |

### Users
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/users/register` | Register a new user |
| `POST` | `/api/users/login` | Login user |

### Notifications
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/notifications/:userId` | Get user notifications |

---

## 🎮 How It Works

1. **Create an Account** - Register with your name, email, and password
2. **Start or Join a Story** - Create your own story or contribute to existing ones
3. **Write Your Part** - Add your creative continuation to any open story
4. **Vote on Contributions** - Help the community identify the best additions
5. **Build Together** - Watch as the story evolves with selected contributions
6. **Get Notified** - Receive alerts when your contributions are selected

---

## 📸 Pages Overview

| Page | Route | Description |
|------|-------|-------------|
| Home | `/` | Browse all stories with search functionality |
| Login | `/login` | User authentication |
| Create Story | `/create` | Create a new story |
| Story Page | `/story/:id` | View story and add contributions |
| Story Details | `/full-story/:id` | View complete story content |
| My Stories | `/my-stories` | Manage your created stories |
| My Contributions | `/my-contributions` | View your contribution history |
| User Profile | `/profile/:id` | View user profile |

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

---

## 👨‍💻 Author

**Sajid Mujawar**

---

## 📄 License

This project is licensed under the ISC License.

---

## 🙏 Acknowledgments

- Thanks to all contributors who help make CoWrite better
- Inspired by the power of collaborative storytelling
- Built with ❤️ for the writing community

---

<div align="center">

**Happy Writing! 📝✨**

*Create stories together, one contribution at a time.*

</div>
