# NekoStream V2

## Included
- Firebase Authentication (Google sign-in)
- Firestore anime catalog
- Anime detail pages
- Episode subcollections
- Video player
- Favorites
- Watch history
- Admin panel
- Firestore security rules
- Mobile responsive UI

## 1. Create Firebase project
Open Firebase Console and create a project. Add a Web App and copy its config into `firebase-config.js`.

Enable:
- Authentication → Sign-in method → Google
- Firestore Database

## 2. Firestore structure
The app uses:
anime/{animeId}
anime/{animeId}/episodes/{episodeId}
admins/{yourUserUid}
users/{uid}/favorites/{animeId}
users/{uid}/history/{historyId}

## 3. Make yourself admin
First sign in once with Google. In Firebase Console → Firestore Database, create:
Collection: `admins`
Document ID: your Firebase Auth UID
You can leave the document empty.

Do NOT put a password or service-account JSON in the website.

## 4. Publish
This is a static website. Upload the folder to GitHub Pages, Cloudflare Pages, Firebase Hosting, or another static host.

## 5. Add content
Sign in as the admin → Admin → Add Anime → Add episode.
Use only video URLs/content you have permission to distribute.

## Important
Firebase web config values are intended to be public client configuration. Security comes from Firestore Rules and Authentication, not from hiding the web config. Never expose Firebase Admin SDK credentials/service-account keys in browser code.
