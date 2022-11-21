# python3-whisper
whisperを使うためのDocker環境を構築します。


## 注意点
CUDA(GPU)には対応していません。

## 構成
```bash
.
├── Dockerfile
├── LICENSE
├── README.md
├── docker-compose.yml
└── sound
    └── sample.mp3
```

(著作権の都合でsample.mp3は.gitignoreで消してます。)

## ダウンロード
git clone等でローカルにダウンロードしてください。
```bash
git clone https://github.com/Charlie-Aki/python3-whisper
```

## 使い方
ダウンロードしたフォルダに移動します。
```bash
cd python3-whisper
```
下記コマンドでpython3-whisperというpython3のコンテナが立ち上がります。
```bash
docker compose up -d
```
`docker ps -a`とすると&darr;こんな感じになるはず。
```
CONTAINER ID   IMAGE                COMMAND                  CREATED          STATUS          PORTS                    NAMES
c2e038cdc7eb   python:3-slim        "python3"                55 seconds ago   Up 54 seconds                            python3-whisper
```


その後`docker exec`で`bash`を立ち上げます。
```bash
docker exec -it python3-whisper bash
```
whisperを用いて音声ファイルをテキストファイルに書き出します。(この例ではデフォルトのsmallモデルを使用)
```bash
whisper ./sound/sample.mp3 --language ja
```

## 参考にしたURL
https://zenn.dev/kento1109/articles/d7d8f512802935
