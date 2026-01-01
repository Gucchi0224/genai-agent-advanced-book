# AIエージェント実践入門 第3章

本プロジェクトは「AIエージェント実践入門」第3章のサンプルコードを実行するための環境です。

## 前提条件

このプロジェクトを実行するには、以下の準備が必要です：

- Python 3.12 以上
- Docker および Docker Compose
- VSCode
- VSCodeのMulti-root Workspaces機能を使用し、ワークスペースとして開いている（やり方は[こちら](../README.md)を参照）
- OpenAIのアカウントとAPIキー
- TAVILYのアカウントとAPIキー

また、Python の依存関係は `pyproject.toml` に記載されています。

## 環境構築

以下の2つの方法で環境を構築できます：
1. **Docker環境**（推奨）：簡単に環境構築できます
2. **ローカル環境（uv使用）**：より細かい制御が必要な場合

### 方法1: Docker環境での構築（推奨）

#### 1. 環境変数の設定

`.env.example`ファイルをコピーして`.env`ファイルを作成し、APIキーを設定してください。

```bash
cp .env.example .env
```

`.env`ファイルの内容を編集：
```env
# OpenAI API設定
# OpenAI APIキーを持っていない場合は、[OpenAIの公式サイト](https://platform.openai.com/)から取得してください。
OPENAI_API_KEY=your_openai_api_key

# Tavily API設定（WEB検索用）
# https://tavily.com でアカウントを作成してAPIキーを取得してください
TAVILY_API_KEY=your_tavily_api_key
```

#### 2. Docker環境の起動

以下のコマンドでPostgreSQLとPython環境（Jupyter Notebook）を起動します：

```bash
docker-compose up -d
```

初回起動時はイメージのビルドに時間がかかります。

#### 3. Jupyter Notebookへのアクセス

ブラウザで以下のURLにアクセスします：
```
http://localhost:8888
```

#### 4. Pythonスクリプトの実行

コンテナ内でPythonスクリプトを実行する場合：

```bash
docker-compose exec app uv run python your_script.py
```

#### 5. 環境の停止

```bash
docker-compose down
```

データを削除して完全にクリーンアップする場合：
```bash
docker-compose down -v
```

### 方法2: ローカル環境での構築（uv使用）

#### 1. chapter3のワークスペースを開く
chapter3 ディレクトリに仮想環境を作成します。
VSCode の ターミナルの追加で`chapter3` を選択します。

#### 2. uvのインストール

依存関係の解決には`uv`を利用します。
`uv`を使ったことがない場合、以下の方法でインストールしてください。

`pip`を使う場合：
```bash
pip install uv
```

MacまたはLinuxの場合：
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

#### 3. Python 仮想環境の作成と依存関係のインストール

依存関係のインストール
```bash
uv sync
```

インストール後に作成した仮想環境をアクティブにします。

```bash
source .venv/bin/activate
```

#### 4. 環境変数のセット
.env.exampleファイルをコピーし、以下の内容を追記した`.env` ファイルを作成してください。

```bash
cp .env.example .env
```

```env
# OpenAI API設定
# OpenAI APIキーを持っていない場合は、[OpenAIの公式サイト](https://platform.openai.com/)から取得してください。
OPENAI_API_KEY=your_openai_api_key

# Tavily API設定（WEB検索用）
# https://tavily.com でアカウントを作成してAPIキーを取得してください
TAVILY_API_KEY=your_tavily_api_key
```