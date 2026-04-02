# 入院タスク管理アプリ

病棟業務向けの入院患者タスク管理Webアプリです。

**URL**: https://syuzi327.github.io/inpatient-management/

---

## 概要

- 患者を登録するとテンプレートからタスクが自動生成される
- テンプレートはGoogleスプレッドシートで管理（スプシの「使い方」シート参照）
- データはブラウザのlocalStorageに保存。サーバー不要、ログイン不要
- 単一HTMLファイル構成。GitHub Pagesで動作

---

## 画面構成

| タブ | 役割 |
|------|------|
| 患者一覧 | 登録患者を入院日順に表示。100%完了患者はグレーアウトして最下部に移動 |
| 本日のタスク | 期限切れ（赤）・前日リマインダー（黄）・今日のタスクを表示 |
| フリータスク | 入院前タスク（未完了）と患者に紐づかない自由タスクを管理 |

---

## 技術構成

| 項目 | 内容 |
|------|------|
| 構成 | HTML + CSS + Vanilla JS（単一ファイル） |
| データ保存 | localStorage（キー：`admtasks`） |
| テンプレート取得 | Google Sheets 公開CSV（1時間キャッシュ） |
| ホスティング | GitHub Pages（mainブランチ push で自動デプロイ） |

---

## ファイル構成

```
index.html   アプリ本体（HTML・CSS・JS すべて含む）
README.md    このファイル
```

---

## デプロイ

```bash
git add index.html
git commit -m "変更内容"
git push
```

pushから反映まで約1〜2分。
