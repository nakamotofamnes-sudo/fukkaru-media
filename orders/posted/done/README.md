# orders/posted — 出した投稿の記録

チャット（Cowork）が投稿したら、**このフォルダにJSONを1つ置いてください。**
Mac の `handoffpull.py`（5分おき）が拾って `~/fukkaru/post/チャット記録/` に移し、
`postlog.py` が管制画面の「📮 出した投稿」に並べます。

拾ったファイルは、こちら側で `orders/posted/done/` へ移されます。

## 形

ファイル名は `<日付>-<媒体>.json`（例 `20260902-gbp.json`）。

```json
{
  "media": "gbp",
  "postedAt": "2026-09-02 20:00:00",
  "text": "投稿した本文",
  "postId": "accounts/.../localPosts/..."
}
```

| 項目 | 中身 |
|---|---|
| `media` | `gbp` / `x` / `threads` / `instagram` のどれか |
| `postedAt` | `YYYY-MM-DD HH:MM:SS`（日本時間） |
| `text` | 実際に出した本文 |
| `postId` | 媒体が返したID。無ければ空文字 |

**形が違うものは黙って捨てられます。**

## 気をつけること

- **このリポジトリは公開です。** お客様の氏名・電話番号・番地は**絶対に書かないでください。**
  地域を書くなら市区町村までです。
- ここに何を書いても**投稿は起きません。**記録だけの場所です。
  投稿の口は Mac の `~/fukkaru/post/queue` だけです。
- 書き込みには、このリポジトリへの **push 権限**が要ります。
  権限が無いと `is not in this session's authorized repository set` で 403 になります。
