---
title: "顧客の声をプロダクトに反映したい！Productboardを触ってみた"
emoji: "🦻🏻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["productboard", "ツール"]
published: true
---

# 概要

こんにちは！Lisa Technologies インターンの[なかがわはじめ](https://dev-blog.lisatech.jp/members/hajimenakagawa/)です！

今回、弊社ではより一層顧客の声をプロダクトに反映していくため、Productboard というツールを導入することにしました！

https://productboard.com

こちらはアメリカの Saas ですが、Slack などとは違って日本ではまだまだ導入事例が多くないようですので、筆者が実際に Free Trial で触ってみてわかったことを記事に残そうと思います！

# 課題意識

弊社が Productboard の導入を決めた理由は、顧客の声をプロダクトに反映するフローが整っていなかったことでした。

[FDM](https://fooddeliverymanager.com/) という toB のプロダクトを開発している弊社では、顧客の声をキャッチするのは主に Sales や Customer Success のチームです。彼らは日々前線に立って顧客の声を聞いてくれているのですが、それらをどこに集約するのかは特に決まっていませんでした。Salesforce にメモ書きしておくだけのときもあれば、Slack や Mtg で全体に共有するときもあるし、わざわざ Notion にドキュメントを残しておくときもあります。

ですので、開発側が顧客の声にアクセスしたいときにどこを見ればよいか判断が難しい状況になっていました。よって顧客の声をプロダクトに反映するのは、頻繁にビジネスサイドとやりとりする開発リーダーの属人的な仕事になってしまっていました。

この習慣がボトルネックとなってか、組織全体としても顧客の声をプロダクトに反映することに苦手意識を感じるようになります。そこで「これではいけない、顧客の声をどこかに集約し、スムーズにプロダクトに反映できるようにならなければ」ということになり、Productboard を試してみることにしたのです。

# Productboard の機能

Productboard のコンセプトは”**The customer-centric product management platform**”。顧客中心のプロダクトを作るために、Roadmaps・Prioritization・Insights・Engagement・Integrations の大きく 5 つの機能が提供されています。ドキュメンテーション以外で欲しい機能は大体網羅されている印象です。詳しくは[公式 Docs](https://productboard.com)を御覧ください。

以下では、特に使いたいと思った機能をピックアップして紹介します。

## バックログ＆ロードマップ

Prioritization・Roadmaps の機能です。いわゆるバックログとロードマップの機能がかなり使いやすく提供されています。

https://www.productboard.com/product/prioritization/
https://www.productboard.com/product/roadmaps/

特に感銘を受けたのは Features（バックログ、Prioritization）の機能です。

バックログではタスクの親子関係を明示することができ、Value（その機能が生み出す価値の大きさ）と Effort（その機能を実装するのに必要な工数）を入力することで、Value/Effort Score を自動的に算出して優先順位を付ける補助をしてくれます。また、直近のどのリリースに含めるかをチェックボックスで入力することもできます。

![](https://storage.googleapis.com/zenn-user-upload/ea761a2620dd-20220131.png)

さらにバックログには複数の View が提供されており、とくに 2 次元グラフでタスクの関係性を整理する表示方法には目からウロコでした。

![](https://storage.googleapis.com/zenn-user-upload/1a8c0730d90b-20220131.png)

## 顧客の声を集める

弊社が最も使いたい機能です。Insights と名付けられています。顧客の声を起票して Productboard 上にストックすることができます。

![](https://storage.googleapis.com/zenn-user-upload/7a86f04f69a2-20220131.png)

Productboard では Integrations という豊富なアプリ連携が提供されており、顧客の声の収集も自動化することができます。以下では弊社での利用方法を 3 つ紹介します。

### Google Form から集める

顧客アンケートなどを Google Form で行っており、今までは Slack に流すなどしていましたが、Zapier を通じて Productboard に直接放り込めるようになりました。

**手順**

1. Form を作成し、テスト回答を入力する（1 件以上の回答が入ってないと連携できない）
2. 回答を管理する Spreadsheet を作成する
3. こちらのページの Copy Google Forms responses to Productboard に進む

https://zapier.com/apps/google-forms/integrations/productboard

4. 指示に従って連携完了

新しく回答があるたびに、設定の際に抽出した回答内容をこのように Insights にそのまま蓄積することができます。

![](https://storage.googleapis.com/zenn-user-upload/163268f40a04-20220131.png)
_雑な例ですみません_

### Slack から集める

Productboard で提供されている Slack アプリを用いて、Slack の任意のメッセージを Productboard に push することができます。push するメッセージを Slack 上でも集約するために、リアク字チャンネラーという Slack アプリを使って顧客の声を 1 つのチャンネルにまとめています。

**弊社のフロー**

1. Slack の任意の箇所で顧客の声が共有される
2. そのメッセージに:顧客の声:emoji を付ける
3. メッセージが`#product-fb`チャンネルに転送される（リアク字チャンネラーでそういう風に設定している）
4. `#product-fb`に転送されたメッセージで"Push to Productboard"を選択
5. プロダクト名やコメントを付与し、Productboard に送信

![](https://storage.googleapis.com/zenn-user-upload/c8b29486077e-20220131.png)

![](https://storage.googleapis.com/zenn-user-upload/b95fa47bff30-20220131.png =300x)

![](https://storage.googleapis.com/zenn-user-upload/f61b76fd5cfa-20220131.png)
_Slack 上で情報を入力_

![](https://storage.googleapis.com/zenn-user-upload/8048377fdccc-20220131.png)
_Productboard に蓄積_

### Notion など、任意の Web サイトから集める

Productboard で提供されている Chrome 拡張機能を使って、任意のページからコピペで Productboard に転送することができます。弊社ではユーザーヒアリングインタビューなどは Notion に議事録をとっているので、そこからコピペで転送するフローを構築しました。

https://chrome.google.com/webstore/detail/productboard-make-product/mlpbdkpkicfkhgagnoamdcimmhdkakni

**使い方**

1. 顧客の声をページからコピーする
2. 拡張機能を開く
3. 顧客の名前、顧客の声（ペースト内容）、タグを入力し、Submit する

<!-- TODO 画像 -->

![](https://storage.googleapis.com/zenn-user-upload/f4e4302f3329-20220131.png)

## 顧客の声とタスクを紐付ける

Insights に蓄積された顧客の声を、バックログのタスクと紐付けることができます。

使い方はとっても簡単で、「文章を選択 → 紐付けたいタスクを選択」だけで OK。これを開発陣が行うことで、そのタスクがなぜ必要なのか、どれくらい重要なのかを顧客の声から判断することができます。

![](https://storage.googleapis.com/zenn-user-upload/02f47287cc18-20220131.png)

# 価格

気になるお値段ですが、結構お高い印象です。最安プランでも$20 per maker/month かかります。
https://www.productboard.com/pricing/

ただ、Maker 以外の role、Contributor や Viewer には料金がかからないようですので、アカウントの管理を工夫すればお安く利用できるかも知れません。

![](https://storage.googleapis.com/zenn-user-upload/fa2378db1744-20220131.png)

「顧客の声を集約する」という目標を達成するためには Slack や Chrome extension の機能を利用したいので、最低でも Pro プランを利用することになりそうです。

# 導入事例

導入に際し、他社様での導入事例を調査しました。

## Techtouch さん

https://tech.techtouch.jp/entry/voc_management

**課題意識**
課題意識と導入結果がわかりやすく公式ブログに残されていました。

> 顧客要望が多方面から数多く挙がるようになり、要望の一元管理に加え、要望出所、数、重要度との紐付け、そこから開発優先度を客観的に決める必要性など、従来の管理方法だけでは限界も見えていました。

**導入結果**

> サービス導入の一番の目的であった、営業、顧客、 カスタマーサクセス、社内など多方面からの要望やアイディアを Productboard へ集約して管理ができるようになったことで、情報収集や整理、そのためにかけるコミュニケーション工数が大幅に下がりました。特に、 Slack との連携機能を使い、社内の特定の Slack チャネル（#product_arekore）へ要望を投稿することで、 Productboard 内へ要望が蓄積されるようにしたことで、拾った顧客の声や、自分で気づいた機能改善ポイントといった重要な情報の取りこぼしも減りました。
>
> また、情報が１箇所に集約されたことで、プロダクトへの要望が全社へ見える化されました。これにより、例えば顧客とのコミュニケーションの際には、過去にいただいている要望を把握し、まもなく対応予定であることをスムーズにお伝えすることができたり、機能開発の優先度を決める際には、声の数や要望の出元を踏まえて判断できるようになりました。

## SmartHR さん

プロダクトサイクルの起点として Productboard を利用しているとのことで、Productboard 公式にも掲載されていました。
https://tech.smarthr.jp/entry/2021/06/16/115550
https://www.productboard.com/customers/smarthr/

![](https://cdn-ak.f.st-hatena.com/images/fotolife/a/adachipm/20210614/20210614205107_original.jpg)
_https://tech.smarthr.jp/entry/2021/06/16/115550 より_

# 最後に

ここまでお読みいただきありがとうございます。今回の情報は Free Trial を触った時点での情報だということをお忘れなきようお願いします。これから Productboard を実際に運用していき、さらに知見が溜まったらまた Zenn で公開しますのでぜひお待ち下さいね！

---

記事を最後までお読みいただきありがとうございました！
Lisa Technologies では積極的にエンジニアを採用しております。
資金調達済でこれからどんどん拡大していく面白いフェーズですので、ぜひ覗いてみてください！

Wantedly 募集一覧

- [事業推進のためのプロダクトロードマップを CEO と共に、PdM 募集！](https://www.wantedly.com/projects/753234)
- [Amplify/React/Typescript でアジャイル開発](https://www.wantedly.com/projects/765141)
- [AWS Amplify,AWS CDK ベースで開発！バックエンドエンジニア](https://www.wantedly.com/projects/752467)
- [Figma における開発基盤の設計、土台作りをまるっとおまかせします](https://www.wantedly.com/projects/766407)
- [成長市場、フードデリバリーの管理 SaaS。フロントエンドインターンを募集！](https://www.wantedly.com/projects/752452)

開発ブログ
https://dev-blog.lisatech.jp

プロダクト LP
https://fooddeliverymanager.com/

会社 HP
https://lisatech.jp/

最後までご覧頂きありがとうございました！
