# 予防接種管理アプリ (vax-schedule-app)

このプロジェクトは、NestJS(バックエンド)、Expo(フロントエンド)、PostgreSQL(データベース)を使用した予防接種スケジュール管理アプリケーションです。
開発環境は、VS Code Dev Containers を用いてDocker上で完結するように構成されています。

## システム構成

| コンポーネント | 技術スタック                               |
| :------------- | :----------------------------------------- |
| **フロントエンド** | Expo (React Native), TypeScript            |
| **バックエンド**   | NestJS, TypeScript, Prisma                 |
| **データベース**   | PostgreSQL                                 |
| **実行・開発環境** | Docker, Docker Compose, VS Code Dev Containers |

---

## 開発環境の構築手順

ローカルマシンに必要なのは、Git, Docker Desktop, VS Code (+ Dev Containers拡張機能) のみです。

### 前提条件

- Git
- Docker Desktop
- Visual Studio Code
- [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) VS Code 拡張機能

### 手順

1.  **リポジトリをクローン**
    ```bash
    git clone <リポジトリのURL>
    cd vax-schedule-app
    ```

2.  **VS Codeでプロジェクトを開く**
    ```bash
    code .
    ```

3.  **コンテナで再度開く**
    - VS Codeを開くと、右下に「Reopen in Container」という通知が表示されます。これをクリックしてください。
    - どのコンテナを開くか尋ねられたら、開発したい方を選択します。
      - **`From 'backend/devcontainer.json'`**: バックエンド開発用
      - **`From 'frontend/devcontainer.json'`**: フロントエンド開発用
    - VS Codeが自動的にDockerイメージのビルドとコンテナの起動、開発環境のセットアップを行います。

    *(通知が表示されない場合: `Ctrl+Shift+P` でコマンドパレットを開き、「Dev Containers: Reopen Folder in Container」を選択してください)*

## 開発の始め方

コンテナの起動が完了すると、開発サーバーは自動的に起動します。

- **バックエンドサーバー:** `http://localhost:3000`
  - `command: pnpm run start:dev` が実行され、ホットリロードが有効な状態で起動します。
- **フロントエンドサーバー:** `http://localhost:8081`
  - `command: pnpm start` が実行され、WebプレビューやExpo Go用のQRコードがターミナルに表示されます。

ソースコードを編集すると、変更は自動的にコンテナ内の開発サーバーに反映されます。