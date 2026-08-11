# 未使用画像の退避先

どの HTML からも参照されていない画像をここに退避しています。**削除はしていません。**

現行のページが使っている画像は `images/` 直下と `images/flow/` `images/usage/` にあります。ここにあるファイルは参照ゼロなので、ページの表示には影響しません。

## 退避した理由

差し替えや作り直しの過程で残ったファイルが混在し、「どれが現行版か」が分かりにくくなっていたため、参照されているものだけを `images/` に残しました。

## 内訳（32 枚）

| ファイル群 | 枚数 | 備考 |
|---|---|---|
| `flow/flow_stepN.png` | 7 | 旧世代。現行は `images/flow/flow-stepN-*.png`（`flow-step1-select-flow.png` など） |
| `usage/step0X_*.png` | 10 | 同じ工程の別ショット。現行は `step03_select_create_space` `step04_name_space` `step05_add_knowledge` `step05_upload_done` `step06_1〜4` `step07_agent_ready` |
| `screenshot_2XX.png` | 8 | 連番のまま残っていた素材。用途不明 |
| `agent-stepN-*.png` | 5 | エージェントページで使わなくなったショット |
| `quick-chat.png` `quick-data.png` | 2 | 用途不明 |

## 復帰させたいとき

`images/_archive/` から元の階層（`images/` または `images/flow/` `images/usage/`）へ戻し、HTML の `<img>` タグから参照してください。

その際、**`width` / `height` 属性を実寸で付けてください。** 寸法がないと遅延読み込み時にレイアウトがずれて、アンカーの飛び先がずれます。実寸は次のコマンドで確認できます。

```bash
python3 -c "import struct,sys; h=open(sys.argv[1],'rb').read(24); print(struct.unpack('>II', h[16:24]))" 画像パス
```

## 残っている撮影タスク

`quick-usage.html` のガイド B ステップ B-4「Space を参照しているか確認する」だけスクリーンショットがありません。実機で確認後、`images/flow/` に追加して該当箇所の TODO コメントと差し替えてください。
