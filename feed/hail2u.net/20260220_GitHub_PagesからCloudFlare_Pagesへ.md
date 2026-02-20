---
uid: 281df9134
title: "GitHub PagesからCloudFlare Pagesへ"
type: feed

date: 2026-02-20
created: 2026-02-20T02:09:00.000Z
published: 2026-02-20
modified: 2026-02-20
source: https://hail2u.net/blog/hello-cloudflare-pages
domain: hail2u.net
site_name: Hail2u
feed_name: Hail2u
feed_url: https://hail2u.net/feed


guid: https://hail2u.net/blog/hello-cloudflare-pages

visibility: public
status: published
---

# GitHub PagesからCloudFlare Pagesへ



## メタ情報

- **公開日**: 2026-02-20
- **ソース**: [Hail2u](https://hail2u.net/blog/hello-cloudflare-pages)




## 本文

<p>ちょっとした事情でウェブサイトを<a href="https://pages.cloudflare.com/">CloudFlare Pages</a>に移動させる。1か月くらい前の話だ。最終的にはGitHub側やCloudFlare側でビルドせず、Gitリポジトリー監視もしていない。ローカルのファイル群をFTPでミラー的な更新方式になっていて、ちょっと楽しい。APEXドメインのためネームサーバーも移行せざるを得ず、不安が残る。色々変わり、なんらかの不具合がありそうだ。</p>

<p>移行は、Gitリポジトリー監視(Git Integration)で始め、最終的には<a href="https://developers.cloudflare.com/workers/wrangler/">Wrangler</a>を使って直接アップロード(Direct Upload)する。最初から直接アップロードでPagesを作ると、後ほどGitリポジトリー監視に変更できないので、こうせざるを得ない。また、Pagesの作成は右上の「+ Add」からしかできない。そこかしこのドキュメントに書いてあるようにWorkers &amp; PagesのCreate ApplicationからはPagesは作れなさそうだった。導線が無い気がする。</p>

<ol>
  <li>(CloudFlare) PagesをGitHubのgh-pagesブランチを監視するように作成する
    <ul>
      <li>Build commandは<code>exit 0</code></li>
      <li>Preview branchを無効に</li>
    </ul>
  </li>
  <li>数日は何もせず、更新だけ行う</li>
  <li>(ローカル) gh-pagesブランチをcf-pagesブランチへ名前を変更する</li>
  <li>(ローカル) pushするブランチをcf-pagesにするようnpmスクリプトを更新する</li>
  <li>(ローカル) cf-pagesブランチをGitHubへ送る
    <ul>
      <li>ビルドされないことを確認</li>
    </ul>
  </li>
  <li>(CloudFlare) cf-pagesブランチを監視するように設定する</li>
  <li>数日は何もせず、更新だけ行う</li>
  <li>(ローカル) npxを使い<a href="https://developers.cloudflare.com/workers/wrangler/commands/#login">Wranglerを認証</a>する
    <ul>
      <li>自動的に開いたページで認証を進めると、うまく戻ってこれないことがある</li>
    </ul>
  </li>
  <li>(ローカル) Gitのpushコマンドの代わりに<a href="https://developers.cloudflare.com/pages/get-started/direct-upload/#deploy-your-assets">npx経由でWrangler</a>を使うようnpmスクリプトを更新する</li>
  <li>(CloudFlare) Automatic deploymentを無効にする
    <ul>
      <li>ついでにProduction branchをmainに変更</li>
    </ul>
  </li>
  <li>(GitHub) cf-pagesブランチを削除する</li>
  <li>数日は何もせず、更新だけ行う</li>
  <li>(GitHub) 設定→Pages→Build and deployment→BranchをNoneにしてGitHub Pagesを停止する</li>
  <li>(GitHub) gh-pagesブランチを削除する</li>
  <li>(ローカル) gh-pagesブランチなどのために作られている.gitディレクトリーを削除する</li>
</ol>

<p>かなり遠回りだ。Gitリポジトリー監視がうまくいった辺りでドメインの移行を済ませている。これでローカルでビルドしたファイルを直接アップロードできる。Wranglerは更新したファイルだけアップロードしてくれるので、FTPでミラー的な使い方と言える。GitHubでもCloudFlareでもジョブが走らず、世界に優しいような気分になれる。</p>

<hr>

<p>Wranglerのpages deployコマンドに<kbd>--dry-run</kbd>オプションが欲しい、起動コストがなかなかあるなという感想だ。プロジェクト名や出力ディレクトリーは設定ファイルを書いた方が良さそうだ。<a href="https://developers.cloudflare.com/pages/functions/wrangler-configuration/#inheritable-keys"><code>pages_build_output_dir</code>というPages専用の設定</a>がある。Wranglerに更新があるとnpxコマンドが止まるので、Direct Uploadするだけだし、バージョン番号を固定しても良いかもしれない。</p>


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
