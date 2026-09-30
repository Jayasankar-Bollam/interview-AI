# Interview AI 🤖

Interview AI is a full-stack web application that helps candidates prepare for job interviews using AI.

The application takes a **job description, resume, and candidate details** and uses Google Gemini AI to generate a personalized interview preparation report.

## 🚀 Features

* User Registration and Login
* JWT-based Authentication
* Upload Resume PDF
* Job Description Input
* AI-powered Resume Analysis
* Job Match Score
* Technical Interview Questions
* Behavioral Interview Questions
* Skill Gap Analysis
* Personalized Preparation Roadmap
* AI-generated Resume
* Download Resume as PDF
* View Previous Interview Reports

## 🛠️ Technologies Used

### Frontend

* React.js
* Vite
* React Router
* Axios
* SCSS

### Backend

* Node.js
* Express.js
* JWT
* bcryptjs
* Multer
* pdf-parse
* Puppeteer

### Database

* MongoDB
* Mongoose

### AI

* Google Gemini API
* Zod
* zod-to-json-schema

## 📂 Project Structure

```text
interview-ai/
│
├── Backend/
│   ├── server.js
│   ├── package.json
│   │
│   └── src/
│       ├── config/
│       ├── controllers/
│       ├── middlewares/
│       ├── models/
│       ├── routes/
│       └── services/
│
├── Frontend/
│   ├── package.json
│   │
│   └── src/
│       ├── features/
│       ├── App.jsx
│       └── app.routes.jsx
│
└── README.md
```

## ⚙️ How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/interview-ai.git
```

```bash
cd interview-ai
```

### 2. Backend Setup

Go to the backend folder:

```bash
cd Backend
```

Install dependencies:

```bash
npm install
```

Create a `.env` file inside the `Backend` folder:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GOOGLE_GENAI_API_KEY=your_gemini_api_key
```

Start the backend:

```bash
npm run dev
```

Backend will run on:

```text
http://localhost:3000
```

### 3. Frontend Setup

Open another terminal:

```bash
cd Frontend
```

Install dependencies:

```bash
npm install
```

Start the frontend:

```bash
npm run dev
```

Frontend will normally run on:

```text
http://localhost:5173
```

## 🔑 Getting Gemini API Key

This project uses Google Gemini API for generating the interview report.

Create an API key from Google AI Studio:

https://aistudio.google.com/app/apikey

Add the key to:

```env
GOOGLE_GENAI_API_KEY=your_api_key
```

Don't upload your `.env` file or API key to GitHub.

## 🔄 How the Project Works

The basic flow of the application is:

```text
User
 ↓
Register / Login
 ↓
Enter Job Description
 ↓
Upload Resume
 ↓
Enter Self Description
 ↓
Backend receives the data
 ↓
Resume text is extracted
 ↓
Data is sent to Gemini AI
 ↓
AI generates interview report
 ↓
Report is stored in MongoDB
 ↓
Report is displayed in the frontend
```

## 🤖 AI Interview Report

After submitting the details, Gemini analyzes the candidate profile and job description.

The application generates:

### Match Score

Shows how closely the candidate's profile matches the given job description.

### Technical Questions

Generates technical questions based on the candidate's skills and the job requirements.

### Behavioral Questions

Generates questions related to communication, teamwork, projects, challenges, and previous experiences.

### Skill Gaps

Identifies technologies or skills that the candidate may need to improve for the target role.

### Preparation Roadmap

Creates a personalized preparation plan based on the identified skill gaps.

## 📄 Resume Processing

The application allows the user to upload a PDF resume.

The flow is:

```text
Resume PDF
 ↓
Multer
 ↓
PDF Text Extraction
 ↓
Resume Text
 ↓
Gemini AI
```

The extracted resume content is then used along with the job description for generating the interview report.

## 📑 AI Resume Generation

The project also includes an AI resume generation feature.

The flow is:

```text
Candidate Information
 ↓
Gemini AI
 ↓
HTML Resume
 ↓
Puppeteer
 ↓
PDF
 ↓
Download
```

This allows the user to generate a customized resume based on the target job.

## 🔐 Authentication

I used JWT-based authentication in this project.

During registration:
 
```text
User Password
 ↓
bcrypt
 ↓
Hashed Password
 ↓
MongoDB
```

During login:

```text
Email + Password
 ↓
Verify User
 ↓
Generate JWT
 ↓
Authentication Cookie
```

Protected routes use authentication middleware to verify the user before allowing access.

## 🔌 Main API Routes

### Authentication

```text
POST /api/auth/register
POST /api/auth/login
GET  /api/auth/logout
GET  /api/auth/get-me
```

### Interview

```text
POST /api/interview/
GET  /api/interview/
GET  /api/interview/report/:interviewId
POST /api/interview/resume/pdf/:interviewReportId
```

## 🧠 AI Response Structure

I used Zod to define the expected structure of the AI response.

The response contains information such as:

```text
Match Score
Technical Questions
Behavioral Questions
Skill Gaps
Preparation Plan
Job Title
```

This helps keep the AI response structured and easier to use in the frontend.

## 🗃️ Database

I used MongoDB with Mongoose.

The main collections/models are:

* User
* Interview Report
* Blacklist

Interview reports are connected to the logged-in user so that each user can access their own reports.

## 🔒 Environment Variables

The following values should be kept private:

```env
MONGO_URI=
JWT_SECRET=
GOOGLE_GENAI_API_KEY=
```

Make sure `.env` is included in `.gitignore`.

## 🐛 Error Handling

The application handles common issues such as:

* Invalid login
* Unauthorized requests
* Invalid resume files
* Large resume files
* MongoDB connection errors
* Gemini API errors
* Failed interview report generation

Gemini API availability can sometimes cause temporary `503` errors. In that case, the request can be retried or another available Gemini model can be used.

## 📚 What I Learned From This Project

While building this project, I got practical experience with:

* React frontend development
* Node.js and Express
* REST APIs
* MongoDB and Mongoose
* JWT authentication
* Password hashing
* File uploads
* PDF text extraction
* Gemini API integration
* Prompt engineering
* Zod validation
* Puppeteer
* PDF generation
* Frontend and backend integration
* Error handling

## 🔮 Future Improvements

Some features I would like to add in the future:

* DOCX resume support
* AI mock interview
* Voice-based interview
* AI answer evaluation
* Coding interview practice
* Interview performance tracking
* More detailed analytics
* Better AI response streaming
* Deployment and CI/CD

## 👨‍💻 About Me

I built this project to learn and implement a real-world full-stack application with AI integration.

It helped me understand how to connect a React frontend with a Node.js backend, MongoDB, file processing, authentication, and a generative AI API in one application.

---

**Built by Jayasankar Bollam**
