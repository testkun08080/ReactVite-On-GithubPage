[日本語](README.md) | English

# Overview

This document records the steps to deploy a documentation page built with React + Vite (+ Tailwind) to GitHub Pages.
Most of the basic setup should be completed using shell commands.

*Sample page is [here](https://testkun08080.github.io/ReactVite-On-GithubPage/)*

### Prerequisites
- git cli([Install here](https://cli.github.com/))
- npm, Node.js 20+ ([Download here](https://nodejs.org/en/download/))

---

## Setup (React - Vite + Tailwind) 🛠️

1. **Clone or download locally**
   ```bash
   git clone https://github.com/testkun08080/ReactVite-On-GithubPage.git
   cd ReactVite-On-GithubPage
   ```
   Or download the setup script directly:
   ```bash
   curl -o setup-react-vite.sh https://raw.githubusercontent.com/testkun08080/ReactVite-On-GithubPage/main/setup-react-vite.sh
   ```

2. **Copy the script to your target repo if you want to create a page there**
   ```bash
   cp setup-react-vite.sh /path/to/YourGitRepo/
   cd /path/to/YourGitRepo/
   ```

3. **Grant execute permission**
   ```bash
   chmod +x setup-react-vite.sh
   ```

4. **Run the setup command (choose your own names)**
   If you want to create the frontend in a separate folder under the root:
   ```bash
   # ./setup-react-vite.sh SampleProject ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

   Or, if you want the frontend at the root of a new repo:
   ```bash
   # ./setup-react-vite.sh ReactVite-On-GithubPage ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

5. **Test locally:**
   After creation, move into the generated project folder and run locally.
   You should be able to access it at localhost:5173/<PROJECT_NAME>.
   ```bash
   cd <PROJECT_NAME>
   npm run dev
   ```

---

## Deploy

- ### 1(A). If creating a new repository

  1. **Initial commit:** 
    ```bash
    git init
    git add .
    git commit -m "Initial commit"
    ```
  2. **Create repository:** 
    ```bash
    gh repo create --public --source=.
    ```
  3. **Push:** 
    ```bash
    git branch -M main
    git push -u origin main
    ```

- ### 1(B). If committing and pushing to an existing repo

  1. **Commit and push:**
    ```bash
    git add .
    git commit -m "add react vite app"
    git push origin main
    ```

- ### 2. Deploy the app

  1. **Move to the React app folder:** 
    ```bash
    cd <PROJECT_NAME>
    ```
  2. **Build and deploy for GitHub Pages**
     This will build the app and deploy only the contents of the `dist` folder.
     ```bash
     npm run deploy
     ```
  3. **Check GitHub Pages**
    
     Make sure the deploy is complete in GitHub Actions.<br>
     Go to Settings > Pages > Visit Site to check if your app is displayed correctly.<br>
     Or, visit your GitHub Pages URL (adjust for your project):

     ```bash
     https://USER_NAME.github.io/REPO_NAME/
     ```
    
     Here is the sample for this repository:
     (https://testkun08080.github.io/ReactVite-On-GithubPage/)
