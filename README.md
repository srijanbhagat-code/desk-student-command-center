# UniDesk – Student Command Center

A modern, responsive SaaS-style productivity web application built for college students to manage class attendance, semester GPAs, assignments, Pomodoro study sessions, weekly timetables, and academic analytics from one unified dashboard.

UniDesk runs entirely in the browser with **zero backend dependencies**, automatic **LocalStorage** persistence, **JSON backup export/import**, and full **GitHub Pages** compatibility.

---

## Features

- **Command Center Dashboard**
  - Dynamic greeting, current date and day, and live workspace summary.
  - KPI cards for total assignments, completed tasks, overall attendance percentage, and weekly study hours.
  - Interactive **Academic Performance Overview** charts (attendance vs. target and weekly study trend).
  - **Upcoming Deadlines** widget with one-click completion, **Today's Classes** snapshot, and quick-access navigation cards.
- **Attendance Manager**
  - Add, edit, and delete subjects with quick `+1 Attended` and `+1 Missed` controls.
  - Customizable minimum attendance target (default: `75%`).
  - Automatic calculation of **consecutive classes required** to recover when below the target, and **classes safe to miss** while staying compliant.
  - Clear warning banners and status badges whenever subjects fall below the required threshold.
- **SGPA & CGPA Calculator**
  - Multi-semester workspace with credit-weighted SGPA per semester and cumulative CGPA across all semesters.
  - Inline subject editing (name, credits, grade) and semester management.
  - Fully **editable grade-point scale** with built-in **10-Point** and **4.0 US** presets plus custom grade tiers.
- **Assignment Manager**
  - Create, edit, filter, search, sort, and delete tasks with title, subject, description, due date, priority (`Low`, `Medium`, `High`), and status (`Pending`, `In Progress`, `Completed`).
  - Automatic **Overdue** detection with dedicated filter pill and alert banner.
- **Pomodoro Study Timer**
  - Timestamp-accurate countdown ring for **Focus (25 min)**, **Short Break (5 min)**, and **Long Break (15 min)** with Start/Pause, Reset, and Complete & Log controls.
  - Customizable interval durations, cycle counter, Web Audio completion chime, manual offline study logging, and daily/weekly study progress tracking.
- **Weekly Timetable**
  - Monday–Sunday class organizer with subject, classroom, start/end times, accent colors, and "Today" highlighting.
  - Day-by-day filtering and automatic schedule overlap/conflict detection.
- **Productivity Analytics**
  - Interactive charts and progress bars covering assignment completion, weekly study hours vs. goal, subject attendance statistics, semester SGPA trends, and full study session history.
- **Data Persistence & Themes**
  - Automatic saving and loading via `localStorage`.
  - Light and Dark themes with persistent preference.
  - Complete JSON data export, validated JSON import, sample workspace loader, and clean reset.

---

## Technologies Used

- **HTML5** — Semantic, accessible single-page structure
- **CSS3** — Custom properties, responsive CSS Grid/Flexbox, Light & Dark themes
- **Vanilla JavaScript (ES6+)** — Modular IIFE namespace architecture compatible with both local `file://` and HTTP servers
- **LocalStorage API** — Automatic browser-side persistence
- **Chart.js (v4 CDN)** — Interactive charts with native HTML5 Canvas offline fallback
- **SVG** — Custom vector favicon, icons, and Pomodoro progress ring

---

## Folder Structure

```text
unidesk-student-command-center/
├── index.html
├── README.md
├── .gitignore
├── .nojekyll
├── assets/
│   └── favicon.svg
├── css/
│   └── style.css
└── js/
    ├── storage.js
    ├── attendance.js
    ├── cgpa.js
    ├── assignments.js
    ├── timer.js
    ├── timetable.js
    ├── analytics.js
    └── app.js
```

---

## Installation

No package managers, build tools, or backend servers are required.

1. Clone or download this repository:
   ```bash
   git clone https://github.com/<your-username>/unidesk-student-command-center.git
   ```
2. Navigate into the project directory:
   ```bash
   cd unidesk-student-command-center
   ```

---

## Running Locally

You can open UniDesk using either method below:

### Option 1: Open Directly in Browser
Double-click `index.html` (or open it via your browser's **File → Open File** menu). All JavaScript modules and LocalStorage persistence work directly without a build step.

### Option 2: Run with a Local Development Server
- **VS Code Live Server**: Right-click `index.html` and select **Open with Live Server**.
- **Python 3**:
  ```bash
  python -m http.server 8000
  ```
  Then open `http://localhost:8000` in your browser.
- **Node.js**:
  ```bash
  npx serve .
  ```

---

## Deploying to GitHub Pages

1. Create a new public repository on GitHub (e.g., `unidesk-student-command-center`).
2. Push your project files to the `main` branch:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: UniDesk Student Command Center"
   git branch -M main
   git remote add origin https://github.com/<your-username>/unidesk-student-command-center.git
   git push -u origin main
   ```
3. On GitHub, open your repository and go to **Settings → Pages**.
4. Under **Build and deployment**:
   - **Source**: Select **Deploy from a branch**
   - **Branch**: Select `main` and folder `/ (root)`, then click **Save**.
5. Wait 1–2 minutes for the build to finish. Your live site will be available at:
   ```text
   https://<your-username>.github.io/unidesk-student-command-center/
   ```

---

## Screenshots

Add screenshots of your live deployment inside an `assets/screenshots/` folder and link them below:

```markdown
![UniDesk Dashboard - Light Theme](assets/screenshots/dashboard-light.png)
![UniDesk Dashboard - Dark Theme](assets/screenshots/dashboard-dark.png)
![Attendance & CGPA Tools](assets/screenshots/academics.png)
```

**How to capture & add screenshots:**
1. Open UniDesk in your browser (desktop `1440×900` and mobile `390×844` views).
2. Capture screenshots of the Dashboard (Light & Dark), Attendance Manager, CGPA Calculator, and Study Timer.
3. Save the PNG files into `assets/screenshots/`.
4. Uncomment or update the Markdown image links above and commit the files to your repository.

---

## Future Improvement Ideas

- **ICS / Calendar Export**: Export assignment deadlines and timetable classes as `.ics` calendar files.
- **Exam Countdown & Grade Predictor**: Calculate required final exam scores to achieve a target course grade.
- **Recurring Class Holidays**: Mark cancelled classes or holidays without affecting attendance percentages manually.
- **Offline PWA Support**: Add a Service Worker and `manifest.json` so UniDesk can be installed as a desktop/mobile Progressive Web App.
- **Keyboard Shortcuts**: Quick shortcuts (e.g., `Space` to start/pause timer, `N` to create a task).
