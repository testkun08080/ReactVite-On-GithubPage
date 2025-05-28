# Overview
This document records the steps to deploy a documentation page built with React + Vite (+ Tailwind) to GitHub Pages.
The basic setup should be completed mainly through shell commands.

## Set Up Yourself Using the Script (React - Vite + Tailwind) 🛠️

1. **Download the Shell Script:**  
   This script creates a web application template based on React-Vite with Tailwind applied.  
   It also sets up deployment to GitHub Pages.
   ```bash
   setup-react-vite.sh
   ```
2. **Grant Execute Permission to the Script:**  
   ```bash
   chmod +x setup-react-vite.sh
   ```
3. **Run the Setup Script (choose any name you like):**  
   Be sure to specify the frontend folder name, repository name, and your GitHub username.
   ```bash
   # ./setup-react-vite.sh SampleProject ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```
4. **Test Locally:**  
   After creation, run the following command to start the app locally.  
   You should be able to access it at localhost:5173/<PROJECT_NAME>.
   ```bash
   npm run dev
   ```

## Deployment
1. **Initial Commit:**  
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```
2. **Create Repository:**  
   Create the repository manually, or use the GitHub CLI below.
   ```bash
   gh repo create --public --source=.
   ```
3. **Push to GitHub:**  
   ```bash
   git branch -M main 
   git push -u origin main
   ```
4. **Move to the React Application Folder:**  
   ```bash
   cd <Your_App_Folder>
   ```
5. **Build and Deploy for GitHub Pages:**  
   The build will be done in advance, and only the contents of the dist folder should be deployed.
   ```bash
   npm run deploy
   ```
6. **Check GitHub Pages:**  
   Check the following URL, or  
   go to Settings > Pages > Visit Site to see if the application displays correctly.  
   Also, check if the deploy is complete in GitHub Actions.  
   Finally, visit your GitHub Pages site like below for final confirmation:  
   (https://USER_NAME.github.io/REPO_NAME/)
   Below is a sample of this page
   (https://testkun08080.github.io/ReactVite-On-GithubPage/)