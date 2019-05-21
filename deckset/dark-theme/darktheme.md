# [fit] getting started with dark theme

by punchdrunker

---

# 自己紹介

- 2010年〜 iOS/Androidのアプリを書いてみる
- 2011年〜 SNS mixi(ミクシィ)
- 2016年〜 家族アルバム みてね(ミクシィ)
- DroidKaigiとかshibuya.apkを運営

---

# Dark theme

Qから新しい Dark themeになった(Pからあった)
省電力
視覚障害のある人にやさしい
暗い所で見やすくなる

---

# 開発者が取るべき対応

---

# 開発者が取るべき対応

何もしなくても特に困らない

---

# 対応した方がいいアプリ

暗いところでも使って欲しいなら対応してあげると親切

---

# ユーザーとしての使い方

- 設定アプリから有効に
- 一度有効にすると通知メニューにも出現する
- Pixelだとバッテリーセーバーを有効にした時もDark themeになる

---

# 開発者側から見た使い方

- AppThemeをDayNightを継承したものにすると楽。(かどうかはアプリによる)
  - Theme.MaterialComponents.DayNightを推奨
  - (Theme.AppCompat.DayNight もある)
- DayNightなAppThemeを設定することで、OSで設定したnight modeをアプリの中で拾えるようになる。
- night modeを拾えるようになれば、values-nightでリソース定義できるので、colors.xmlもnight mode用に定義できる。

---

# アプリの中での切り替え方

- AppCompatDelegate
- UiModeManager

まぎらわしいけど、UiModeManagerはQのnight modeとは別もの。アプリの中でのモードを切り替えることができるので、Pまでなら、これだけで似たような事が実現できる。

Qからのnight modeはICS以降が対応しおており、OSのnight modeと連携したもの。
`AppCompatDelegateのsetDefaultNightMode` でモードによるふるまいを変更できる。

---

# 色の決め方
MDGにあるとおり

プライマリで言うと
- 黒を使うとしても、真っ黒は避ける(#121212くらい)
- もともとの色を使いたい場合は、そのままではなくの彩度を下げると良い(4.5:1に下げたもの)

---

# 色の定義を整理するには

アプリの構造によって対応方針が変わるので、正解はなさそう。現状から最も良い方針を考えましょう。
ただ、確実に言えるのは以下
色名にblackとかwhiteとか使うのはやめた方がよさそう(transparentならいいかも)
機能や部品の名前にしましょう
色数は少いに越したことはないので、意味もなく1箇所でしか使わない色とかは消した方が良さそう。

---

# Demo 

---
# Reference

基本仕様
https://developer.android.com/preview/features/darktheme

Androidでのデフォルト実装について
https://material.io/develop/android/theming/dark/

関連API
https://developer.android.com/reference/androidx/appcompat/app/AppCompatDelegate.html#MODE_NIGHT_FOLLOW_SYSTEM

具体的な対応方針はMDGから
https://material.io/design/color/dark-theme.html#usage
