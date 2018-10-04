
# [fit]今時のProgress indicator

### by punchdrunker

---

# 自己紹介

- 高校卒業まで札幌在住
- 2010年〜 iOS/Androidのアプリを書いてみる
- 2011年〜 ミクシィ
- 家族アルバム みてね
- DroidKaigiとかshibuya.apk運営

---

# 課題

![right](progress.png)

- アプリのUIが古いまま
- ProgressDialogは非推奨に
- とりあえず置換したDialogFragmentはIllegalStateException
- そもそもMaterial Designに準拠するべき

---

# ProgressDialogの功罪

- Toastライクに気軽に表示できる
  - コピペされがち
- 表示中に画面の操作を禁止できる
  - ユーザにとっては不自由に感じる

---

# MDC的クルクル (Progress indecators)

## 用途

待ち時間/処理時間の表現をするためのもの

## 種類

Linear と Circular の2つ

[material.ioより](https://material.io/design/components/progress-indicators.html)

---

![fit](indicator.png)

---

# 三原則

- Informative: ただの装飾ではなく意味のある表示
- Animated: 注意を引く必要がある
- Consistent: 一貫性

---

# 配置

処理や通信が完了した時に表示される部分に埋め込まれているべき。

リストが表示される予定の場所に埋め込んだり、選択したitemに沿って表示するなど。

---

![fit](progress1.mp4)

---

![fit](progress2.mp4)

---

# [fit]完全に理解した

---

# [fit]じゃあ、更新系は?

---

# 事例

有名そうなアプリのUIを確認してみる

- twitter
- facebook
- gmail

---

# 事例

投稿系はそもそも処理中表示せずに、完了したフリをしてエラーになったら知らせるやり方が主流

---

# [fit]長い処理の表現

---

![fit](progress3.mp4)

---
# FIN
