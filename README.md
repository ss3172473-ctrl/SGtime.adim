# Code Issuance Page Deployment Guide

Since the Vercel/GitHub CLI tools are not installed locally, please follow these steps to deploy the page.

## 1. Push to GitHub
1.  Create a **new repository** on [GitHub](https://github.com/new).
2.  Run the terminal commands below in this folder to push your code:
    ```bash
    git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
    git branch -M main
    git push -u origin main
    ```

## 2. Deploy to Vercel
1.  Go to [Vercel Dashboard](https://vercel.com/dashboard).
2.  Click **Add New Project**.
3.  Select **Continue with GitHub** and choose the repository you just created.
4.  **Configure Project**:
    - **Framework Preset**: Select `Other` (if not auto-detected).
    - **Root Directory**: `./` (Default).
    - **Build Command**: Leave empty.
    - **Output Directory**: Leave empty (or `./`).
5.  Click **Deploy**.

## 3. Firebase Security Rules
1.  Go to the [Firebase Console](https://console.firebase.google.com/).
2.  Select your project (`sungongsigan-platform`).
3.  Navigate to **Firestore Database** > **Rules**.
4.  Copy the content of the `firestore.rules` file included in this folder and paste it into the editor.
    - *Note: These rules allow open access since the current app doesn't use User Authentication.*

## 4. Test
1.  Open the Vercel deployment URL.
2.  Try generating a code.
3.  Check the Firebase Console > **Data** tab to see if the creating appears in `codes` collection.
