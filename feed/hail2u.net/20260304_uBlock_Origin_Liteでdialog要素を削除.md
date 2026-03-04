---
uid: 61f6a12c3
title: "uBlock Origin Liteでdialog要素を削除"
type: feed

date: 2026-03-04
created: 2026-03-04T03:00:58.000Z
published: 2026-03-04
modified: 2026-03-04
source: https://hail2u.net/blog/removing-a-dialog-element-with-ublock-origin-lite
domain: hail2u.net
site_name: Hail2u
feed_name: Hail2u
feed_url: https://hail2u.net/feed


guid: https://hail2u.net/blog/removing-a-dialog-element-with-ublock-origin-lite

visibility: public
status: published
---

# uBlock Origin Liteでdialog要素を削除



## メタ情報

- **公開日**: 2026-03-04
- **ソース**: [Hail2u](https://hail2u.net/blog/removing-a-dialog-element-with-ublock-origin-lite)




## 本文

<p>とあるウェブサイトでログインを要求する<code>dialog</code>要素が全画面に被さって出る。普段はログインする必要が無いので、ログインしておらず、毎回のように閉じる操作を要求される。あろうことか<kbd>Esc</kbd>キーで閉じることもできない。普通に<a href="https://github.com/uBlockOrigin/uBOL-home">uBlock Origin Lite</a>で消そうとすると、ウェブページが操作不能になる。見えないだけでダイアログ用のレイヤーが被さったままになってしまうからだ。</p>

<pre><code class="language-easylist">example.com##dialog:remove()</code></pre>

<p>このように明示的に<code>dialog</code>要素を削除する必要がある。そのための<a href="https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#subjectremove"><code>remove()</code>というアクション・オペレーター</a>が用意されているようだ。残念ながら閉じる関数はない。また、たまに削除を失敗する。</p>


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
