# 推薦文生成ツール

入力された候補者情報だけを根拠に、事実に基づいた日本語の推薦文を AI で自動生成するツール。現代的なモダン UI と正確な生成ロジックが特徴です。

## ローカル開発

### 1. 環境変数の設定

`.env.example` をコピーして `.env` を作成し、OpenAI API キーを設定してください。

```bash
cp .env.example .env
```

### 2. サーバーの起動

```bash
npm start
```

ブラウザで `http://localhost:3000` を開いてください。

## Vercel へのデプロイ

このアプリは Vercel Serverless Functions で実行可能です。

### デプロイ手順

1. **GitHub にプッシュ**
   ```bash
   git add .
   git commit -m "Deploy to Vercel"
   git push
   ```

2. **Vercel でインポート**
   - https://vercel.com にアクセス
   - 「New Project」をクリック
   - GitHub リポジトリを選択

3. **環境変数を設定**
   - Project Settings → Environment Variables
   - `OPENAI_API_KEY`: Your OpenAI API key
   - `OPENAI_MODEL`: `gpt-4o-mini` (default)

4. **デプロイ完了後、自動的に以下の URL で利用可能**
   - `https://your-project.vercel.app`

## 機能

- ✅ 事実に基づいた推薦文生成（入力情報のみを根拠）
- ✅ 4層構成（紹介 → 経験から強み → 職種での価値 → 推薦・面接依頼）
- ✅ 自然な日本語文体（参考例文ベース）
- ✅ 生成後の編集・カスタマイズ対応
- ✅ モダンな黒白科技デザイン UI

## 技術スタック

- **Frontend**: HTML5 + CSS3 + Vanilla JavaScript
- **Backend**: Node.js (ローカル) / Vercel Serverless Functions (本番)
- **AI**: OpenAI API (GPT-4o-mini)
- **Deploy**: Vercel

## 重要な注意

- API キーは絶対にコード内に埋め込まないでください
- `.env` ファイルは `.gitignore` で除外されています
- 生成ロジックは入力された情報のみを根拠とし、未入力の事実は生成しません