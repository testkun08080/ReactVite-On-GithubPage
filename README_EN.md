[日本語](README.md) | English

# Overview
This document records the steps to deploy a documentation page built with React + Vite (+ Tailwind) to GitHub Pages.
The basic setup should be completed mainly through shell commands.

*Sample page is [here](https://testkun08080.github.io/ReactVite-On-GithubPage/)*

## Prerequisites
- npm, Node.js 20+ ([Download here](https://nodejs.org/en/download/))

## Setup (React - Vite + Tailwind) 🛠️

1. **Clone or download locally**
   ```bash
   git clone https://github.com/testkun08080/ReactVite-On-GithubPage.git
   cd ReactVite-On-GithubPage
   ```
   Or just download the script directly:
   ```bash
   curl -o setup-react-vite.sh https://raw.githubusercontent.com/testkun08080/ReactVite-On-GithubPage/main/setup-react-vite.sh
   ```

2. **If you have another repo where you want to create the page, copy the script there**
   ```bash
   cp setup-react-vite.sh /path/to/YourGitRepo/
   cd /path/to/YourGitRepo/
   ```

3. **Grant permission**
   ```bash
   chmod +x setup-react-vite.sh
   ```

4. **Run the setup command (use any name you like)**
   If you want to create the frontend as a separate folder under the root:
   ```bash
   #./setup-react-vite.sh SampleProject ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

   Or, if you want the root of the new repo to be the same as the frontend:
   ```bash
   #./setup-react-vite.sh ReactVite-On-GithubPage ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

5. **Test locally**
   After creation, move to the generated project folder and run it locally.
   You should be able to access it at localhost:5173/<PROJECT_NAME>.
   ```bash
   cd <PROJECT_NAME>
   npm run dev
   ```

## Deploy

#### 1A. If creating a new repository
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

#### 1B. If committing and pushing to an existing repo
1. **Commit and push:**
   ```bash
   git add .
   git commit -m "add react vite app"
   git push origin main
   ```

#### 2. Deploy the app
2. **Move to the React application folder:** 
   ```bash
   cd <PROJECT_NAME>
   ```
3. **Build and deploy for GitHub Pages**
   The build will be done in advance, and only the contents of the dist folder will be deployed.
   ```bash
   npm run deploy
   ```
4. **Check GitHub Pages**
   
   Also check if the deploy is complete in GitHub Actions.<br>
   Go to Settings > Pages > Visit Site to confirm the application is displayed correctly.<br>
   Or, go to your GitHub Pages URL (adjust for your project) for final confirmation:

   ```bash
   https://USER_NAME.github.io/REPO_NAME/
   ```
   
   Here is a sample from this repository:
   (https://testkun08080.github.io/ReactVite-On-GithubPage/)
