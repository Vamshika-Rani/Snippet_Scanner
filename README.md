# Snippet_Scanner
Snippet Scanner is a web-based tool that scans code snippets and URLs for security vulnerabilities based on the OWASP Top 10 guidelines. It helps developers identify and fix critical security issues in their code with AI-powered analysis and real-time scanning.

🌐 Live Website: https://snippet-scanner.pages.dev

Features
AI-Powered Vulnerability Detection
Scan Code Snippets or URLs
Severity Classification
🛡Covers OWASP Top Vulnerabilities
⚙️ How to Set Up the Project
Backend (Flask)
Clone the repository

git clone https://github.com/your-username/snippet-scanner.git
cd snippet-scanner
Set up a virtual environment (recommended)

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
Install the dependencies

pip install -r requirements.txt
Run the Flask app

python app.py
This will start the backend server at http://127.0.0.1:5050.

✅ Make sure CORS is enabled for frontend integration.

🖥️ How to Run the Web App (Frontend)
The frontend is a static website built using HTML, Tailwind CSS, and vanilla JavaScript.

You can open the index.html directly in your browser OR deploy it using any static hosting provider like:

Cloudflare Pages (used here)
GitHub Pages
Netlify
Ensure the backend is running at the URL specified in the fetch() API inside the JS script (app.py runs at http://127.0.0.1:5050 by default, or update to production backend URL).

📦 Dependencies
Backend
Flask
flask-cors
re (regex)
json, os, etc. (standard Python libraries)
Install all Python dependencies using:

pip install -r requirements.txt
API Endpoints
POST /scan
Accepts JSON with either:

{ "code_snippet": "<your_code_here>" }
or

{ "url": "https://yourwebsite.com" }
Returns:

{
  "vulnerabilities": [
    {
      "issue": "XSS Detected",
      "severity": "High",
      "description": "...",
      "suggestion": "...",
      "line_number": 12,
      "owasp_category": "A7: Cross Site Scripting (XSS)"
    }
  ]
}
