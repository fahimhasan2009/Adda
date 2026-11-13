# Adda — Firebase Text Sharing Social Media

সব source file `Adda-Firebase` folder-এর মধ্যে রাখা হয়েছে।

## এই build-এ কাজ করছে
- Firebase Email/Password signup, login, logout
- Firestore user profile create
- Real-time post feed
- Text post create
- Like/Unlike transaction
- Comment add ও list
- Post/author search
- Responsive premium UI
- Firestore security rules

## Firebase সেটআপ
1. https://console.firebase.google.com/ এ Adda project তৈরি করুন।
2. Project Overview → Add app → Web (</>) → Register app।
3. Web config থেকে apiKey, authDomain, projectId, storageBucket, messagingSenderId, appId নিন।
4. Build → Authentication → Get started → Sign-in method → Email/Password enable করুন।
5. Build → Firestore Database → Create database।
6. Firestore Rules-এ `firestore.rules`-এর সম্পূর্ণ content paste করে Publish করুন।
7. `.env.example`-এর copy করে `.env` নাম দিন এবং Firebase config বসান।

## Run
Node.js 18+ terminal:
```bash
npm install
npm run dev
npm run build
```

## GitHub (Android)
ZIP extract করে GitHub repository-তে `Adda-Firebase` folder-এর ভেতরের files এবং `src` folder upload করুন। `.env` upload করবেন না; `.gitignore` এটি বাদ রাখে। `.env.example` upload করা নিরাপদ।

## Firebase Hosting
Firebase CLI দরকার:
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
npm run build
firebase deploy
```
Hosting public directory `dist` দিন। `firebase.json` আগে থেকেই আছে; init-এর সময় overwrite করবেন না।

## Security
Firebase Web config frontend-এ ব্যবহার করা যায়; Firestore Rules access নিয়ন্ত্রণ করে। Firebase Admin SDK বা service account private key কখনো frontend/GitHub-এ দেবেন না। Rules publish না করে live data ব্যবহার করবেন না।

## পরবর্তী ধাপ
Follow/unfollow, Following feed, repost, bookmark persistence, automated notifications, admin dashboard, profile editing/photo upload এবং moderation tools পরবর্তী ধাপে যোগ করতে হবে।