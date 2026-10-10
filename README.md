# SORACOM Flux AI画像判定ハンズオン

スマートフォンで撮影した写真を **SORACOM Harvest Files** にアップロードし、それをトリガーに **SORACOM Flux** を起動、**AI（Google Gemini）が画像からメーターの数値を読み取って Discord に通知する** までを体験するハンズオン資料です。

SORACOM UG 広島のハンズオンイベント用に作成しています。

## このハンズオンの主役

アップロード用の Web アプリ（[soracom-harvest-uploader](https://github.com/tyamon1006/soracom-harvest-uploader)）は「写真をアップロードするための入口」にすぎません。
**本題は、アップロードをトリガーに Flux 上で AI が画像を判定し、結果を通知するパイプラインを自分で組み立てること**です。

```
スマホで撮影
  │  ① アップローダアプリ（入口／使い方だけ簡単に説明）
  ▼
SORACOM Harvest Files
  │  ② ファイル作成/更新イベント（トリガー）
  ▼
SORACOM Flux
  ├─ Harvest Files Event Channel … トリガー
  ├─ AIブロック「数値読み取り」    … Gemini 2.5 Flash-Lite が画像→メーター値をJSON抽出
  └─ Webhook「Discord通知」        … 読み取り結果をDiscordへ通知
```

## 資料本体

- 手順書: [`docs/handson.md`](docs/handson.md)

## ライセンス / 注意

- このリポジトリは SORACOM UG HIROSHIMA のハンズオンイベント用に作成されたものです。
- 資料内の Discord Webhook URL・ログイン情報・認証キーはすべてプレースホルダ（例: `<あなたのWebhook URL>`）です。実運用の値はコミットしないでください。
