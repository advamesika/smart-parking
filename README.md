# Smart Parking

פרויקט Smart Parking מוכן לפתיחה ב־Visual Studio Code.

## פתיחה ב־VS Code
1. הורידו את קובץ ה־ZIP.
2. חלצו אותו למחשב באמצעות Extract All.
3. פתחו VS Code.
4. בחרו File → Open Folder.
5. בחרו בתיקייה `Smart-Parking-VSCode` שחילצתם.
   חשוב: פתחו את התיקייה עצמה, לא את קובץ ה־ZIP.

## הפעלת האתר
נדרשת התקנה של Docker Desktop והפעלה שלו לפני שמריצים את הפרויקט.

1. ב־VS Code בחרו Terminal → New Terminal.
2. ודאו שאתם נמצאים בתיקיית הפרויקט, שבה נמצא `docker-compose.yml`.
3. הריצו:

```bash
docker compose up -d
```

4. פתחו בדפדפן את:
   http://localhost:8080

לעצירת האתר:

```bash
docker compose down
```

אפשר גם להפעיל את המשימות מתוך VS Code:
- Terminal → Run Task → Smart Parking: הפעלת האתר
- Terminal → Run Task → Smart Parking: עצירת האתר

## מבנה הפרויקט

```text
Smart-Parking-VSCode/
├── .github/workflows/ci.yml
├── .vscode/tasks.json
├── .gitignore
├── docker-compose.yml
├── README.md
├── web/index.html
└── storage/images/
```

## GitHub Repository
1. צרו ב־GitHub מאגר חדש בשם `smart-parking`.
2. פתחו Terminal ב־VS Code מתוך תיקיית הפרויקט והריצו:

```bash
git init
git add .
git commit -m "Initial Smart Parking project"
git branch -M main
git remote add origin https://github.com/USERNAME/smart-parking.git
git push -u origin main
```

החליפו את `USERNAME` בשם המשתמש שלכם ב־GitHub.

## GitHub Actions Workflow
הקובץ `.github/workflows/ci.yml` מריץ בדיקות אוטומטיות לאחר העלאה ל־GitHub. כדי לראות אותן, פתחו את המאגר ב־GitHub ולחצו על Actions.

## מה הפרויקט מדגים
- `web`: שרת Nginx שמציג את האתר בפורט 8080.
- `storage`: שרת Apache שמגיש את תמונות הרכבים בפורט 8081.
- `docker-compose.yml`: מפעיל את שני השרתים יחד.
- `ci.yml`: בודק אוטומטית את הקבצים ואת זמינות האתר ושרת התמונות.
