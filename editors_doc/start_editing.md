#cpprefjpを編集するには

本cpprefjpサイトは、Google Sitesサービス上に構築されていますが、編集自体はGitHubリポジトリにあるMarkDown形式のプレーンテキストで行います。

cpprefjpサイトのGitHubリポジトリは、以下になります：
* [https://github.com/cpprefjp/site](https://github.com/cpprefjp/site)


また、cpprefjpサイト上に掲載する画像ファイルのようなリソースも、GitHubリポジトリで管理しています。
* [画像ファイルリポジトリ](https://github.com/cpprefjp/image)


##GitHubからcpprefjpサイトへの自動反映
GitHub上で記述したMarkDown(.md)形式のリファレンスは、自動的にhtmlに変換されて、cpprefjpサイトに反映されます。

###反映間隔
反映間隔は、1日1回となります。何らかの理由で、すぐに反映させたい場合は、cpprefjp/siteリポジトリに、Issue報告としてご連絡ください。


###変換エラーの検出
MarkDown形式からhtmlへの変換で、何らかのエラーが発生した場合、cpprefjp/siteリポジトリのIssueとして登録されます。Issueは、コミッタ全員に通知されますので、関連する編集者の方は対応お願いします。

問題を修正した場合、自動反映ツールが自動的にチケットをクローズしますので、編集者の方は自分でチケットをクローズしないようお願いします。

###自動反映ツール
自動反映ツールも、GitHub上で開発が進められています。

* [andare - github にある Markdown 形式のファイルを取得して html に変換して返すサーバ](https://github.com/cpprefjp/andare)

機能要望やpull request等がありましたら、こちらにお願いします。

このツールは、コアメンバの一人である[melpon](https://github.com/melpon)さんが保持しているサーバー上で動作しています。


##編集権限を得るには
以前、Google Sites上でcpprefjpサイトを編集していたころは、boostjpのGoogle Groupに参加している人であれば、誰でも自由に編集ができました。

現在はGitHub上で編集作業を行っている関係で、編集権限を現在のコミッタに与えてもらうか、pull requestしてコミッタに取り込んでもらうかする必要があります。

###編集権限を得る方法
編集権限は、旧cpprefjpサイトで編集を行っていた方には、無条件でお渡しします。

以下のページに載っているコミッタの人たちの誰かにコンタクトをとってもらうか、cpprefjp/siteリポジトリのIssue報告として、編集権限の申請を行ってください。

* [cpprefjp members](https://github.com/cpprefjp?tab=members)

コミッタから直接お誘いに行く場合もありますので、快く引き受けていただければ幸いです。

cpprefjpサイトの編集に慣れていない方は、pull requestからでもぜひ始めてみてください。これは、編集権限を得るための審査ではなく、編集の練習のためだと考えてください。pull requestを何回かいただければ、継続して活動していただけるものと判断し、編集権限をお渡しします。


##MarkDown形式による編集方法
cpprefjpサイトは、MarkDown(.md)形式でリファレンスを記述します。

MarkDownは、GitHubサービス上でドキュメントを記述するフォーマットとして広く使用されている形式です。

MarkDownの記述方法をわかりやすく解説してくれているWebサイトは、すでに数多く存在しますので、詳細はそちらを参照してください。

* [Markdown記法 チートシート](http://qiita.com/Qiita/items/c686397e4a0f4f11683d)
* [文章作成やメモ書きにも便利、Markdown記法](http://kojika17.com/2013/01/starting-markdown.html)
* [Markdown文法の全訳](http://blog.2310.net/archives/6)


MarkDown形式では、htmlのタグも併用できますが、cpprefjpサイトでは積極的にはhtmlタグを使用しない方針です。できるだけ、MarkDown形式でできる範囲内で解決するようにしてください。

新規リファレンスを書くにあたって、雛形ページを用意していますので、そちらをベースにして編集作業を行ってください。
* [ヘッダファイルトップページの雛形](./header_template_page.md)
* [関数の雛形](./function_template_page.md)
* [クラスの雛形](./class_template_page.md)
