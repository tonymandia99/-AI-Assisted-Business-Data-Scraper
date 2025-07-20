# 🕷️ AI-Assisted Business Data Scraper

A fully automated, AI-assisted web scraping system that extracts business listings from [Superpages.com](https://www.superpages.com), hosted on a Contabo VPS with Ubuntu 22.04. Built for efficiency, reliability, and hands-free execution using Python, Playwright, and systemd.

---

## 🚀 Features

- ✅ **Headless scraping** with [Playwright](https://playwright.dev/python/)
- 🧠 **AI-assisted automation** using ChatGPT (for logic, scheduling, error handling)
- 🖥️ **Remote VPS deployment** on **Contabo**, managed via **MobaXterm**
- 🔁 **Autonomous scheduling**: runs daily from **2:00 AM to 12:00 AM** using `systemd` timers
- 🩺 **Self-health monitoring** using a heartbeat/status file
- ⚠️ **Failsafe stop service**: prevents zombie tasks using `stop-superpages.service`
- 🗂️ Outputs organized CSV files per state/category
- 🧪 Optional: Restart logic, log rotation, and email alerts

---

## 📸 Sample Output
state,category,name,phone,address,website
Texas,Electricians,John's Electric,555-1234,123 Main St, www.johnselectric.com

---

## 🛠️ Technologies Used

| Tool/Tech        | Purpose                                  |
|------------------|------------------------------------------|
| 🐍 Python 3.10+   | Core language                            |
| 🎭 Playwright     | Headless browser automation              |
| ⏱️ systemd        | Linux service + timer scheduling         |
| 🧠 ChatGPT        | Code assistance + optimization            |
| 💻 MobaXterm      | Remote terminal access (Windows SSH)     |
| 🖥️ Ubuntu 22.04   | VPS operating system                     |
| 📡 Contabo VPS    | Hosting environment                      |

---

## 🧪 How It Works

1. `superpages.service` starts the scraper at 2:00 AM
2. Scraper loops through all cities + job categories
3. After each scrape, updates a status file
4. `stop-superpages.service` stops it at 12:00 AM
5. Systemd handles restart every day — zero manual work

---

## 📦 Setup Instructions

### 1. Clone the Repo
```bash
git clone https://github.com/yourusername/ai-assisted-superpages-scraper.git
cd ai-assisted-superpages-scraper
python3 -m venv scraper-env
source scraper-env/bin/activate
pip install -r requirements.txt
playwright install
2. Install Requirements
bash
Copy
Edit
python3 -m venv scraper-env
source scraper-env/bin/activate
pip install -r requirements.txt
playwright install
3. Configure systemd Services
Files:

superpages.service

superpages.timer

stop-superpages.service

stop-superpages.timer

Enable timers:

bash
Copy
Edit
sudo systemctl enable superpages.timer
sudo systemctl enable stop-superpages.timer
4. Run Manually (for testing)
bash
Copy
Edit
python3 superpages_scraper.py
🔐 Security & Ethics
This project is for educational purposes only. Respect robots.txt and website terms of use. Always rate-limit requests and avoid scraping sensitive or private data.

📄 License
MIT License © 2025 tonymandia99

🤝 Credits
Built with AI assistance from ChatGPT and deployed on infrastructure by Contabo.

markdown
Copy
Edit

---

### ✅ Next Steps for You

1. **Create the GitHub repo** → example: `ai-assisted-superpages-scraper`
2. Add:
   - `superpages_scraper.py`
   - `requirements.txt`
   - `README.md` (above)
   - `systemd/` folder with `.service` and `.timer` files

3. Push to GitHub:
```bash
git init
git add .
git commit -m "Initial commit: AI-assisted Superpages scraper"
git remote add origin https://github.com/yourusername/ai-assisted-superpages-scraper.git
git push -u origin main
