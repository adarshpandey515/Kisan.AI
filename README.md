# 🌾 Kisan.ai

**Revolutionizing Farm Management with Technology**  
*Kisan.ai* is an award-winning project that modernizes farming by integrating AI, AR, and real-time updates, making agriculture more efficient, profitable, and sustainable.

## 🌟 Key Features

- **📦 Inventory Management**: Real-time tracking to prevent overstocking and understocking.
- **⏰ Expiration Tracking**: Automatic alerts for perishable goods.
- **📲 Real-Time Alerts**: Stock notifications via SMS/WhatsApp.
- **🤖 AI Resource Estimation**: Optimize resources based on soil, season, and crop needs.
- **📈 Market Insights**: Current prices and trader contacts for informed selling.
- **🌦️ Weather Forecasting**: Tailored forecasts for better planning.
- **🛠️ Automated Tool Crafting**: Simplified creation of tools from available resources.
- **🕶️ AR Visualization**: Manage inventory with 3D AR models.

## 🔗 Links
- [Project](https://devfolio.co/projects/kisanai-499c)
- [Hackathon Win Announcement](https://www.linkedin.com/posts/aryankyatham_we-won-the-google-international-level-hackathon-activity-7167872040169861120-soVz)

## 👥 Developers
- Aryan Kyatham
- Sharvin Gavad
- Myron Dabreo
- Neston Cabral

## 🛠️ Technologies Used
- Django | AI & ML | AR | SMS/WhatsApp API

---

## 📁 Repository Structure

```
Kisan.AI/
├── README.md                        # Project overview and documentation
├── LICENSE                          # License file
└── bitnbuild/                       # Main Django project root
    ├── manage.py                    # Django management CLI entry point
    ├── requirements.txt             # Python dependencies
    ├── db.sqlite3                   # SQLite database (auto-created on first migration)
    ├── credentials.json             # Google OAuth2 credentials
    ├── token.json                   # Google API token (auto-generated)
    ├── yolov8n.pt                   # Pre-trained YOLOv8 model weights
    ├── faiss_index/                 # FAISS vector store for AI document search
    ├── media/                       # Uploaded media files (product images, etc.)
    │
    ├── bitnbuild/                   # Django project configuration package
    │   ├── settings.py              # Project settings (database, apps, auth, etc.)
    │   ├── urls.py                  # Root URL dispatcher
    │   ├── wsgi.py                  # WSGI entry point for production deployment
    │   └── asgi.py                  # ASGI entry point for async deployment
    │
    ├── inventory/                   # App: Inventory management
    │   ├── models.py                # Category and Product database models
    │   ├── views.py                 # Inventory CRUD, weather, AI/Gemini chat, PDF report
    │   ├── forms.py                 # ProductForm for adding/editing inventory items
    │   ├── urls.py                  # URL routes for the inventory app
    │   └── migrations/              # Database migration files
    │
    ├── analysis/                    # App: Farm analysis and AI recommendations
    │   ├── views.py                 # Views for crop, fertilizer, seed, profit analysis
    │   ├── urls.py                  # URL routes for the analysis app
    │   └── migrations/              # Database migration files
    │
    ├── inventory_recommendation/    # App: Market bids and product listing
    │   ├── models.py                # Product model for marketplace listing
    │   ├── views.py                 # Views for posting products and viewing bids
    │   ├── forms.py                 # ProductForm for marketplace
    │   ├── urls.py                  # URL routes for recommendations app
    │   └── migrations/              # Database migration files
    │
    ├── yolo/                        # App: Computer vision / object detection
    │   ├── views.py                 # Real-time stock detection via YOLOv8 + webcam
    │   ├── urls.py                  # URL routes for YOLO app
    │   └── migrations/              # Database migration files
    │
    └── resources/                   # App: AI-powered resource estimation
        ├── views.py                 # Gemini AI integration for crop resource planning
        ├── urls.py                  # URL routes for resources app
        └── migrations/              # Database migration files
```

---

## ⚙️ Prerequisites

- Python 3.9+
- pip
- A virtual environment tool (`venv` or `virtualenv`)
- A Google API key (for Gemini AI features)
- A Twilio account (for SMS/WhatsApp alerts)
- An OpenWeatherMap API key (for weather forecasting)

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/adarshpandey515/Kisan.AI.git
cd Kisan.AI/bitnbuild
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
# On Linux/macOS:
source venv/bin/activate
# On Windows:
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file inside the `bitnbuild/` directory and populate it with your credentials. **Never commit this file to version control.**

```env
# Django
SECRET_KEY=your_django_secret_key
ALLOWED_HOSTS=127.0.0.1,localhost

# Google Generative AI (Gemini)
GOOGLE_API_KEY=your_google_generative_ai_api_key

# Google OAuth2
SOCIAL_AUTH_GOOGLE_OAUTH2_KEY=your_google_oauth2_client_id
SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET=your_google_oauth2_client_secret

# Twilio (SMS/WhatsApp alerts)
TWILIO_ACCOUNT_SID=your_twilio_account_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_PHONE_NUMBER=your_twilio_phone_number

# OpenWeatherMap (weather forecasting)
OPENWEATHERMAP_API_KEY=your_openweathermap_api_key
```

### 5. Apply database migrations

```bash
python manage.py migrate
```

### 6. Create a superuser (optional, for Django admin access)

```bash
python manage.py createsuperuser
```

### 7. Run the development server

```bash
python manage.py runserver
```

The application will be available at `http://127.0.0.1:8000/`.

---

## 🗂️ Main Files Explained

| File / Directory | Purpose |
|---|---|
| `bitnbuild/manage.py` | Django CLI entry point — used to run the server, apply migrations, and manage the project. |
| `bitnbuild/requirements.txt` | Lists all Python packages required to run the project. |
| `bitnbuild/bitnbuild/settings.py` | Central configuration: installed apps, database, authentication backends, static/media paths. |
| `bitnbuild/bitnbuild/urls.py` | Root URL configuration that includes routes from all Django apps. |
| `bitnbuild/inventory/models.py` | Defines `Category` and `Product` database models used throughout the project. |
| `bitnbuild/inventory/views.py` | Core views: inventory CRUD operations, weather forecasting, tool crafting, PDF report generation, and AI chat (Gemini). |
| `bitnbuild/analysis/views.py` | Views for farm analysis pages (crops, fertilizer, seed usage, profit) and SMS alert integration via Twilio. |
| `bitnbuild/resources/views.py` | Sends crop/land/soil data to Google Gemini AI to estimate required farming resources. |
| `bitnbuild/yolo/views.py` | Uses YOLOv8 and OpenCV to detect produce via webcam and automatically update inventory stock levels. |
| `bitnbuild/inventory_recommendation/views.py` | Handles marketplace listing of products and viewing buyer bids. |
| `bitnbuild/yolov8n.pt` | Pre-trained YOLOv8 nano model weights for object detection. |
| `bitnbuild/faiss_index/` | Local FAISS vector index used for semantic search over uploaded inventory PDF documents. |
| `bitnbuild/db.sqlite3` | SQLite database file storing all application data (created automatically after migration). |

---

## 🖼️ Screenshots

![Screenshot 2024-03-04 163221](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/fcabdaa5-184a-4d11-b9d0-01dd90a68b0e)

![MixCollage-04-Mar-2024-04-59-PM-7716](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/4a0c863c-57c3-4e2c-951e-c0913c18cd22)

![MixCollage-04-Mar-2024-04-40-PM-9170](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/a22a4741-e08d-4bfc-ac0b-8d2bc8f136d9)

![Screenshot 2024-03-04 163923](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/1457ca8c-4ed6-4c20-9a89-cd1a2a83de72)

![Screenshot 2024-03-04 163412](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/4bef717f-479b-487c-935a-ed7c36169bcf)

![Screenshot 2024-03-04 163633](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/3ad2a2a2-86b0-4967-a8ab-730713efcf96)

![Screenshot 2024-03-04 163838](https://github.com/ARYANK-08/KISANInv.AI/assets/120780784/9fcc0f4f-c94f-4eaf-80bd-3eb81c18021c)

Interactive Data Queries: Allows for quick, conversational access to specific inventory information, eliminating manual search efforts.

This project transforms traditional farming into a technology-driven process, making it more efficient and data-informed. By addressing inventory management, resource estimation, market intelligence, and weather forecasting, it empowers farmers to make smarter decisions, reduce waste, and increase profitability sustainably.
