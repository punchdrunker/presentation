# [fit] Practical Transition

### by punchdrunker

---

# 自己紹介

- 2010年〜 iOS/Androidのアプリを書いてみる
- 2011年〜 mixi(ミクシィ)
- 2016年〜 家族アルバム みてね(ミクシィ)
- DroidKaigiとかshibuya.apkを運営

---

# 経緯

写真一覧画面から写真の詳細画面に遷移した時に...

- Fling to finish(上下スワイプで閉じる)を実装したい
- どうせなら粋なアニメーション演出も出来ると嬉しい
- ドキュメント通りに書いてるのに動かん!!!!1
  - 書いた通りに動いてました(反省)
- 完全に理解した!!
- 挫折
- Transition ﾁｮｯﾄﾃﾞｷﾙ
- Transition 見送り

---

# 用語の説明

- Transition framework(遷移)
  - 画面遷移でレイアウトにアニメーション効果を付けることもできるフレームワークの総称
- Transition
  - Transition Managerによって管理される、"遷移"そのもの

---

# 用語の説明
- SharedElement(View)
  - 遷移元と遷移先で繋ぎ合わせたいView。optionとしてstartActivityに渡す。
- Transition name(String)
  - 遷移元と遷移先のViewに同じtransitionNameを付ける事でSharedElementとして認識される

---

# お手本にしたもの

- android-transition-examples
  - https://github.com/google/android-transition-examples
- twitter公式クライアント

---

# Fragment to Fragment

1つのActivity内での遷移はgoogle exampleそのまま

---

# Activity to Activity

---

# Fragment to Fragment

---

# Fragment to ViewPager

---

# Overlap

---

# RecyclerView

---

# FIN
