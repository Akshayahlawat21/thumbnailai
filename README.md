# thumbnailai
Overview
Thumb-io is a full-stack web application that leverages Google's Gemini AI to generate eye-catching thumbnails for videos. Simply enter your video title, select a style, aspect ratio, and color scheme — and let AI do the rest. No design skills required!

Features
🎨 AI-Powered Generation — Create professional thumbnails using Google Gemini AI
⚡ Fast Iterations — Generate multiple variations and choose what fits best
🖼️ Multiple Styles — Bold & Graphic, Minimalist, Cinematic, and more
📐 Aspect Ratio Options — Support for 16:9, 1:1, 4:3, and other formats
🎭 Color Schemes — Choose from curated color palettes
🔐 Google OAuth — Secure authentication with Google
💾 Save & Manage — Access all your generated thumbnails anytime
🌐 Community Gallery — Browse and get inspired by community creations
📱 Responsive Design — Works seamlessly on desktop and mobile
Tech Stack
Frontend
Technology	Name	Purpose
React	React 19	UI library for building interactive components
Vite	Vite	Lightning-fast build tool and dev server
TailwindCSS	TailwindCSS	Utility-first CSS framework for styling
Framer Motion	Framer Motion	Smooth animations and transitions
React Router	React Router	Client-side routing and navigation
Backend
Technology	Name	Purpose
Express	Express 5	Web server framework for REST APIs
MongoDB	MongoDB	NoSQL database for storing user data
Google Gemini	Google Gemini	AI-powered image generation
Cloudinary	Cloudinary	Image storage, optimization, and CDN
TypeScript	TypeScript	Type-safe JavaScript development
Zod	Zod	Schema validation for request/response data
Getting Started
Prerequisites
Node.js 18+
MongoDB instance (local or Atlas)
Google Cloud Console project with OAuth credentials
Cloudinary account
Google AI Studio API key (for Gemini)
Installation
Clone the repository

git clone https://github.com/vvk079/thumbnailio.git
cd thumbnailio
Install dependencies

# Install server dependencies
cd server
npm install

# Install client dependencies
cd ../client
npm install
Set up environment variables (see Environment Variables)

Run the development servers

# Terminal 1 - Start backend server
cd server
npm run server

# Terminal 2 - Start frontend
cd client
npm run dev
Open your browser

Frontend: http://localhost:5173
Backend: http://localhost:3000
Environment Variables
Create a .env file in the server directory:

# Database
MONGODB_URI=mongodb://localhost:27017/thumb-io

# Session
SESSION_SECRET=your-super-secret-session-key

# Google AI (Gemini)
GEMINI_API_KEY=your-gemini-api-key

# Cloudinary
CLOUDINARY_URL=cloudinary://api_key:api_secret@cloud_name

# Google OAuth
GOOGLE_OAUTH_CLIENT_ID=your-google-client-id
GOOGLE_OAUTH_CLIENT_SECRET=your-google-client-secret
GOOGLE_OAUTH_REDIRECT_URL=http://localhost:3000/api/v1/auth/google/callback

# Optional
CLIENT_URL=http://localhost:5173
NODE_ENV=development
PORT=3000
Usage
Sign in with your Google account
Navigate to the Generate page
Enter your video title
Select your preferred style, aspect ratio, and color scheme
Add any additional details or prompts (optional)
Click Generate and wait for your AI thumbnail
Download or save to your collection
Project Structure
thumbnailio/
├── client/                 # React frontend
│   ├── src/
│   │   ├── assets/         # Static assets & constants
│   │   ├── components/     # Reusable UI components
│   │   ├── configs/        # API configuration
│   │   ├── context/        # React context (Auth)
│   │   ├── data/           # Static data (features, pricing)
│   │   ├── pages/          # Page components
│   │   └── sections/       # Homepage sections
│   └── public/             # Public assets
│
├── server/                 # Express backend
│   ├── src/
│   │   ├── config/         # App configuration
│   │   ├── controllers/    # Route handlers
│   │   ├── middlewares/    # Auth & validation
│   │   ├── models/         # Mongoose schemas
│   │   └── routes/         # API routes
│   └── api/                # Vercel serverless entry
│
└── README.md
API Endpoints
Method	Endpoint	Description
POST	/api/v1/auth/google	Initiate Google OAuth
GET	/api/v1/auth/google/callback	OAuth callback
POST	/api/v1/thumbnail/generate	Generate new thumbnail
GET	/api/v1/user/thumbnail/:id	Get specific thumbnail
GET	/api/v1/user/thumbnails	Get user's thumbnails
Deployment
Both client and server are configured for Vercel deployment:

client/vercel.json — Frontend deployment config
server/vercel.json — Backend serverless config
Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

Fork the repository
Create your feature branch (git checkout -b feature/amazing-feature)
Commit your changes (git commit -m 'Add some amazing feature')
Push to the branch (git push origin feature/amazing-feature)
Open a Pull Request
