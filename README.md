# 🍇 シャインマスカットゲーム

スイカゲーム風の合体パズル。もやしから始めて、8段階の「高級化」を経てシャインマスカットを目指します。
HTML 1ファイル完結・外部ライブラリなし・オフライン動作。

**遊ぶ → https://rivtm33.github.io/yasai-game/**

## 進化ルート（安い → 高級）

| 段階 | 野菜 | 値段 |
|---|---|---|
| 1 | もやし | ¥30 |
| 2 | きゅうり | ¥70 |
| 3 | なす | ¥120 |
| 4 | トマト | ¥200 |
| 5 | ブロッコリー | ¥350 |
| 6 | パプリカ | ¥600 |
| 7 | まつたけ | ¥3,000 |
| 8 | シャインマスカット | ¥8,000 |

シャインマスカット同士がくっつくと、消滅して **¥20,000** の特大ボーナス。

## 操作

- **クリック / タップ** … その位置に投下
- **◀ ▶（盤面の左右）** … カゴを横からゆさぶる「ずる」ボタン
- **🔀 シャッフル** … 盤面をグラグラ揺らして中身の種類を入れ替える（回数無制限・0.7秒のクールダウン）
- **⏩ オート** … 高速自動プレイ（投下間隔190ms・重力2倍）
- **🔔 / 🎵** … 効果音・BGM の切り替え

## レベル

| | 落とせる種類 | 野菜の大きさ | デッドライン | 猶予 |
|---|---|---|---|---|
| かんたん | 4種 | ×0.80 | 浅い(98) | 2.2秒 |
| ふつう | 3種 | ×1.00 | 標準(122) | 1.2秒 |
| むずかしい | 3種 | ×1.15 | 深い(150) | 0.7秒 |

## 技術メモ

- 物理は自作の Position Based Dynamics（重力 → 積分 → 拘束解決7回 × 2サブステップ → 位置から速度を復元）
- 音はすべて Web Audio API でその場合成。効果音・ファンファーレ・4小節ループのBGMに音声ファイルは一切なし
- 野菜の画像は 256px の正方形JPEGとして base64 で HTML に直接埋め込み、Canvas 側で円形にクリップ

## 画像クレジット

野菜の写真は Openverse 経由で取得した、再利用が許可されている画像です。

| 野菜 | タイトル / 作者 | ライセンス | 出典 |
|---|---|---|---|
| もやし | bean sprouts! / Stacy Spensley | CC BY | https://www.flickr.com/photos/21001756@N06/3683922689 |
| きゅうり | cucumber / viZZZual.com | CC BY | https://www.flickr.com/photos/22394551@N03/2738586453 |
| なす | Chinese eggplant / hoegsberg | CC BY | https://www.flickr.com/photos/2175/2038623321 |
| トマト | Red & Yellow Tomatoes / Scott 97006 | CC BY | https://www.flickr.com/photos/29487672@N07/14566173188 |
| ブロッコリー | broccoli / wanko | CC BY | https://www.flickr.com/photos/51043590@N00/466686 |
| パプリカ | Red peppers / 16:9clue | CC BY | https://www.flickr.com/photos/53255320@N07/6796213909 |
| まつたけ | Matsutake mushroom (Japan) | CC0 | https://www.rawpixel.com/image/5915306/image-public-domain-leaves-green |
| シャインマスカット | Green Grapes / Alabama Extension | CC0 | https://www.flickr.com/photos/184594136@N08/50088087491 |

各画像は正方形に切り出し・256pxへ縮小したうえで利用しています（トリミング以外の改変なし）。
