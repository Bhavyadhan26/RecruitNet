# RecruitNet
🧠 AIT RecruitNet — Placement Management & Job Application Portal
🎓 A Full-Stack Campus Placement Management System built with Django, designed for students, TPOs, and recruiters to manage campus hiring drives efficiently.
🚀 Project Overview

AIT RecruitNet is a comprehensive placement management portal that simplifies the placement process for colleges.
It allows:

Students to view jobs, apply online, upload resumes, and track their applications.

TPOs (Training & Placement Officers) to post new job openings and manage student applications.

Administrators to monitor all users and maintain the placement data efficiently.

This system integrates automated resume parsing (via Gemini AI), student-job fit analysis, and a modern dashboard UI for every user role.

🏗️ Tech Stack
Layer	Technology
Frontend	HTML5, CSS3, TailwindCSS, Bootstrap, JavaScript (ES6)
Backend	Python 3.11+, Django 4.x
Database	MySQL
AI Integration	Google Gemini API (for Resume Parsing and Fit Score)
File Handling	Django FileStorage + pdfplumber
Version Control	Git & GitHub
Deployment	(Localhost / planned: Render / AWS / Railway)
🧩 Project Structure
AIT_RecruitNet/
│
├── AIT_RecruitNet/
│   ├── settings.py
│   ├── urls.py
│   ├── wsgi.py
│   └── asgi.py
│
├── placement/
│   ├── migrations/
│   ├── templates/placement/
│   │   ├── components_dashboard/
│   │   │   ├── header.html
│   │   │   ├── sidebar.html
│   │   │   └── footer.html
│   │   ├── student_my-jobs.html
│   │   ├── student_applied_jobs.html
│   │   └── page-sigin.html
│   │
│   ├── static/placement/assets_dashboard/
│   │   ├── css/
│   │   ├── js/
│   │   ├── imgs/
│   │   └── icons/
│   │
│   ├── models.py
│   ├── views.py
│   ├── urls.py
│   ├── forms.py
│   ├── admin.py
│   ├── utils/
│   │   └── pdfparserscript.py
│   ├── tests.py
│   └── __init__.py
│
├── manage.py
└── README.md

🧱 Key Features
🧍‍♀️ For Students

View all available Job Posts.

Upload Resume (PDF) → Automatic Resume Parsing using Gemini AI.

Job Fit Score Analysis using AI suggestions.

Apply for jobs & view Application Status.

Track all Applied Jobs in one place.

Edit and maintain Student Profile.

🧑‍💼 For TPOs (Training & Placement Officers)

Post new Job Listings for companies.

Manage eligibility criteria, departments, and courses.

View and shortlist student applications.

Manage drives, company data, and results.

🧑‍🏫 For Admins

Manage all users (Students, HODs, TPOs).

Manage departments, programs, and job listings.

Review placement analytics and audit logs.

🗃️ Database Schema (Simplified)
Table	Purpose
User	Authentication and role mapping
Role	Defines roles – Student, TPO, HOD
Student	Stores student profiles and academic info
Department	Department-level details
Program	Degree and course mapping
TPO	TPO details and access controls
Company	Company profiles
JobPost	Job listings posted by TPOs
JobApplication	Tracks which student applied to which job
Resume	Stores uploaded student resumes
ResumeParsed	Parsed resume data (skills, experience, etc.)
FileStore	File metadata for uploads
AuditLog	Tracks actions in the system
🧮 AI Resume Fit Analysis

Each uploaded resume is processed using:

pdfplumber to extract text.

Google Gemini API to analyze skills, education, and experience.

Output:

Fit Score (% match) with the job post

Suggestions for improvement

This enables data-driven career insights for students.

⚙️ Setup Instructions
1️⃣ Clone the Repository
git clone https://github.com/yourusername/AIT_RecruitNet.git
cd AIT_RecruitNet

2️⃣ Create & Activate Virtual Environment
python -m venv venv
venv\Scripts\activate      # Windows
# OR
source venv/bin/activate   # macOS/Linux

3️⃣ Install Dependencies
pip install -r requirements.txt

4️⃣ Configure .env or settings.py

Set up your MySQL credentials:

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'ait_recruitnet',
        'USER': 'root',
        'PASSWORD': 'yourpassword',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}


Add your Gemini API Key inside:

GOOGLE_GENAI_API_KEY = "YOUR_GEMINI_API_KEY"

5️⃣ Apply Migrations
python manage.py makemigrations
python manage.py migrate

6️⃣ Create Superuser
python manage.py createsuperuser

7️⃣ Run Server
python manage.py runserver


Access app at 👉
http://127.0.0.1:8000/

🖥️ Main Functional Pages
Page	URL Name	Description
Dashboard	index	Main student dashboard
My Jobs	student_my-jobs	View & apply for jobs
Applied Jobs	student_applied_jobs	View jobs the student has applied for
Login	page-sigin	Login screen
Post Job	post_job	TPO posts a new job
Resume Upload	analyse_resume	Upload PDF & analyze fit score
📂 Key Python Scripts
Script	Purpose
pdfparserscript.py	Parses resume PDFs and performs Gemini AI job fit analysis
views.py	Contains Django views for all student, TPO, and admin actions
models.py	Defines database structure and relationships
admin.py	Admin dashboard customization
urls.py	URL routing for placement app
📊 Future Enhancements

✅ Add automated email notifications on selection
✅ Integrate data analytics dashboard for placement trends


👥 Contributors

Bhavya Dhanuka- Project Leader and Backend Developer
Parth Sharma - System Architect
Abhinav Jain - Frontend Developer
Amogh Sahore - Frontend Developer

🌟 Acknowledgements

Django Framework – backend core

Google Gemini API – resume parsing & AI insights

pdfplumber – text extraction from PDF resumes


