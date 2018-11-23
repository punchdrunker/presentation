# [fit]Transition indicator

### by punchdrunker

---

# 自己紹介

- 高校卒業+1年まで札幌在住
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
- Transition ﾁｮｯﾄﾃﾞｷﾙ ← 今ココ

---

# 用語の説明

- Transition framework(遷移)
  - 単に画面遷移するだけの機能もあるが、加えてレイアウトにアニメーション効果を付けることもできるフレームワークの総称
- Transition
  - Transition Managerによって管理される、"遷移"そのもの
- SharedElement(View)
  - 遷移元と遷移先で繋ぎ合わせたいView。optionとしてstartActivityに渡す。
- Transition name(String)
  - 遷移元と遷移先のViewに同じtransitionNameを付ける事でSharedElementとして認識される

---

# お手本にしたもの

twitter公式クライアント

---

# Activity to Activity

---

# Activity to Fragment

---

# Activity to ViewPager

---

# Overlap

---

# RecyclerView

---

# FIN
