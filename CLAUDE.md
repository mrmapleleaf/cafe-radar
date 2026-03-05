# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev        # 開発サーバー起動 (http://localhost:3000)
npm run build      # プロダクションビルド
npm run generate   # 静的サイト生成
npm run preview    # ビルド成果物のプレビュー
```

## Architecture

**Nuxt 4 + Vue 3 + Tailwind CSS v4** のSPA。カフェ検索アプリ「ココイケ」。

- Tailwind は `@tailwindcss/vite` プラグイン経由で統合（`tailwind.config.js` は不要）
- `app/assets/css/main.css` に `@import "tailwindcss"` のみ記載
- `<style lang="scss" scoped>` を使用しているが、SCSSパッケージは未インストール（現状は空のスタイルブロックのみ）

### データフロー（現状）

```
index.vue
  └── ScreenA.vue        # 検索条件UI（位置・範囲選択）
        └── CafeModal.vue  # 検索結果モーダル（未実装・プレースホルダー）
```

`ScreenA.vue` が状態（`isInputVisible`, `selectedRange`, `isModalOpen`）を管理し、`CafeModal` へ `isOpen` プロップを渡す。カフェAPIの連携・実際の検索ロジックは未実装。