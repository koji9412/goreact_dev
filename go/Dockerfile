# 使用するベースイメージ
FROM golang:latest

# 作業ディレクトリを設定
WORKDIR /app

# Goモジュールの有効化
RUN go mod init app

# ホストマシンのGoのソースコードをコンテナにコピー
COPY . .

# 必要なツールやライブラリをインストール
# 例: ホットリロードツールのairをインストール
RUN go install github.com/cosmtrek/air@latest

# コンテナを起動する際のコマンドを設定 (ローカル環境用)
CMD ["air", "-c", ".air.toml"]

# 以下は本番環境用
# アプリケーションをビルド
# RUN go build -o main .
#
# アプリケーションを直接実行
# CMD ["./main"]
