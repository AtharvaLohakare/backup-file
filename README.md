# AI-Powered Lost & Found Matching System

An AI-powered web application that helps users find lost items by matching them with reported found items using **image similarity, text similarity, and metadata matching**.

## 🌐 Live Project

**Frontend:**
https://lost-found-ai-matcher.netlify.app/

**Backend API:**
Add your Render backend URL here.

---

## 📌 Project Overview

The **AI-Powered Lost & Found Matching System** is designed to make lost-and-found management faster and easier.

Users can report:

* Lost items
* Found items
* Item images
* Item details such as category, color, brand, location, and date

The system compares lost and found items and generates a **match score** to identify possible matches.

---

## ✨ Features

### 👤 Report Lost Item

Users can submit:

* Item name
* Category
* Description
* Color
* Brand
* Location
* Date
* Image

### 🔎 Report Found Item

Users can submit details of an item they have found using the same information fields.

### 🤖 AI Matching

The system compares lost and found items using three components:

* 🖼️ **Image Similarity**
* 📝 **Text Similarity**
* 📋 **Metadata Matching**

The final score combines these components to determine the strength of a possible match.

### 📊 Explainable Matching

The system provides reasons for a match, such as:

* Category matches
* Color matches
* Brand matches
* Location matches
* Item name matches
* Strong image similarity
* Strong description similarity
* Strong metadata match

### 📈 Match Categories

| Score     | Match Level           |
| --------- | --------------------- |
| 90–100%   | Very High Match       |
| 75–89%    | High Match            |
| 50–74%    | Possible Match        |
| Below 50% | Low / No Strong Match |

---

## 🧠 Matching System

The current lightweight matching system uses:

### 1. Image Similarity

Images are compared using **Perceptual Hashing (pHash)**.

This provides a lightweight way to identify visually similar images without requiring a large deep-learning image model.

### 2. Text Similarity

Item names and descriptions are compared using lightweight word-based similarity.

### 3. Metadata Matching

The system checks:

* Category
* Color
* Brand
* Location
* Item name

### Final Score

The current prototype uses:

```text
40% Image Similarity
30% Text Similarity
30% Metadata Matching
```

These weights are prototype design choices and can be adjusted in future versions.

---

## 🏗️ System Architecture

```text
User
  │
  ▼
Netlify Frontend
HTML + CSS + JavaScript
  │
  ▼
Render Backend
FastAPI + Python
  │
  ├───────────────┐
  ▼               ▼
AI Matching      MySQL
  │               │
  ├── Image       │
  │   Similarity  │
  ├── Text        │
  │   Similarity  │
  └── Metadata    │
                  ▼
              Aiven MySQL
```

---

## 🛠️ Technologies Used

### Frontend

* HTML5
* CSS3
* JavaScript

### Backend

* Python
* FastAPI
* SQLAlchemy
* PyMySQL

### AI / Matching

* Perceptual Hashing
* Lightweight text similarity
* Metadata matching
* Pillow
* ImageHash
* NumPy

### Database

* MySQL
* Aiven MySQL

### Deployment

* **Frontend:** Netlify
* **Backend:** Render
* **Database:** Aiven

### Development Tools

* Visual Studio Code
* Git
* GitHub

---

## 📁 Project Structure

```text
AI-Powered-Lost-Found-Matching-System/
│
├── backend/
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── image_matcher.py
│   ├── text_matcher.py
│   ├── uploads/
│   ├── test_image_ai.py
│   └── test_text_ai.py
│
├── index.html
├── report-lost.html
├── report-found.html
├── items.html
├── item-detail.html
│
├── script.js
├── items.js
├── item-detail.js
├── style.css
├── config.js
├── requirements.txt
├── .gitignore
└── README.md
```

---

## ⚙️ Installation & Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/AtharvaLohakare/AI-Powered-Lost-Found-Matching-System.git
```

### 2. Move into the project directory

```bash
cd AI-Powered-Lost-Found-Matching-System
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the virtual environment

### Windows

```powershell
venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

### 6. Configure the database

Create a `.env` file:

```env
DATABASE_URL=mysql+pymysql://USER:PASSWORD@HOST:PORT/DATABASE
```

Do **not** commit `.env` to GitHub.

### 7. Start the backend

```bash
uvicorn backend.main:app --reload
```

The local API will run at:

```text
http://127.0.0.1:8000
```

---

## 🔐 Environment Variables

The project uses:

```text
DATABASE_URL
```

Example:

```env
DATABASE_URL=mysql+pymysql://username:password@host:port/database
```

The `.env` file is excluded from Git using `.gitignore`.

---

## 🚀 Deployment

### Frontend

The frontend is deployed using **Netlify**.

### Backend

The FastAPI backend is deployed using **Render**.

### Database

The MySQL database is hosted using **Aiven**.

---

## 🔄 Application Workflow

```text
1. User reports a lost item
              ↓
2. Item is stored in MySQL
              ↓
3. User reports a found item
              ↓
4. User opens the lost item
              ↓
5. User starts AI matching
              ↓
6. Image similarity is calculated
              ↓
7. Text similarity is calculated
              ↓
8. Metadata is compared
              ↓
9. Scores are combined
              ↓
10. Best matching found items are displayed
```

---

## 🎯 Future Improvements

Possible future improvements include:

* User authentication
* Email notifications
* Admin dashboard
* Better semantic text matching
* More advanced image embeddings
* Location-based matching
* Date-based matching
* Cloud image storage
* Mobile application
* Improved ranking algorithms
* Real-time notifications
* Duplicate item detection

---

## 📚 Project Purpose

This project was developed as a **college minor project** to demonstrate the practical application of:

* Artificial Intelligence
* Machine Learning concepts
* Computer Vision
* Natural Language Processing concepts
* Web Development
* REST APIs
* Database Management
* Cloud Deployment

---

## 👨‍💻 Developer

**Atharva Lohakare**

Computer Science / Artificial Intelligence & Machine Learning Student

GitHub:
https://github.com/AtharvaLohakare

---

## 📄 License

This project is created for educational and academic purposes.
