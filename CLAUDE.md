# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Environment

### Package Management

このセクションには、プロジェクトで使用するパッケージマネージャーとビルドシステムを記載してください。

例:
```bash
# 依存関係のインストール
<package-manager> install

# 開発用依存関係のインストール
<package-manager> install --dev

# 特定のグループをインストール
<package-manager> install --group <group-name>
```

### Running Tests

このセクションには、テストの実行方法を記載してください。

例:
```bash
# すべてのテストを実行
<test-command>

# 特定のテストファイルを実行
<test-command> tests/path/to/test_file.py

# 詳細出力付きで実行
<test-command> -v
```

### Code Quality

このセクションには、コード品質ツールの使用方法を記載してください。

例:
```bash
# Linterの実行
<linter> check .

# フォーマッターの実行
<formatter> format .

# 型チェックの実行
<type-checker> .

# コミット前の完全チェック（推奨）
<linter> check . && <formatter> format . && <type-checker> .
```

設定は `pyproject.toml` または各ツールの設定ファイルに記載してください。

### Type Safety

このセクションには、型安全性に関する要件を記載してください。

推奨事項:
- すべての関数、メソッド、変数に型アノテーションを付与
- 静的型チェックをコミット前に実行
- `Any`型の使用を避け、具体的な型を使用
- 型エラーは無視せず、必ず解決

## Key Development Guidelines

### Code Style

このセクションには、プロジェクトのコーディング規約を記載してください。

推奨事項:
- **命名規則**: クラスはPascalCase、関数/変数はsnake_case、定数はUPPER_SNAKE_CASE
- **型ヒント**: 型アノテーションを積極的に使用
- **Docstrings**: 標準的なフォーマット（例: Google-style）を使用
- **行の長さ**: プロジェクトで統一された最大文字数を設定
- **インポート**: ツールによる自動ソート（stdlib → サードパーティ → ローカル）

### Documentation Standards

このセクションには、ドキュメンテーション標準を記載してください。

推奨事項:
- 公開関数、クラス、モジュールには包括的なdocstringを記載
- 標準的なフォーマット（例: Google-style）を採用
- Docstringは型アノテーションと一致させる
- 複雑な関数には使用例を含める

### Testing Strategy

このセクションには、テスト戦略を記載してください。

推奨事項:
- **単体テスト**: 高速、外部依存なし（モックを使用）
- **統合テスト**: 中速、外部サービスをモック
- **E2Eテスト**: 実際の外部サービスを使用、適切にマーク
- **テストマーカー**: テストの種類や依存関係を示すマーカーを使用

## Documentation

ドキュメンテーションシステムを使用する場合、このセクションに設定を記載してください。

詳細なガイドラインは `@.claude/docs.md` を参照。

### File Locations

例:
- すべてのドキュメント: `docs/*.md`
- ドキュメント設定: `docs/conf.py`（Sphinxの場合）
- ビルドシステム: `docs/Makefile`（Sphinxの場合）

## Technology Stack Summary

このセクションには、プロジェクトで使用する主要な技術を記載してください。

例:
- **ランタイム**: Python X.X.X
- **パッケージマネージャー**: <package-manager>
- **テスト**: <test-framework> >= X.X.X
- **Linting**: <linter> >= X.X.X
- **型チェック**: <type-checker> >= X.X.X
- **ドキュメント**: <doc-generator> >= X.X.X（オプション）
