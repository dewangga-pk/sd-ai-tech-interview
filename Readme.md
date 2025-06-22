# AI Technical Interview Generator

A full-stack web application powered by the **MERN stack** and integrated with **Gemini AI**, designed to help users simulate and prepare for technical interviews. This tool generates a personalized list of potential interview questions and concise answers based on the position's experience requirements and the selected discussion topics.

> 🔒 Authentication is required to access the main features. Users can sign up or log in to start generating sessions.

---

## 🌟 Features

- 🔐 **Authentication** — Register & login to access core features.
- 🧠 **AI-powered Question Generation** — Generate 10 technical interview questions and concise answers based on:
  - Position
  - Years of experience
  - Topics of discussion
  - Notes
- 📌 **Pin Important Questions** — Mark important questions and move them to the top.
- 📝 **Add More Questions** — Add more questions to the session.
- 📖 **Detailed Explanation** — View deeper explanations to better understand the context of each question.
- 🗂️ **Session Management** — Create, delete, and explore session details.
- Docker support for quick deployment
---

## 🛠️ Built With

| Layer     | Stack                         |
|-----------|-------------------------------|
| Frontend  | React (Vite) + Tailwind CSS 4 |
| Backend   | Express.js + Node.js v22.15.0 |
| Database  | MongoDB                       |
| Package Manager | npm                    |
| AI Model  | Gemini (via API integration)  |
| Container | Docker + Docker Compose       |

---

## ⚙️ Setup & Installation

> You can run the project in **two ways**:

### 🧩 Option 1: Using Docker (Recommended)

> Make sure you have [Docker](https://docs.docker.com/get-docker/) installed.

### 🧪 Requirements

- Docker
- Gemini API Key (get it from [Gemini Studio](https://aistudio.google.com/prompts/new_chat))
- JWT Secret (generate using the command below)

```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
````

### ▶️ Steps

1. Clone this repository:

```bash
git clone https://github.com/dewangga-pk/sd-ai-tech-interview.git
cd sd-ai-tech-interview
```

2. Open `docker-compose.yml` and replace the following placeholders:

```yaml
JWT_SECRET: <your_jwt_secret>
GEMINI_API_KEY: <your_gemini_api_key>
```

3. Run the app:

```bash
docker-compose up --build
```

4. Open in your browser: [http://localhost:3000](http://localhost:3000)

---

### 🛠️ Option 2: Manual Setup (No Docker)

#### Requirements:

- Node.js v22.15.0 → [Download Node.js](https://nodejs.org/en/download)
- MongoDB → [Install MongoDB](https://www.mongodb.com/try/download/community)

#### Steps:

1. Clone the repository:

```bash
git clone https://github.com/dewangga-pk/sd-ai-tech-interview.git
```


2. Setup Backend:

* Go to `backend/`
* Copy `.env.example` to `.env`
* Fill the `.env` file with:

```env
MONGO_URI=mongodb://localhost:27017/interview_tool
JWT_SECRET=<your_jwt_secret>
GEMINI_API_KEY=<your_gemini_api_key>
PORT=8000
```
> Generate a JWT secret with:
```bash
node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
```

3. Setup Frontend:

* Go to `frontend/`
* Copy `.env.example` to `.env`
* Set `VITE_API_BASE_URL` to your backend URL, e.g.

```env
VITE_API_BASE_URL=http://localhost:8000
```

4. Install dependencies and run both frontend & backend:

**Terminal 1: Backend**
```bash
cd backend
npm install
npm run dev
```

**Terminal 2: Frontend**
```bash
cd frontend
npm install
npm run dev
```
By default, the frontend will be served at: `http://localhost:5173`

---

## 📸 Screenshots

> _(Add screenshots or demo GIFs here)_

---

## 📁 Folder Structure

```
sd-ai-tech-interview/
├── backend/           # Express backend (API, DB connection, auth, routes)
├── frontend/          # React (Vite) frontend (UI, session forms, question display)
├── docker-compose.yml
├── README.md
```

---

## 🛡️ Security Notice

* This project uses `.env` files for all sensitive configs
* Actual `.env` files are **ignored via `.gitignore`**
* Please use the `.env.example` as a reference
* Do **not** commit API keys, secrets, or database credentials
