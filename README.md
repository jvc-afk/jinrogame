# 🎮 Nihongo Survival — Jinro Game

Game học tiếng Nhật dạng sói ma cà rồng (Jinro/Werewolf) nhiều người chơi.
Single-file HTML5 + Firebase Realtime Database.

**Live URL:** https://sensei-ai-mvp.web.app
**Firebase project:** `sensei-ai-mvp`

---

## 📁 Cấu trúc

```
jinrogame/
├── public/
│   └── index.html          ← Toàn bộ game (HTML + CSS + JS)
├── firebase.json           ← Cấu hình Firebase Hosting
├── .firebaserc             ← Firebase project binding
├── .github/
│   └── workflows/
│       └── deploy.yml      ← CI/CD: auto-deploy khi push lên main
└── README.md
```

---

## 🚀 Deploy thủ công

```bash
# Cài Firebase CLI (lần đầu)
npm install -g firebase-tools

# Đăng nhập Firebase
firebase login

# Deploy
firebase deploy --only hosting
```

---

## 🔄 Workflow phát triển

```bash
# Chỉnh sửa game
nano public/index.html

# Commit và push → GitHub Actions sẽ tự deploy
git add public/index.html
git commit -m "fix: mô tả thay đổi"
git push origin main
```

---

## ⚙️ Setup GitHub Actions (lần đầu)

1. Vào repo GitHub → **Settings → Secrets and variables → Actions**
2. Tạo secret tên `FIREBASE_SERVICE_ACCOUNT_SENSEI_AI_MVP`
3. Nội dung secret = JSON của Firebase service account
   (Lấy từ: Firebase Console → Project Settings → Service accounts → Generate new private key)

---

## 🔥 Firebase

- **Database:** `sensei-ai-mvp-default-rtdb.asia-southeast1.firebasedatabase.app`
- **Auth:** Anonymous authentication
- **Hosting:** `sensei-ai-mvp.web.app` / `sensei-ai-mvp.firebaseapp.com`
