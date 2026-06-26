# portal

lvncerpedia のカテゴリ索引と `CATEGORY.md` 自動生成。

## 構成

| ファイル | 役割 |
| --- | --- |
| `repos.yaml` | カテゴリ定義（人が編集） |
| `CATEGORY.md` | 索引（自動生成） |
| `.scripts/generate_profile_readme.py` | 生成スクリプト |

## ローカル

```bash
cd portal/.scripts
uv sync
uv run generate_profile_readme.py
uv run generate_profile_readme.py --check
```

## CI

`.github/workflows/update-profile-readme.yml`

- `repos.yaml` 変更 or 定期実行で `CATEGORY.md` を再生成
- `wiki` に新トピックがあれば `未分類` へ追加して PR 作成

GitHub リポジトリ `portal` の Settings → Secrets に **`REPO_WRITE_TOKEN`** が必要。

## モノレポ前提

- 知識本体: [`wiki`](https://github.com/lvncerpedia/wiki)
- トピックリンク: `https://github.com/lvncerpedia/{topic}`
