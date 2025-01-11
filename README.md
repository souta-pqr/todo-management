# Todo.txt コマンドチートシート

## 基本コマンド
ta "タスク内容 +プロジェクト名 due:YYYY-MM-DD"  # タスク追加
tl                                              # 全タスク表示
td 番号                                         # タスク完了マーク
tdel 番号                                       # タスク削除
tp                                             # プロジェクト一覧表示
tc                                             # コンテキスト一覧表示

## プロジェクト管理
tw                                             # workプロジェクトのタスク表示
tr                                             # researchプロジェクトのタスク表示
tdev                                           # developmentプロジェクトのタスク表示
tdoc                                           # documentationプロジェクトのタスク表示

## 期限管理
tdue 2024-01                                   # 2024年1月期限のタスク表示
ttoday                                         # 今日が期限のタスク表示
tweek                                          # 一週間以内が期限のタスク表示

## 優先度管理
tpri 1 A                                       # タスク1を優先度Aに設定
tpri 2 B                                       # タスク2を優先度Bに設定
t lsp A                                        # 優先度Aのタスク表示
t lsp B                                        # 優先度Bのタスク表示

## 高度な使用例
# タスク追加の例
tadd "クライアントミーティング" "tomorrow" work
tadd "論文レビュー" "next friday" research
tadd "コードレビュー" "2024-01-20" development

# フィルタリング
t ls @office                                   # オフィスでのタスク
t ls +work @phone                              # 仕事関連の電話タスク
t ls +project1 due:2024-01                     # プロジェクト1の1月期限タスク

## タスク管理
t append 1 "追加情報"                           # タスク1に情報追加
t prepend 1 "前置情報"                         # タスク1の先頭に情報追加
t replace 1 "新しいタスク内容"                  # タスク1を置換

## メンテナンス
tarchive                                       # 完了タスクをアーカイブ
tstats                                         # タスク統計の表示

## tokaidoの操作（ブラウザ）
# URL: http://localhost:33333
h                                             # 左のリストに移動
j                                             # 次のタスクに移動
k                                             # 前のタスクに移動
l                                             # 右のリストに移動
Enter                                         # タスク詳細を開く