
# 🏥 Provider Data Cleaner  
### Built for EY Hackathon 2025-26 🚀  

An AI-powered healthcare data cleaning application designed to standardize, validate, and enhance provider datasets with intelligent automation.

This project was built during the **EY Hackathon 2026** to solve a real-world problem: cleaning messy healthcare provider data efficiently and accurately.

---

## ✨ Problem Statement

Healthcare provider datasets often contain:
- Inconsistent phone number formats  
- Invalid or malformed email addresses  
- Incomplete or low-quality addresses  
- Unstructured data entries  

Manual cleaning is time-consuming and error-prone.

This tool automates validation, standardization, and quality scoring of provider data.

---

## 🌟 Key Features

### 📞 Phone Number Standardization (India Focused)
- Converts numbers to standard +91XXXXXXXXXX format
- Handles:
  - 10-digit numbers  
  - 11-digit numbers (starting with 0)  
  - 12-digit numbers (starting with 91)  
- Flags invalid entries  

Example:
9876543210   → +919876543210  
09876543210  → +919876543210  
919876543210 → +919876543210  

---

### 📧 Email Validation & Cleaning
- Removes extra whitespace  
- Fixes multiple @ symbols  
- Removes consecutive dots  
- Validates proper email format  

Example:
test@@mail..com → test@mail.com  

---

### 📍 Intelligent Address Quality Scoring

Addresses are scored out of 100 based on:

- Street Number (25)
- Street Type (25)
- ZIP Code (20)
- City Name (30)

Rating System:
- Excellent (90–100)
- Good (70–89)
- Fair (50–69)
- Poor (30–49)
- Invalid (0–29)

For valid addresses, approximate India-based coordinates are generated:
- Latitude range: 8°N – 35°N  
- Longitude range: 68°E – 97°E  

---

### 🗺 Google Maps Integration
- One-click address verification  
- Opens cleaned address directly in Google Maps  

---

### 📊 Real-Time Dashboard
- Total records processed  
- Valid phone numbers  
- Valid email addresses  
- Address quality distribution  
- Visual indicators and color-coded ratings  

---

### 📥 Export Options
Download cleaned data as:
- CSV  
- JSON  

Additional output fields:
- phone_valid
- email_valid
- address_rating
- validation_status
- last_updated

---

## 🛠 Tech Stack

- React 18  
- Vite  
- Tailwind CSS  
- PapaParse  
- Lucide React  
- PostCSS & Autoprefixer  

---

## 🚀 Getting Started

1️⃣ Clone Repository
git clone https://github.com/Gauravrao1/Ey_hackathon.git  
cd ai-agentic-2  

2️⃣ Install Dependencies
npm install  

3️⃣ Run Development Server
npm run dev    

---

## ⚠️ Known Limitations

- Coordinates are approximate (not real geocoding API)
- Optimized for Indian datasets
- Large CSV files (>10MB) may process slower

---

## 🔮 Future Enhancements

- Real geocoding API integration  
- Duplicate detection engine  
- International phone format support  
- Database export functionality  
- Advanced AI anomaly detection  

---

## 👥 Team – EY Hackathon 2025-26

- Gaurav Rao  
- Rashi Gupta  
- Ayush Raj Sinha  
- Harsh Vind  
- Shashank Awasthi  

Together, we focused on building a scalable and practical healthcare data validation solution.

---

## 👨‍💻 Author

Gaurav Rao  
Engineering Student | AI & Frontend Enthusiast  

