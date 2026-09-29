# Personal Expense Tracker

A simple web app to record and manage daily expenses. Built with HTML, CSS, JavaScript and Firebase Firestore.

## Features
- Add an expense with title, amount, category (Food, Travel, Shopping, Bills, Other) and date
- All records are stored in Firebase Firestore (`expenses` collection)
- Expenses appear live in a table below the form
- Delete any expense
- Shows total number of expenses and total amount spent

## Setup
1. Go to the [Firebase console](https://console.firebase.google.com) and create a project.
2. Build → **Firestore Database** → Create database (start in test mode for the assignment).
3. Project settings → **Your apps** → add a **Web app** and copy the `firebaseConfig` object.
4. Open `index.html` and replace the placeholder `firebaseConfig` values.
5. Open `index.html` in a browser (or serve it with any static server) and add an expense.

## Firestore rules (for the assignment)
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /expenses/{id} {
      allow read, write: if true;
    }
  }
}
```
These rules are open to anyone. Fine for a demo, but add authentication before real use.

## Deploy
**Firebase Hosting**
```
npm install -g firebase-tools
firebase login
firebase init hosting   # public directory: . , single-page app: No
firebase deploy
```
Your live URL will be `https://<project-id>.web.app`.

**Alternative: GitHub Pages**
Push the repo, then Settings → Pages → Deploy from branch `main` / root.
