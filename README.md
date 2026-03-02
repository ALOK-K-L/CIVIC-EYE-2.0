# Civic Eye

Civic Eye is a public grievance tracking system built with a React and Vite frontend and a Node.js and PostgreSQL backend. It allows citizens to report infrastructure issues and pinpoint exact locations using interactive maps.

The system uses local AI (via Ollama) to automatically analyze the text of submitted grievances. It extracts relevant tags, determines the priority level, and routes the ticket to the correct government department (such as the Public Works, Electricity Board, or Water Authority). This eliminates the need for manual ticket sorting and speeds up response times.

---

## Key Features

* **Local AI Triage:** Uses local LLMs to automatically analyze complaint text, assign departments, and set priority levels.
* **Geospatial Tracking:** Allows users to drop pins on an interactive map to capture exact latitude and longitude coordinates for an issue.
* **Role-Based Access Control:** Separate dashboards and permission levels for citizens, department officials, and system administrators.
* **Data Visualization:** Interactive charts to track Service Level Agreements (SLAs) and department resolution efficiency.

---

## Tech Stack

### Frontend (Client)
* **Framework:** React 19
* **Build Tool:** Vite (fast HMR and optimized builds)
* **Routing:** React Router v7
* **Styling:** Tailwind CSS v4
* **Animations:** Framer Motion
* **Mapping:** Leaflet & React-Leaflet
* **Data Visualization:** Recharts

### Backend (Server)
* **Runtime & Framework:** Node.js + Express.js
* **Database:** PostgreSQL
* **Database Driver:** `pg` (node-postgres)
* **Authentication:** JWT (`jsonwebtoken`) & `bcrypt`
* **File Handling:** `multer` (for handling image uploads)
* **Environment:** `dotenv`

---

## System Prerequisites

Since this project relies on local AI inference and a local relational database, you need the following installed on your machine before running the application:

1. **Node.js** (v18.0 or higher)
2. **PostgreSQL** (running locally on the default port 5432)
3. **Ollama** (for local AI processing). Once Ollama is installed, pull the Llama 3 model by running this command in your terminal:
   
   ollama run llama3

   ## Local Setup & Installation

The repository is structured into two main directories: `/client` and `/server`. You will need to run two separate terminal windows to start both components simultaneously.

### 1. Clone the Repository

git clone [https://github.com/ALOK-K-L/CIVIC-EYE-2.0.git](https://github.com/ALOK-K-L/CIVIC-EYE-2.0.git)
cd CIVIC-EYE-2.0
2. Database & Backend Setup
Create a PostgreSQL database named civic_eye. Then, open a terminal and install the server dependencies:


cd server
npm install
Environment Variables:
Create a .env file inside the /server directory and configure the following variables so the server can connect to your local database and AI:


PORT=5000
DATABASE_URL=postgres://YOUR_DB_USER:YOUR_DB_PASSWORD@localhost:5432/civic_eye
JWT_SECRET=your_super_secret_jwt_key
OLLAMA_API_URL=http://localhost:11434/api/generate
Start the backend server:


npm start
3. Frontend Setup
Open a new terminal window and install the client dependencies:


cd client
npm install
npm run dev
The frontend application will now be running at http://localhost:5173
