日本語 | [English](README_EN.md)

# 概要
React + Vite ( + Tailwind )を使ったドキュメントページをGithubPage 上へデプロイするまでの流れを記録したものです。
shell コマンドによって基本的には基礎となる設定は完了するはずです。

*サンプルページは[こちら](https://testkun08080.github.io/ReactVite-On-GithubPage/)*

## 事前インストール必要なもの
- npm Node.js 20+ (インストールは[こちら](https://nodejs.org/en/download/))



## セットアップ (React - Vite + Tailwind) 🛠️

1. **ダウンロードシェルコマンドスクリプト:** 
  React-ViteをベースとしたTailwindを適用するwebアプリケーションのテンプレートを作成します。
  さらに、GitHubPageへのデプロイも兼ねた設定も行います。
   ```bash
    setup-react-vite.sh
   ```
1. **パーミッション付与用のコマンド:** 
   ```bash
    chmod +x setup-react-vite.sh
   ```
2. **セットアップ用コマンドの実行(名前はお好みで)**
    必ず、フロントエンドのフォルダ名と、作るレポジトリの名前、Githubのユーザー名を入れてください
    ```bash
   #./setup-react-vite.sh SampleProject ReactVite-On-GithubPage testkun08080
    ./setup-react-vite.sh <PROJECT_NAME> <REPO_NAME> <USER_NAME>
   ```
3. **ローカルでテスト**
    作成し終わったら、以下コマンドでローカル実行してみてください。
    localhost:5173/<PROJECT_NAME>でアクセスできるはずです。
    ```bash
    npm run dev
   ```

## デプロイ
1. **初期コミット:** 
   ```bash
    git init
    git add .
    git commit -m "Initial commit"
2. **レポジトリ作成:** 
   手動でレポジトリを作成、もしくは以下Github CLIを使用
   ```bash
   gh repo create --public --source=.
   ```
3. **プッシュ:** 
   ```bash
    git branch -M main 
    git push -u origin main
   ```
4. **Reactアプリケーションフォルダへ移動:** 
   ```bash
    cd <Your_App_Folder>
   ```
5. **GitHubPage用にビルドとデプロイ**
    事前にbuildも行われて、distフォルダの中身のみがデプロイされずはずです
    ```bash
    npm run deploy
   ```
6. **GitHubPageの確認**
   
    Git Actionsでdeployが完了しているかどうかも確認してください。<br>
   Settings > Pages > Visit Site で アプリケーションが正常に表示されるか確認してみてください。<br>
   もしくは、以下のような　github page URL(適宜、ご自分のプロジェクトに合わせて)に行って最終確認をして下さい。

    ```bash
    https://USER_NAME.github.io/REPO_NAME/
   ```
   
   こちらは、このレポジトリのサンプルです。
   (https://testkun08080.github.io/ReactVite-On-GithubPage/)
