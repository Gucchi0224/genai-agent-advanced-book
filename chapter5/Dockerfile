# Python 3.12のベースイメージを使用
FROM python:3.12-slim

# 作業ディレクトリを設定
WORKDIR /app

# システムパッケージのインストール
RUN apt-get update && apt-get install -y \
    curl \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# uvのインストール（公式の推奨方法）
COPY --from=ghcr.io/astral-sh/uv:latest /uv /usr/local/bin/uv

# pyproject.tomlとuv.lockをコピーして依存関係をインストール
COPY pyproject.toml uv.lock* ./

# uvで依存関係をインストール（dev依存も含む）
RUN uv sync --frozen

# アプリケーションコードをコピー
COPY . .

# スクリプト実行用のデフォルトコマンド
CMD ["/bin/bash"]
