🏋️‍♂️ FitPlan AI – AI-Powered Fitness Application

An intelligent fitness application that generates personalized workout and dietary plans using AI, featuring secure user authentication and comprehensive profile management.

🚀 Features
🤖 AI-Powered Plans – Generate personalized workout and diet plans using Hugging Face models
🔐 Secure Authentication – Complete sign-in/sign-up system with OTP verification
🗄️ User Management – SQLite database for secure user data storage
🎨 Modern UI – Beautiful light-themed interface with custom CSS styling
👤 Profile Editing – Update user information and regenerate plans
📥 Export Functionality – Download workout and diet plans as text files
🔐 Authentication System
🔑 Sign In & Sign Up Implementation

The application includes a dual authentication system for secure and smooth user experience.

✅ Sign In Process
Email & Password authentication
Secure password verification using hashed passwords
JWT token generation after successful login
Session management to maintain login state
🆕 Sign Up Process
🔢 OTP-based email verification
Multi-step registration flow:
User fills registration form (name, email, password)
System checks for existing email
OTP is generated and sent via email
User enters OTP for verification
Account is created after successful verification
📧 SMTP-based email integration for OTP delivery
🗄️ Database Architecture
📦 SQLite Database Setup
Database File: users.db
Lightweight and efficient storage system
📋 Users Table Schema
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    email TEXT UNIQUE NOT NULL,
    password_hash TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
🔒 Security Features
🔐 Password hashing using Werkzeug (generate_password_hash)
✅ Secure password verification (check_password_hash)
🚫 Unique email constraint to prevent duplicates
🕒 Timestamp tracking for account creation
⚙️ Database Operations
register_user(name, email, password_hash) → Create new user
get_user_by_email(email) → Fetch user data
user_exists(email) → Check duplicate emails
🔄 Authentication Flow
🆕 Sign Up Flow
User Form → Email Check → OTP Generation → Email Send 
→ OTP Verification → Account Creation → JWT Token → Dashboard
🔑 Sign In Flow
User Credentials → Database Lookup → Password Verification 
→ JWT Token → Dashboard
🔐 Security Implementation
🔑 JWT Authentication
Secure token generation using user details
Token verification for session management
Stored in Streamlit session state
🔢 OTP System
Random 6-digit OTP generation
Email delivery using SMTP
Session-based OTP verification
🔒 Password Security
PBKDF2 hashing algorithm
Automatic salt generation
No plain-text password storage
🛠️ Technical Implementation
📦 Dependencies
Streamlit – Web framework
SQLite3 – Database
Werkzeug – Security & hashing
PyJWT – Token handling
Hugging Face API – AI model integration
SMTP Libraries – Email services
📁 Project Structure
├── app.py              # Main application UI
├── auth.py             # Authentication logic (JWT, OTP)
├── database.py         # Database operations
├── email_utils.py      # Email handling (OTP sending)
├── model_api.py        # AI model integration
├── prompt_builder.py   # Workout plan prompts
├── diet_builder.py     # Diet plan prompts
└── requirements.txt    # Dependencies
🧠 Session Management
Authentication state tracking
User profile storage
Edit mode handling
Workout & diet plan storage
🚀 Getting Started
📥 1. Install Dependencies
pip install -r requirements.txt
⚙️ 2. Set Environment Variables

Create a .env file:

HUGGINGFACE_API_KEY=your_api_key
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASSWORD=your_app_password
▶️ 3. Run the Application
streamlit run app.py
🌐 4. Access the App

Open your browser:
👉 http://localhost:8501

📊 Usage
🆕 New Users – Sign up and verify email using OTP
🔑 Existing Users – Sign in with credentials
🧾 Profile Creation – Enter fitness details
🤖 Plan Generation – Get AI-powered workout & diet plans
✏️ Profile Editing – Update details and regenerate plans
🔒 Security Features

Encrypted Passwords: PBKDF2 hashing with salt

JWT Authentication: Secure token-based sessions

OTP Verification: Email-based account verification

Input Validation: Form validation and sanitization

Session Security: Secure session state management
