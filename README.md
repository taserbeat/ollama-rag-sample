# ollama-rag-sample

Ollama の生成 AI モデルで RAG を試す

# 実行方法

Docker でコンテナを起動する。

```bash
docker compose up -d
```

Ollama のコンテナに入り、モデルをダウンロードする。

```bash
# コンテナにログイン
docker compose exec ollama bash

# モデルをダウンロード
ollama pull gemma3:4b
ollama pull embeddinggemma:300m

# コンテナからログアウト
exit
```

テキスト生成の API を呼び出す。

```bash
curl -X POST http://localhost:11434/api/generate -d '{"model": "gemma3:4b", "prompt": "地球の地軸はなぜ傾いているの？", "stream": false}'
```

テキストの埋め込み API を呼び出す。

```bash
curl -X POST http://localhost:11434/api/embed -d '{"model": "embeddinggemma:300m", "input": "なぜ空は青いの？"}'
```

# 終了方法

```bash
docker compose down --volumes --remove-orphans
```

モデルファイルが数 GB になるので、ストレージ圧迫を気にするなら`.ollama`フォルダも削除しておく。

```bash
rm -r ./.ollama
```

# 参考

- [Ollama | GitHub](https://github.com/ollama/ollama)
- [Ollama REST API](https://github.com/ollama/ollama/blob/main/docs/api.md)
- [Ollama Library](https://ollama.com)
