日本語 | [English](README_EN.md)

# 概要
React + Vite ( + Tailwind )を使ったドキュメントページをGithubPage 上へデプロイするまでの流れを記録したものです。
shell コマンドによって基本的には基礎となる設定は完了するはずです。

*サンプルページは[こちら](https://testkun08080.github.io/ReactVite-On-GithubPage/)*

## 事前インストール必要なもの
- npm Node.js 20+ (インストールは[こちら](https://nodejs.org/en/download/))
- 

## セットアップ (React - Vite + Tailwind) 🛠️

1. **ローカルへクローンorダウンロード**
    ```bash
    git clone https://github.com/testkun08080/ReactVite-On-GithubPage.git
    cd ReactVite-On-GithubPage
   ```
   もしくは直接スクリプトだけダウンロードしてください
   ```bash
   curl -o setup-react-vite.sh https://raw.githubusercontent.com/testkun08080/ReactVite-On-GithubPage/main/setup-react-vite.sh
   ```

2. **ページを作成したいレポがあれば、そちらにスクリプトをコピーしてください**
   ```bash
   cp setup-react-vite.sh /path/to/YourGitRepo/
   cd /path/to/YourGitRepo/
   ```

3. **パーミッション付与**
   ```bash
   chmod +x setup-react-vite.sh
   ```

4. **セットアップ用コマンドの実行(名前はお好みで)**
   フロントエンドをルート以下に別フォルダとして作成したい場合
   ```bash
   #./setup-react-vite.sh SampleProject ReactVite-On-GithubPage testkun08080
    ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

   or もし新しいレポのルートをフロントエンドと同じにしたい場合
    ```bash
   #./setup-react-vite.sh ReactVite-On-GithubPage ReactVite-On-GithubPage testkun08080
    ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```

5. **ローカルでテスト:**
    作成し終わったら、作成されたプロジェクトフォルダへ移動して、ローカル実行してみてください。
    localhost:5173/<PROJECT_NAME>でアクセスできるはずです。
    ```bash
    cd <PROJECT_NAME>
    npm run dev
   ```

## デプロイ

#### 1A.レポジトリを作成新しく作る場合
1. **初期コミット:** 
   ```bash
    git init
    git add .
    git commit -m "Initial commit"
2. **レポジトリ作成:** 
   ```bash
   gh repo create --public --source=.
   ```
3. **プッシュ:** 
   ```bash
    git branch -M main
    git push -u origin main
   ```

#### 1B.既存レポへコミットしてプッシュする場合
1. **コミットとプッシュ:**
   ```bash
   git add .
   git commit -m "add react vite app"
   git push origin main
   ```

#### 2.アプリをデプロイする
2. **Reactアプリケーションフォルダへ移動:** 
   ```bash
    cd <PROJECT_NAME>
   ```
3. **GitHubPage用にビルドとデプロイ**
    事前にbuildも行われて、distフォルダの中身のみがデプロイされずはずです
    ```bash
    npm run deploy
   ```
4. **GitHubPageの確認**
   
    Git Actionsでdeployが完了しているかどうかも確認してください。<br>
   Settings > Pages > Visit Site で アプリケーションが正常に表示されるか確認してみてください。<br>
   もしくは、以下のような　github page URL(適宜、ご自分のプロジェクトに合わせて)に行って最終確認をして下さい。

    ```bash
    https://USER_NAME.github.io/REPO_NAME/
   ```
   
   こちらは、このレポジトリのサンプルです。
   (https://testkun08080.github.io/ReactVite-On-GithubPage/)
