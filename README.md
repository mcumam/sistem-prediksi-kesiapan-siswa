# Sistem Prediksi Kesiapan Siswa - UNS

A comprehensive web-based student readiness prediction system built with Flask, featuring machine learning predictions, modern UI, and analytics dashboard.

## 🚀 Features

### 🔐 Authentication System
- Secure login with session management
- Admin credentials: `admin` / `12345678`
- Automatic logout functionality

### 📊 Student Readiness Prediction
- Interactive form with validation
- Prediction based on multiple factors:
  - Student age (5.0 - 7.0 years)
  - Gender (L/P)
  - Father's education level
  - Mother's education level
  - PAUD experience (Ya/Tidak)
- Real-time prediction results with readiness levels

### 📈 Analytics Dashboard
- Visual statistics with charts
- Student readiness distribution
- Age-based analytics
- Recent predictions table
- Interactive data visualization using Chart.js

### 💾 Data Management
- CSV export functionality
- Daily prediction storage (max 30 per day)
- Automatic file generation with timestamps

### 🎨 Modern UI/UX
- Responsive design with Tailwind CSS
- UNS university branding
- Professional gradient backgrounds
- Mobile-friendly interface
- Smooth transitions and hover effects

## 🛠️ Technology Stack

- **Backend**: Flask (Python)
- **Frontend**: HTML5, Tailwind CSS, JavaScript, jQuery
- **Charts**: Chart.js
- **Data Processing**: Pandas, NumPy
- **Machine Learning**: Scikit-learn
- **Styling**: Google Fonts (Poppins)

## 📁 Project Structure

```
├── app.py                          # Main Flask application
├── decision_tree_model.py          # ML model training script
├── student_readiness_dataset.csv   # Training dataset
├── templates/
│   ├── login.html                  # Login page
│   ├── index.html                  # Main prediction interface
│   └── earning.html                # Analytics dashboard
└── README.md                       # Project documentation
```

## 🚀 Installation & Setup

### Prerequisites
- Python 3.7+
- pip package manager

### Installation Steps

1. **Clone or download the project files**

2. **Install required packages**
   ```bash
   pip install flask pandas scikit-learn matplotlib joblib
   ```

3. **Run the application**
   ```bash
   python app.py
   ```

4. **Access the application**
   - Open your browser and navigate to: `http://localhost:8080`
   - Login with credentials: `admin` / `12345678`

## 📖 Usage Guide

### 1. Login
- Navigate to the application URL
- Enter username: `admin`
- Enter password: `12345678`
- Click "Login"

### 2. Making Predictions
- Fill out the student information form:
  - **Nama Siswa**: Student's name
  - **Usia**: Age (5.0, 5.5, 6.0, 6.5, or 7.0 years)
  - **Jenis Kelamin**: Gender (L for Male, P for Female)
  - **Pengalaman PAUD**: PAUD experience (Ya/Tidak)
  - **Pendidikan Ayah**: Father's education level
  - **Pendidikan Ibu**: Mother's education level
- Click "Prediksi Kesiapan" to get results
- View prediction score and readiness level

### 3. Analytics Dashboard
- Click "Analytics" in the header navigation
- View comprehensive statistics and charts
- Analyze student readiness distribution
- Review recent predictions

### 4. Export Data
- Click "Export Data" button on the prediction page
- Download CSV file with all daily predictions
- File includes all student data and prediction results

## 🧠 Prediction Logic

The system uses rule-based logic for predictions:

### Age 5.0 - 5.5 years
- **Siap (85 points)**: Both parents have S1/S2 education + PAUD experience
- **Belum Siap (65 points)**: Other combinations

### Age 6.0 years
- **Siap (85 points)**: Both parents have SMA or higher education
- **Cukup Siap (75 points)**: Both parents have SD/SMP + PAUD experience
- **Belum Siap (65 points)**: Other combinations

### Age 6.5 - 7.0 years
- **Siap (85 points)**: Both parents have formal education + PAUD experience
- **Cukup Siap (75 points)**: Both parents have formal education, no PAUD
- **Belum Siap (65 points)**: Other combinations

## 📊 Readiness Score Interpretation

- **≥ 90**: Sangat Siap (Very Ready)
- **80-89**: Siap (Ready)
- **70-79**: Cukup Siap (Moderately Ready)
- **< 70**: Belum Siap (Not Ready)

## 🔧 Configuration

### Login Credentials
Edit in `app.py`:
```python
VALID_USERNAME = "admin"
VALID_PASSWORD = "12345678"
```

### Education Levels
```python
education_levels = ['Tidak Sekolah', 'SD', 'SMP', 'SMA', 'D3', 'S1', 'S2']
```

### Age Ranges
```python
age_ranges = [5.0, 5.5, 6.0, 6.5, 7.0]
```

## 🚀 Deployment

### Local Development
```bash
python app.py
```
Access at: `http://localhost:8080`

### Production Deployment
1. Use a production WSGI server (e.g., Gunicorn)
2. Configure environment variables
3. Set up reverse proxy (e.g., Nginx)
4. Enable HTTPS

## 📝 API Endpoints

- `GET /` - Redirect to login
- `GET /login` - Login page
- `POST /login` - Authentication
- `GET /logout` - Logout
- `GET /predictor` - Main prediction interface
- `GET /earning` - Analytics dashboard
- `POST /predict` - Make prediction (AJAX)
- `GET /export` - Export CSV data

## 🎯 Key Features Highlights

### 🔒 Security
- Session-based authentication
- CSRF protection ready
- Input validation and sanitization

### 📱 Responsive Design
- Mobile-first approach
- Tablet and desktop optimized
- Touch-friendly interface

### 🎨 Professional UI
- UNS university branding
- Consistent color scheme
- Modern typography with Poppins font
- Smooth animations and transitions

### 📊 Data Analytics
- Real-time statistics
- Interactive charts
- Export capabilities
- Historical data tracking

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is developed for Universitas Sebelas Maret (UNS) educational purposes.

## 👥 Support

For support and questions, please contact the development team at Universitas Sebelas Maret.

---

**Managed By Universitas Sebelas Maret**
