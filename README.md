# Todo.txt & Tokaido チートシート

## bashrcの設定
以下の設定を`~/.bashrc`に追加した．

```bash
# Todo.txt aliases and functions
alias t='todo.sh -d ~/.todo.cfg'

# Basic commands
alias ta='t add'
alias tl='t ls'
alias td='t do'
alias tdel='t del'
alias tp='t listproj'
alias tc='t listcon'

# Project specific
alias tw='t ls +work'
alias tr='t ls +research'
alias tdev='t ls +development'
alias tdoc='t ls +documentation'

# Due date filters
alias tdue='t ls due:'
alias ttoday='t ls due:$(date +%Y-%m-%d)'
alias tweek='t ls due:$(date -d "+7 days" +%Y-%m-%d)'

# Complex functions
function tadd() {
   local task="$1"
   local due_date="$2"
   local project="${3:-work}"
   t add "$task +$project due:$(date -d "$due_date" +%Y-%m-%d)"
}

function tpri() {
   local task_num="$1"
   local priority="${2:-A}"
   t pri "$task_num" "$priority"
}

# Archive completed tasks
alias tarchive='t archive'

# Show task statistics
alias tstats='t stats'
```

## 基本コマンド
| コマンド | 説明 |
|----------|------|
| `ta "タスク内容 +プロジェクト名 due:YYYY-MM-DD"` | タスク追加 |
| `tl` | 全タスク表示 |
| `td 番号` | タスク完了マーク |
| `tdel 番号` | タスク削除 |
| `tp` | プロジェクト一覧表示 |
| `tc` | コンテキスト一覧表示 |

## プロジェクト管理
| コマンド | 説明 |
|----------|------|
| `tw` | workプロジェクトのタスク表示 |
| `tr` | researchプロジェクトのタスク表示 |
| `tdev` | developmentプロジェクトのタスク表示 |
| `tdoc` | documentationプロジェクトのタスク表示 |

## 期限管理
| コマンド | 説明 |
|----------|------|
| `tdue 2024-01` | 2024年1月期限のタスク表示 |
| `ttoday` | 今日が期限のタスク表示 |
| `tweek` | 一週間以内が期限のタスク表示 |

## 優先度管理
| コマンド | 説明 |
|----------|------|
| `tpri 1 A` | タスク1を優先度Aに設定 |
| `tpri 2 B` | タスク2を優先度Bに設定 |
| `t lsp A` | 優先度Aのタスク表示 |
| `t lsp B` | 優先度Bのタスク表示 |

## 高度な使用例

### タスク追加の例
| コマンド | 説明 |
|----------|------|
| `tadd "クライアントミーティング" "tomorrow" work` | 明日が期限のworkタスク追加 |
| `tadd "論文レビュー" "next friday" research` | 次の金曜が期限のresearchタスク追加 |
| `tadd "コードレビュー" "2024-01-20" development` | 指定日が期限のdevelopmentタスク追加 |

### フィルタリング
| コマンド | 説明 |
|----------|------|
| `t ls @office` | オフィスでのタスク |
| `t ls +work @phone` | 仕事関連の電話タスク |
| `t ls +project1 due:2024-01` | プロジェクト1の1月期限タスク |

## タスク管理
| コマンド | 説明 |
|----------|------|
| `t append 1 "追加情報"` | タスク1に情報追加 |
| `t prepend 1 "前置情報"` | タスク1の先頭に情報追加 |
| `t replace 1 "新しいタスク内容"` | タスク1を置換 |

## メンテナンス
| コマンド | 説明 |
|----------|------|
| `tarchive` | 完了タスクをアーカイブ |
| `tstats` | タスク統計の表示 |

## Tokaidoの操作（ブラウザ）
URL: http://localhost:33333

| キー | 動作 |
|------|------|
| `h` | 左のリストに移動 |
| `j` | 次のタスクに移動 |
| `k` | 前のタスクに移動 |
| `l` | 右のリストに移動 |
| `Enter` | タスク詳細を開く |
