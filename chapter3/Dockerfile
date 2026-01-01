# Python 3.12のベースイメージを使用
FROM python:3.12-slim

# 作業ディレクトリを設定
WORKDIR /app

# システムパッケージのインストール（PostgreSQL接続に必要）
RUN apt-get update && apt-get install -y \
    curl \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# uvのインストール（公式の推奨方法）
COPY --from=ghcr.io/astral-sh/uv:latest /uv /usr/local/bin/uv

# pyproject.tomlとuv.lockをコピーして依存関係をインストール
COPY pyproject.toml uv.lock* ./

# uvで依存関係をインストール（dev依存も含む）
RUN uv sync --frozen

# アプリケーションコードをコピー
COPY . .

# Jupyterカーネルを登録
RUN uv run python -m ipykernel install --user --name genai_ch3 --display-name "Python 3.12 (Chapter 3)"

# Jupyter Notebookのポートを公開
EXPOSE 8888

# デフォルトコマンド（Jupyter Notebookを起動）
CMD ["uv", "run", "jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--NotebookApp.token=''", "--NotebookApp.password=''"]
