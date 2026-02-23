---
uid: f2e49a203
title: "CloudFlare Pages絡みでの変化"
type: feed

date: 2026-02-23
created: 2026-02-23T01:51:36.000Z
published: 2026-02-23
modified: 2026-02-23
source: https://hail2u.net/blog/changes-related-to-cloudflare-pages
domain: hail2u.net
site_name: Hail2u
feed_name: Hail2u
feed_url: https://hail2u.net/feed


guid: https://hail2u.net/blog/changes-related-to-cloudflare-pages

visibility: public
status: published
---

# CloudFlare Pages絡みでの変化



## メタ情報

- **公開日**: 2026-02-23
- **ソース**: [Hail2u](https://hail2u.net/blog/changes-related-to-cloudflare-pages)




## 本文

<p>CloudFlare Pagesの機能や仕様により、このウェブサイトの挙動が変化している。最も大きなものとしては、HTML文書のURLが拡張子無しに昇格されていることだ。クールじゃなかったURIは変わらないこともない。</p>

<p>CFPでは、拡張子を強制する、つまりリダイレクトさせないことは不可能だ。もしGitHub Pagesに戻ってもそのままいけるはずなので、あまり気にしていない。GHPでは拡張子無し<em>でも</em>アクセスできるようになっているが、リダイレクトはされないだけだ。</p>

<p>些細な変更としては各フィードがapplication/rss+xmlを返すようになっている。CFPでは_headersファイルでHTTPヘッダーを自由に追加、変更できる。<a href="https://hail2u.net/blog/internet/github-pages-and-content-type-header">読めなかったフィード・リーダー</a>で読めるようになるかもしれない。10年以上も放置していたようだ。また、上記拡張子無しURLの関係で<code>guid</code>要素の値が変わったこともあり、未読がドバっと出たかもしれない。</p>

<p>他、HTMLに書いてある<code>preload</code>や<code>preconnect</code>の<code>link</code>要素が<a href="https://developers.cloudflare.com/pages/configuration/early-hints/#2-automatic-link-header-generation">自動的にHTTPヘッダーとして追加</a>されている。</p>


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
