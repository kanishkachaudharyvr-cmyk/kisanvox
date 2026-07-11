# KisanVox 🌾🗣️

**KisanVox** is a voice-orchestrated, AI-agent-powered logistics and supply chain assistant built to empower regional farmers. It allows farmers to tap a single button, speak naturally in their regional Indian language, and automatically coordinate logistics for dispatching their crops to optimal markets.

Live Production URL: **[https://kisanvox.vercel.app](https://kisanvox.vercel.app)**

---

## 🚀 Key Features

*   **Multilingual Browser Voice Orchestration**: Farmers can select English, Hindi, Marathi, Telugu, or Punjabi. The app uses the native Web Speech API to transcribe speech locally in their regional accents.
*   **Real-time Indian Mandi Rates**: Integrated with live APMC daily wholesale rates (via `cms.mandirates.in/api/daily-prices`). The backend automatically sorts and maps prices to route crops to the highest-paying market.
*   **Customizable SVG Map Route Tracker**: Extracts source farms and destination mandis from speech, dynamically calculates coordinates, and draws curved routing dashed animations on a responsive light-themed dashboard.
*   **Printable Dispatch Voucher**: Generates a receipt containing optimal prices, matched local truck drivers (with rating, ETA, and phone), and translated regional text confirmations.
*   **Serverless Ready**: Built with FastAPI and optimized with `tempfile` storage to run on read-only serverless filesystems like Vercel.

---

## 🛠️ Technology Stack

*   **Backend**: Python, FastAPI, Uvicorn, Pydantic, HTTPX, python-dotenv
*   **AI Agent**: Google Antigravity SDK (`google.antigravity` framework)
*   **Frontend**: HTML5, Vanilla JavaScript, Tailwind CSS (Glassmorphic light-theme)
*   **Speech-to-Text**: Native Browser Speech Recognition API (with Sarvam AI STT backend translation fallbacks)
*   **Hosting**: Vercel

---

## 📦 Local Setup and Installation

### 1. Clone the repository
```bash
git clone https://github.com/kanishkachaudharyvr-cmyk/kisanvox.git
cd kisanvox
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Setup Environment Variables
Create a `.env` file in the root directory:
```env
SARVAM_API_KEY=your-sarvam-api-key
GOOGLE_APPLICATION_CREDENTIALS=path-to-google-credentials-json
```
*(Note: If no credentials or keys are supplied, the app gracefully falls back to local high-fidelity agent emulation and Web Speech API translations so that the app remains 100% functional for demonstrations).*

### 4. Run the Server
```bash
python app.py
```
Open **[http://127.0.0.1:8000](http://127.0.0.1:8000)** in your browser.

---

## 🌩️ Deployment to Vercel

The project includes `vercel.json` and is configured to run out of the box as a Python serverless API.

Deploy preview:
```bash
vercel
```

Deploy to production:
```bash
vercel --prod
```
