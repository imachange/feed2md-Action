---
uid: 50975b0a6
title: "StandbyBudgetPercentでスリープを維持"
type: feed

date: 2026-10-15
created: 2026-10-15T23:22:34.000Z
published: 2026-10-15
modified: 2026-10-15
source: https://hail2u.net/blog/keep-sleeping-with-standbybudgetpercent
domain: hail2u.net
site_name: Hail2u
feed_name: Hail2u
feed_url: https://hail2u.net/feed


guid: https://hail2u.net/blog/keep-sleeping-with-standbybudgetpercent

visibility: public
status: published
---

# StandbyBudgetPercentでスリープを維持



## メタ情報

- **公開日**: 2026-10-15
- **ソース**: [Hail2u](https://hail2u.net/blog/keep-sleeping-with-standbybudgetpercent)




## 本文

<p>現PCでも夜にスリープさせると、朝には休止状態になっている。前PCでもいつのまにかこうなっていたが、バッテリーの劣化と不調だろうと思い込んでいた。新品でも起こるとなると調べるしかない。数年位前から<a href="https://learn.microsoft.com/ja-jp/windows-hardware/customize/power-settings/adaptive-hibernate">Adaptive Hibernate (状況に応じた休止状態)</a>というもので制御するらしい。その中の<a href="https://learn.microsoft.com/ja-jp/windows-hardware/customize/power-settings/standbybudgetpercent">StandbyBudgetPercent</a>で指定されたパーセンテージ分、バッテリーが減ったら休止状態に移行するようだ。</p>

<p>電源設定などでは隠されており、powercfgアプリでも隠し設定になっている。/QHオプションで表示されたら設定可能だろう。<a href="https://learn.microsoft.com/ja-jp/windows-hardware/design/device-experiences/modern-standby-sleepstudy">SleepStudy</a>の報告を読むと、既定の5%で8時間くらいは維持できそうだ。余裕をもって倍の10%にしたところ、スリープを維持できている。</p>

<hr>

<p>前PCではうまくいかない。環境を移行し終わったあたりでWindowsを再インストール(「システム→回復→Windows Updateで問題を解決する」で行う方)すると、嘘みたいに維持できるようになった。これでKindle及びPrimie Video専用端末として使いやすくなった。</p>


---

*この記事は [Hail2u](https://hail2u.net/feed) から自動取得されました。*

<!-- 
利用可能なプレースホルダー:
基本情報: uid, title, description, type, category
日付: date, created, updated, published, modified
ソース: source, domain, site_name, feed_name, feed_url, feed_category
コンテンツ: excerpt, content, content_snippet, language, image_url
著者・その他: author, authors, guid, comments
タグ・カテゴリ: tags_array, categories, categories_array
その他: slug, notes, visibility, status

条件分岐: 
-->
