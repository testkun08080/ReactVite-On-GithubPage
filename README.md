日本語 | [English](README_EN.md)
# 概要
React + Vite (+ Tailwind) を使ったドキュメントページを GitHub Pages 上へデプロイするまでの流れを記録したものです。  
基本的な設定はシェルコマンドで完了します。

*サンプルページは[こちら](https://testkun08080.github.io/ReactVite-On-GithubPage/)*

### 事前インストールが必要なもの
- Node.js 20+ および npm（[インストールはこちら](https://nodejs.org/en/download/)）

---

## セットアップ (React - Vite + Tailwind) 🛠️

1. **ローカルへクローンまたはダウンロード**
   ```bash
   git clone https://github.com/testkun08080/ReactVite-On-GithubPage.git
   cd ReactVite-On-GithubPage
   ```
   またはスクリプトのみダウンロード
   ```bash
   curl -o setup-react-vite.sh https://raw.githubusercontent.com/testkun08080/ReactVite-On-GithubPage/main/setup-react-vite.sh
   ```

2. **ページを作成したいリポジトリにスクリプトをコピー**
   ```bash
   cp setup-react-vite.sh /path/to/YourGitRepo/
   cd /path/to/YourGitRepo/
   ```

3. **パーミッション付与**
   ```bash
   chmod +x setup-react-vite.sh
   ```

4. **セットアップ用コマンドの実行（名前は任意）**
   フロントエンドをルート以下の別フォルダに作成したい場合
   ```bash
   # ./setup-react-vite.sh SampleProject ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

   もしくは新しいリポジトリのルートをフロントエンドと同じにしたい場合
   ```bash
   # ./setup-react-vite.sh ReactVite-On-GithubPage ReactVite-On-GithubPage testkun08080
   ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

5. **ローカルでテスト**
   作成されたプロジェクトフォルダへ移動し、ローカルで実行してください。  
   `localhost:5173` でアクセスできるはずです。
   ```bash
   cd <PROJECT_NAME>
   npm run dev
   ```

---

## デプロイ

- ### 1(A). 新しくリポジトリを作成する場合

  1. **初期コミット:** 
    ```bash
    git init
    git add .
    git commit -m "Initial commit"
    ```
  2. **リポジトリ作成:** 
    ```bash
    gh repo create --public --source=.
    ```
  3. **プッシュ:** 
    ```bash
    git branch -M main
    git push -u origin main
    ```

- ### 1(B). 既存リポジトリへコミットしてプッシュする場合
  1. **コミットとプッシュ:**
    ```bash
    git add .
    git commit -m "add react vite app"
    git push origin main
    ```

- ### 2. アプリをデプロイする
  1. **React アプリケーションフォルダへ移動:** 
    ```bash
    cd <PROJECT_NAME>
    ```
  2. **GitHub Pages 用にビルドとデプロイ**
    事前に build も行われ、`dist` フォルダの中身のみがデプロイされます。
    ```bash
    npm run deploy
    ```
  3. **GitHub Pages の確認**

    GitHub Actions で deploy が完了しているか確認してください。  
    Settings > Pages > Visit Site でアプリケーションが正常に表示されるか確認してください。  
    または、以下のような GitHub Pages の URL（ご自身のプロジェクトに合わせて）で最終確認してください:

    ```
    https://USER_NAME.github.io/REPO_NAME/
    ```

    こちらはこのリポジトリのサンプルです。  
    [https://testkun08080.github.io/ReactVite-On-GithubPage/](https://testkun08080.github.io/ReactVite-On-GithubPage/)

