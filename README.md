# Lisa Zenn記事管理リポジトリ
[Lisa TechnologiesのZennアカウント](https://zenn.dev/lisatech)の記事を管理するリポジトリです。

## 技術スタック
- [Zenn CLI](https://zenn.dev/zenn/articles/zenn-cli-guide)

※npm packageなので、Node.jsをインストールする必要があります

## ディレクトリ構成
```
.
├── README.md
├── articles
├── books
├── package-lock.json
└── package.json
```
## Installation
```
git clone https://github.com/Lisa-Technologies/zenn-content.git
cd zenn-content
npm install
```
## Usage
お好きなエディタで執筆を進めることができます。詳しくは[記事執筆の流れ](#writing)を御覧ください。

記事のプレビューの際には以下のコマンドを叩いてください。
```
npx zenn preview
```
以下のようにlocalhostが立ち上がります。
```
👀 Preview: http://localhost:8000
```

また、メニューバーからは様々な解説を読むことができます。


<img width="352" alt="Screen Shot 2021-11-12 at 9 54 03" src="https://user-images.githubusercontent.com/51704330/141393723-0f5df8bb-ba83-43aa-bd6d-99cd3817a345.png">

<h2 id='writing'>記事執筆の流れ</h2>

1. mainから`new/[記事の概要]`という名前でブランチを切ります
2. `npx zenn new:article`で記事の雛形を生成します
3. 執筆します
4. 適切なslugやemoji、tagなどを設定します
5. 推敲段階まで来たらPRを投げ、誤字脱字等をレビューしてもらいます（採用促進テンプレートの内容を最後に書くようにしてください）
6. mainにマージされることで、自動的にZenn側にデプロイされます

## 採用促進テンプレート
下記の内容を記事の末尾に貼り付けてください。テンプレートは採用状況に合わせて適宜更新しましょう！
```md
---
記事を最後までお読みいただきありがとうございました！
Lisa Technologiesでは積極的にエンジニアを採用しております。
資金調達済でこれからどんどん拡大していく面白いフェーズですので、ぜひ覗いてみてください！

Wantedly募集一覧
- [事業推進のためのプロダクトロードマップをCEOと共に、PdM募集！](https://www.wantedly.com/projects/753234)
- [Amplify/React/Typescriptでアジャイル開発](https://www.wantedly.com/projects/765141)
- [AWS Amplify,AWS CDKベースで開発！バックエンドエンジニア](https://www.wantedly.com/projects/752467)
- [Figmaにおける開発基盤の設計、土台作りをまるっとおまかせします](https://www.wantedly.com/projects/766407)
- [成長市場、フードデリバリーの管理SaaS。フロントエンドインターンを募集！](https://www.wantedly.com/projects/752452)

開発ブログ
https://lisatech.blog

プロダクトLP
https://fooddeliverymanager.com/

会社HP
https://lisatech.jp/

最後までご覧頂きありがとうございました！
```

## 関連リンク

- [Zenn CLIで記事・本を管理する方法](https://zenn.dev/zenn/articles/zenn-cli-guide)
- [ZennのMarkdown記法一覧](https://zenn.dev/zenn/articles/markdown-guide)
- [Zennのスラッグ（slug）とは](https://zenn.dev/zenn/articles/what-is-slug)
- [Lisa's Output Hub]()
- [Lisa Zennアカウント](https://zenn.dev/lisatech)
