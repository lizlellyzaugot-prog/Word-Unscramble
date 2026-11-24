# Word Unscramble Game

A fun and interactive word unscrambling game built with HTML, CSS, and JavaScript, with Firebase integration for real-time data management.

## 🎮 Features

- **Interactive Gameplay**: Challenge yourself to unscramble words
- **Real-time Database**: Uses Firebase Realtime Database to store and retrieve game data
- **Responsive Design**: Beautiful gradient UI with smooth animations
- **User-Friendly Interface**: Clean and intuitive design with modal dialogs
- **Score Tracking**: Keep track of your game progress
- **Dynamic Word Generation**: Randomly generated scrambled words for variety

## 🛠️ Technologies Used

- **HTML5**: Markup and structure
- **CSS3**: Styling with gradients and animations
- **JavaScript (Vanilla)**: Game logic and interactivity
- **Firebase Realtime Database**: Backend data storage
- **Firebase SDK v8.10.1**: Cloud services integration

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v12 or higher) - [Download](https://nodejs.org/)
- **npm** (comes with Node.js)
- A **Google Account** (for Firebase)
- A modern web browser (Chrome, Firefox, Safari, Edge)

## 🚀 Getting Started

### 1. Clone or Download the Project

```bash
# If cloning from repository
git clone <repository-url>
cd word-unscramble-game

# Or simply download the files
```

### 2. Install Firebase CLI

```bash
npm install -g firebase-tools
```

### 3. Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com)
2. Click **"Create a project"**
3. Enter your project name (e.g., "Word Unscramble Game")
4. Follow the setup wizard and complete the project creation

### 4. Set Up Firebase Realtime Database

1. In Firebase Console, navigate to **Realtime Database**
2. Click **"Create Database"**
3. Choose location and start in **Test Mode** (for development)
   - ⚠️ For production, use **Locked Mode** with proper security rules
4. Copy your **Database URL** (format: `https://your-project.firebaseio.com`)

### 5. Get Your Firebase Configuration

1. Go to **Project Settings** (⚙️ icon)
2. Scroll to "Your apps" section
3. Click the web app icon (`</>`), or add a new app
4. Copy the Firebase configuration object

Your config should look like:
```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  databaseURL: "https://YOUR_PROJECT.firebaseio.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID"
};
```

### 6. Update Your index.html

Locate the Firebase configuration section in `index.html` (search for `firebaseConfig`) and replace it with your actual credentials.

### 7. Test Locally

```bash
# Option 1: Use Python's built-in server
python -m http.server 8000

# Option 2: Use Node.js http-server
npx http-server

# Option 3: Use Firefox - just open the file directly
```

Then open `http://localhost:8000` in your browser.

## 📦 Deployment to Firebase Hosting

### Step 1: Initialize Firebase in Your Project

```bash
firebase login
```

This will open a browser window to authenticate with your Google account.

### Step 2: Initialize Firebase Project

```bash
firebase init
```

When prompted:
- Select **"Hosting"** using arrow keys and space
- Choose your Firebase project
- For public directory, enter: `.` (current directory) or `public`
- Configure as single-page app: **No** (unless applicable)
- Do NOT overwrite `index.html` if it already exists

### Step 3: Prepare Deployment Files (Optional)

If you chose `public` as the directory, move your files:

```bash
mkdir public
copy index.html public\
```

### Step 4: Deploy to Firebase

```bash
firebase deploy
```

After deployment, Firebase will provide your live URL:
```
Hosting URL: https://your-project-name.web.app
```

## 🎯 How to Play

1. **Start the Game**: Open the application in your browser
2. **View the Scrambled Word**: A random word will appear, scrambled
3. **Unscramble**: Rearrange the letters to form the correct word
4. **Submit**: Click "Submit" or press Enter to check your answer
5. **Score Points**: Earn points for correct answers
6. **Challenge Yourself**: Continue playing to improve your score

## 📁 Project Structure

```
word-unscramble-game/
├── index.html          # Main HTML file with embedded CSS and JavaScript
├── README.md           # This file
└── firebase.json       # Firebase configuration (created after initialization)
```

## 🔒 Firebase Security Rules

For **production deployment**, add these security rules to your Realtime Database:

```json
{
  "rules": {
    ".read": "auth != null",
    ".write": "auth != null"
  }
}
```

For more information, see [Firebase Security Rules Documentation](https://firebase.google.com/docs/database/security).

## ⚠️ Important Notes

- **API Keys**: Keep your Firebase credentials in environment variables for production
- **Test Mode Warning**: Test Mode allows anyone to read/write data. Use Locked Mode for production
- **CORS**: Firebase SDK handles CORS automatically
- **Browser Support**: Works on all modern browsers (Chrome, Firefox, Safari, Edge)

## 🐛 Troubleshooting

### Firebase Connection Issues
- Check if your Firebase credentials are correct in `index.html`
- Verify your database URL in Firebase Console
- Check browser console (F12) for error messages

### Database Read/Write Errors
- Ensure you're in **Test Mode** or have correct **Security Rules**
- Check database URL format
- Verify network connection

### Deployment Issues
```bash
# Clear Firebase cache
firebase logout
firebase login

# Try deployment again
firebase deploy --debug
```

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements.

## 📄 License

This project is open source and available under the MIT License.

## 📞 Support

For Firebase issues, visit:
- [Firebase Documentation](https://firebase.google.com/docs)
- [Firebase Community](https://firebase.google.com/community)

For general web development help:
- [MDN Web Docs](https://developer.mozilla.org/)
- [Stack Overflow](https://stackoverflow.com/)

## 🎉 Enjoy the Game!

Happy playing and good luck with your unscrambling! 🎮

---

**Last Updated**: November 2026  
**Firebase SDK Version**: 8.10.1
