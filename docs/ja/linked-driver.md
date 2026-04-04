# Linked Driver

Linked Driver は、1つのスライダーで **複数のターゲット** を同時に制御する機能。

スライダーに最初に設定されるドライバー（Primary Driver）に加えて、同じスライダーの動きに連動する追加のドライバーを作成できる。1つのスライダーで `hide_viewport` と `hide_render` を同時に切り替えたり、複数のノードパラメータを1つのスライダーでまとめて制御したい場合に便利。

<div style="display: flex; gap: 1em; flex-wrap: wrap;">
  <img src="../../images/linked_driver_left.png" alt="Linked Driver パネル" style="max-height: 400px;">
  <img src="../../images/linked_driver_right.png" alt="Linked Driver ダイアログ" style="max-height: 400px;">
</div>

## ターゲットタイプ

Primary Driver と同様に、3種類のターゲットタイプを選択できる。

| ターゲットタイプ | 説明 |
|----------------|------|
| **Shape Key** | メッシュ・カーブ・サーフェスオブジェクトのシェイプキー |
| **Custom Property** | ボーンのカスタムプロパティ |
| **Data Path** | 任意のプロパティをデータパスで指定 |

## Range（出力範囲）

各 Linked Driver には、Primary Driver とは独立した **Range Min / Max** を設定できる。

スライダーの位置が Primary Driver の範囲にマッピングされるのと同じ比率で、Linked Driver の範囲にも変換される。

!!! example "例"
    Primary の Range が 0〜1、Linked の Range が 10〜20 の場合、スライダーが 50% の位置にあるとき → Primary = 0.5、Linked = 15

### Default Output

スライダーがデフォルト位置（レスト位置）にあるときの Linked Driver の出力値。Primary Driver のデフォルト値と Linked の Range から自動的に計算されるため、編集不可（読み取り専用）。

## 追加・管理の操作

N パネルのスライダーリストで対象スライダーを選択し、🔗 ボタンをクリックすると **Manage Linked Drivers** ダイアログが開く。追加・編集・削除はすべてこのダイアログ内で行う。

- 上部のリストで既存の Linked Driver を確認・選択
- **＋ ボタン**: 新しい Linked Driver を追加
- **－ ボタン**: 選択中の Linked Driver を削除
- リストの項目を選択すると、下部にターゲット設定と Range が表示され、その場で編集可能
- **OK** を押すと、追加・編集・削除が一括で確定される

## 既存ドライバーの上書き（Force Overwrite）

ターゲットに既にドライバーが設定されている場合、警告が表示される。

「**Overwrite existing driver**」チェックボックスを ON にすると、既存のドライバーを削除して Linked Driver に置き換える。

!!! warning "注意"
    上書きすると既存のドライバーは完全に削除される。意図しないドライバーの消失に注意。

## 注意事項

- Linked Driver は **スライダー専用**。ジョイスティックには対応していない
- Primary Driver の Range やデフォルト値を変更すると、Linked Driver の式も自動的に再計算される
- Linked Driver を持つスライダーを削除すると、Linked Driver も一緒に削除される
