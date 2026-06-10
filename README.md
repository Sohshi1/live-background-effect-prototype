# Live Background Effect Prototype

MediaPipeを使って人物領域を推定し、人物を避けながら背景側にだけ簡易CGエフェクトを重ねる研究プロトタイプです。

## できること

- 動画ファイルまたはWebカメラ映像を入力できる
- MediaPipe Image Segmenterで人物領域と背景領域を分離する
- 人物領域を避けて、背景側だけに粒子・光・色変化を重ねる
- MediaPipe Face Detectorで顔の検出位置を確認できる
- FPSとセグメンテーション処理時間を画面上で確認できる

## 使い方

```bash
python3 -m http.server 5173
```

ブラウザで以下を開きます。

```text
http://localhost:5173/
```

初回起動時にMediaPipeのWASMとモデルをCDNから読み込むため、ネットワーク接続が必要です。

## 研究上の位置づけ

ライブ配信やDVDなどの映像に後から演出を重ねると、出演者の顔や体を隠してしまう可能性があります。このプロトタイプでは、まず人物領域を避けて背景にだけエフェクトを載せられるかを確認します。

Background Matting V2などの高精度mattingを試す前段階として、ブラウザ上で軽量に動くMediaPipeを使い、実装可能性と見え方を確認することを目的にしています。

## 使用技術

- HTML
- CSS
- JavaScript
- MediaPipe Tasks Vision
