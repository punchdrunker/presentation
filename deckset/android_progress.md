
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

# [fit]更新系は?

---

# 有名なアプリの事例

- twitter
- facebook
- gmail

---

# 有名なアプリの事例

投稿、編集、削除はそもそも処理中表示せずに、完了したフリをしてエラーになったら知らせるやり方が主流ぽい

---

# [fit]時間のかかる処理の表現

---

![fit](progress3.mp4)

---

こんなUI標準で用意されてない...

---
# 作ろう

Buttonを継承して、Viewを自前でゴニョゴニョすれば出来そう。

面倒なので今回はConstrainLayoutを継承して、ClickableなCustomViewを作った。
Layoutの実装であればxmlでレイアウトを定義できて簡単に見た目をいじることが出来る。

---

# レイアウト(大体)

TextViewとProgressBarのvisibilityを切り替えればよさそう

``` xml
<androidx.constraintlayout.widget.ConstraintLayout ...>

    <TextView android:text="Tap!" ... />
    <ProgressBar android:visibility="gone" ... />

</androidx.constraintlayout.widget.ConstraintLayout>
```

---
# 実装

コンストラクタで inflateして、OnClickListenerとタッチイベントを自前でハンドリング

---
# 実装

``` kotlin
class CustomButton(context: Context, attrs: AttributeSet?) : ConstraintLayout(context, attrs) {
    var cListener: OnClickListener? = null
    constructor() { ... // inflate}
    override fun setOnClickListener(listener: OnClickListener?) {
        cListener = listener
    }
    override fun dispatchTouchEvent(ev: MotionEvent): Boolean {
        ... // ACTION_UPでonClickをinvoke
    }

    // Activityから呼ぶ
    fun toggle() { ... // visibility更新 }
}
```

---
# Activity側

``` kotlin
binding.customButton.setOnClickListener {
    button -> (button as CustomButton).toggle()
}
```
---

# FIN
