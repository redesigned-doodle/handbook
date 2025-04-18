+++
date = '2025-04-08T21:52:07+09:00'
title = 'Problem Discovery'
author = ['Kento Maruyama']
weight = 10
+++

## 初期ターゲットユーザのペルソナ

我々は、初期のターゲットユーザとして次のペルソナに決定した。

> **WebベースのSaaSを提供し、MVP開発中〜PMF達成のフェーズにいる企業の開発チームに所属する、チームの決裁権を持つCEOやCTO、Tech-Lead Manager、Tech-Lead、Managerの人物でかつ、開発チームとユーザとの繋がりに課題を感じている方をターゲットにする。**

- **企業種別:** WebベースのSaaSを提供している企業。企業のうち、どちらかというとスタートアップ・ベンチャー企業を優先するが、大企業も含めていく。
- **業種:** toBとtoCの種別は問わない
- **開発チームのフェーズ:** MVP開発中〜PMF達成のフェーズ
- **具体的な人物像:** チームへの製品導入を決定できる重要な役割の人物を対象とする。会社のCEOやCTO、チームのTech-Lead ManagerやTech-Lead、Managerの役割を担う人物を狙う。
- **課題に対する温度感:** 中〜大。ユーザとの繋がりの薄さになんとなく課題を感じている方。もしくは大いに課題に感じており、試行錯誤している方。

> {{< collapse summary="ペルソナ決定の背景" >}}

### ペルソナ決定の背景

自分たちが今持つ知識を活用できるよう、WebベースのSaaSを提供する企業とした。導入や意思決定にスピード感のあるスタートアップやベンチャー企業に所属する開発チームを基本的なターゲットにしている。絶対数が少ない可能性を考慮し、大企業も含めている。

業種を問わない理由としては、ユーザとの繋がりという課題に業種は大きく影響しないと考えているため。つながるユーザの数に変化はあるが、つながることの難しさとつながりを維持する大変さは変わらないと判断した。

フェーズをMVP開発中〜PMF達成とした理由は、このフェーズの開発チームが最もユーザとのつながりを必要とするからである。

具体的な人物像については、チーム内で重要な役割を担っており、かつ最終的に製品導入の判断ができる人物を設定している。

{{</ collapse >}}

---

## 課題の仮説

ソフトウェアサービスを提供する多くの開発チームは、次の課題を抱えていると仮説を立てた。

> - **開発チームとユーザとの繋がりが薄い**

この課題は、開発チームに次の影響を及ぼす。

- どの機能を実装するべきかを判断することができない
- 実装した機能がどのように使われているかを知ることができず、機能の改善案を考えることができない
- ユーザが喜んで課金し、価格よりも価値を感じるプロダクトになれず、PMFを達成できない

「開発チームとユーザとの繋がりが薄い」という課題はさらに深掘りすることができる。 **ここでの課題仮説では、我々がこれから解決策で取り組む、最も上位の課題を設定することにした。これからつくるプロダクトが解決する、課題の範囲を定義するものである。** 

そのため、以降の深掘りについては、次のシーンなどで利用される。

- MVPで取り組む課題を決定する
- 実装する機能の優先順位を決定する

> {{< collapse summary="仮説を立てるまでの背景" >}}

## 仮説を立てるまでの背景

### 1. 大まかな市場性・課題の調査

はじめに、知人・友人の開発者に対し、どんな課題を抱えているかについて、市場性と課題のインタビューを行った。次の質問を行い、どんなことに普段困っているかを聞いた。

- 開発チームの仕事に満足しているか？
- 開発チームでの仕事で、直近で強くストレスに感じた出来事を教えてくれますか？

**3名に確認し、どの方も仕事自体に満足していると回答した。** ストレスに感じた出来事についても回答を得たが、一貫性や共通点はなかった。この聞き方では、回答が発散してしまい、課題の分析につなげるのは難しいと感じた。

---

### 2. 自身の経験から課題の手がかりを考える

自分自身に対しても上記の質問を問いかけ、自己分析をしてみた。結果は次のとおり。

- チームでの仕事に満足していない
- **自分が真剣に取り組み、時間と労力をかけて生み出した製品が全く使われない**ことにストレスを感じた（このとき、私は製品に対する大きな方針を決定できる立場ではなかった。エンジニアとして、自分ができる最大限のことをやっていたということ。）

原因を分析し、次の事項によって「時間と労力をかけて生み出した製品が全く使われない」状態になったと考えた。

- **構想初期や開発途中で、ユーザに市場性の確認を徹底していない**

---

### 3. 市場性・課題の再調査

特に日本において、ユーザと会話する文化はあまり馴染みがない。**ほとんどの開発チームは、ユーザと深く会話していないのではないか？と、ここで考え始めた。** これを検証するため、市場性と課題のインタビューの設問内容を次に変更し、再度確認を行った。

- 最近、開発チームで「手間がかかる」「面倒だな」と感じた作業やプロセスはありますか？
- **「本当にユーザが求めているものを作れているか」という点について、あなたの感覚に近いものを選んでください。**
- **プロダクトの方向性や意思決定について、チームで感じていることがあれば教えてください。**

2名に確認し、次の情報を得ることができた。

- スタートアップに所属する方は、ユーザが求めるものを作れていることに自信を感じていると答えた。大企業に所属する方は、合っていると思うが確証はないと答えた。
- スタートアップに所属する方であっても、機能が実際にどう使われているのかまでは把握しきれていない
- **2人とも「作る機能が明確に決まっており、迷うことがあまりない」と答えなかった**

この結果と自身の過去の経験から、開発チームとユーザの間に何らかの課題があると考え、この課題を分析することにした。

---

### 4. ターゲットユーザに到達することが難しい

課題分析をするため、先の2名以外の他の開発者からインタビューを伺うことにした。特に、友人・知人にいないスタートアップ・ベンチャー企業に所属する開発者にコンタクトをとろう考えた。

しかし、次の施策を試したが、ターゲットの開発者とつながることが全くできなかった。

1. XやLinkedinのソーシャルアカウントに対し、DMでFormの回答依頼を行う
    - **ほとんどの人がDM機能を無効にしている**
2. 直近に資金調達を行ったスタートアップ企業に、コーポレートサイトの問い合わせ経由でFormの回答依頼を行う
    - 問い合わせページの本来の使い方ではない。倫理的にアウトか、**目的外利用禁止の文言がある。**
3. スタートアップが好きそうなテックイベントに参加し、懇親会で知り合いになり、インタビューを行う
    - **自然な参加をすると、普通は連絡先交換まで至らない。** 2-3回の参加が必要になる場合もある。コアユーザになる確度が低く、**時間のコストと見合っていない**。

ここで、次の情報を得ることができた。

- **ユーザとつながることに時間と労力がかかりすぎる**

---

### 5. 開発チームとユーザのつながりが薄い

ターゲットユーザに到達する他の施策として、次があると考えた。

- QiitaとZennに投稿を行い、開発チームとユーザの間に課題を感じる人とつながる。投稿の内容に、Slackコミュニティへの案内を記載し、密につながる環境をつくる。
- ターゲットユーザが集まりそうなイベントを主催する。集まったユーザにコンタクトをとり、コミュニティメンバーに誘い込む。

Slackコミュニティづくりを試していると、次に気づくことができた。

- 呼び込むまでは可能かもしれないが、**持続的に密で熱意のあるつながりを維持するには、多くの工夫が必要**
    - 協力してくれる人に「自分事感」を与え、ともに製品をつくるように感じさせる運用が必要
    - 協力してくれる人にインセンティブを与える仕組みが必要
    - Slackを普段使わない人であれば、LINEで別途通知するなどの工夫が必要
    - みんなが活発に意見を出せるように、場を回すような運用が必要
    - 参加者が増えても、誰でも気軽に発言できるように、心理的安全性の確保が必要

ユーザとつながることに時間と労力がかかるが、**つながったあとも大変な労力がかかる**ことを理解し始めた。開発チームがユーザに便利でクールな製品を生み出すには、ユーザの声が必須である。しかし、ユーザとつながることも、その後のつながりを維持することも**実際はとても大変**である。

また、開発チームが持続的に、ユーザに便利でクールな製品を届けるためには、次の開発アプローチが必要ではないかと気づいた。

- **開発チームとユーザがひとつのチームとなる、Community-drivenな共創型のプロダクト開発**

オープンソースプロジェクトのように、ユーザがissueを起票したり、活発に意見したり、と**開発チームとユーザが密にコラボレーションすることが、便利でクールな製品を生み出す解決策になる**のではないかと気づいた。これを課題の仮説に立て、検証していくことを決めた。

{{</ collapse >}}

---

## 課題仮説の検証

### ゴールの定義

課題仮説が、市場で **"明確に存在し"**、かつ **"痛みを伴っている"** 課題であると確信できること。次の3点が明らかになっていることが、そのサインである。

- **"具体的なエピソード"** と **"感情の痛み"** を複数のユーザーから引き出せている
- その課題に対して **"すでに行動している"** か、あるいは **"行動したがうまくいっていない"** 証拠がある
- 課題が **"意思決定や行動"** に影響していることがわかる

> {{< collapse summary="3点の詳細説明" >}}

### 1. "具体的なエピソード"と"感情の痛み"を複数のユーザーから引き出せている

- ただ「困ってる」と言うのではなく、実際に“失敗した” or “損失を出した”エピソードが語られているか？
- それが個別の現象ではなく複数人に共通しているか？
- そのときの**感情（イライラ、もやもや、悲しみ、恐怖など）**を覚えていたか？

> 例：「ユーザーの声を聞かずに機能を出したら、リテンションが一気に落ちた。営業からも怒られて、チームの士気が下がった。」

### 2. その課題に対して"すでに行動している"か、あるいは"行動したがうまくいっていない"証拠がある

- ユーザーが自分なりに工夫や回避策をとっているか？（Slackでユーザーグループを作っている、Notionでログをとっている、など）
- その解決手段に満足していない、あるいは「うまくいっていない」ことを認めているか？

> 例：「Notionでユーザーの声を記録してたけど、全然見返さなくて形骸化してるんです…」

### 3. 課題が"意思決定や行動"に影響していることがわかる

- その課題がチームの方向性のブレや開発ミス、優先度判断ミスなどに繋がっているか？
- 「この問題があるから、○○ができない」と言っているか？

> 例：「ユーザーの本音がわからなくて、どの機能を次に作るか決められず、結局上司の一声で決めるようになっている」

{{</ collapse >}}

### 課題仮説検証のプロセス

#### 1. ペルソナに該当する、課題に共感するユーザと接点を獲得する

Zenn, Qiita, noteのプラットフォームで、課題に対して激しく共感できる、ユーザに刺さる投稿を行う。投稿に書かれた連絡先から、ペルソナに該当するユーザとの接点を獲得する。

#### 2. ユーザと対話を行い、課題検証ゴールの確認を行う

先に、ペルソナに該当するユーザであるかどうかを確かめる。

> - 現在開発されているプロダクトについて教えてください
> - 現在の開発フェーズは何でしょうか？正式リリースされていますか？
> - 企業種別と開発チームでの役割を教えていただけますか？

ペルソナに該当する方と分かれば、インタビューのアポイントメントを取る。その際、インタビューの背景と目的、主な聞きたいことを伝える。

> 私は今、プロダクトをつくる多くの開発チームが **「ユーザとの繋がりの薄さ」に、課題を感じている**と予想しています。
> 「開発チームとユーザの距離感が遠い」ことで、開発チームに次のような問題を起こしていると考えました。
> 
> - ユーザに対し、どんな機能を実装すればよいかが分からない
> - PMFを達成するプロダクトに成長できない
> 
> もし、この課題を解決できる製品があれば、**〇〇さんのプロダクトを大きく成長できるきっかけをつくれる**と確信しています！
> ぜひ30分ほどお話させていただき、次のことをお聞きしたいです。
> 
> - ユーザーとのフィードバックループを構築していますか？**ユーザーの意見をどのようにプロダクトに反映しているか**をお聞きしたい。
> - 現状のフィードバックループの仕組みに**不満**を感じませんか？**仕組みを変えよう**としたことはありますか？
> - ユーザーの声や意見が、あなたの会社やチームに **どれほど影響を与えていますか？** それぞれ、大中小でお答えください。
>   - 会社の全体目標、経営戦略や経営計画 → CEOやCTOの経営層レベル
>   - プロダクトの方針やロードマップ、開発計画 → TLMやTL, Managerのリーダーレベル
>   - UIやUX、デザイン、詳細の実装方針 → エンジニアやデザイナーなどのチームメンバーレベル

上記のストーリーに沿って対話を進め、課題検証のゴールである次についてをユーザから聞き出す。

- **"課題が原因で発生する問題の具体的なエピソード"** と **"そのときの感情の痛み"**'
- その課題に対して **"すでに行動している"** か、あるいは **"行動したがうまくいっていない"** 証拠があること
- 課題が **"意思決定や行動"** にどれほど影響しているかがわかる

これにより、**「開発チームとユーザとの繋がりが薄い」** という課題が、次の内容であるかを確認することができる。

- 市場に**明確に存在**し、ユーザにとって**大きな痛みを伴う**ものであるかが分かる
- 既存の解決手段では課題の解決が**難しい**、または**満足できない**ものであるかが分かる
- 課題が、経営層レベル、リーダーレベル、チームメンバーレベルに、**どれほど影響を与えているか**が分かる

上記3つの確認ができることで、はじめて取り組むべき課題かどうかを判断することができる。次のチェックリストで7点以上と判断できるなら、MVP開発へ進む。

検証項目 | 基準 | スコア
| --- | --- | ---
感情的痛み | 明確なエピソード＋言語化された感情あり | 3
行動実績 | 明確な打ち手を既に実行 or 試行した証拠あり | 3
意思決定への影響 | 経営/プロダクト/実装方針に1つ以上影響 | 3
合計点 | 9点満点中7点以上なら真の課題 | –

---

## 検証結果

記載予定

---