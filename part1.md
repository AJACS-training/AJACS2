[[AJACS1/講習内容]]へもどる

        --
目次

#contents
        --

# 自己紹介・かずさDNA研紹介 [#zbc1f740]

## 講師の中村 [#te6eb39b]

- 41歳。木更津市在住。

- こんな人です。
    -http://www.kazusa.or.jp/~yn/jp
    -http://navi.kazusa.or.jp/yn/weblog/
    -http://mixi.jp/show_profile.pl?id=49640

- 京大→遺伝研→かずさと「ゲノム」と「情報」を扱ってきています。

## かずさDNA研究所 [#y0a2950c]

我が国初の大規模ゲノム塩基配列決定研究機関です。

- http://www.kazusa.or.jp/
    -シアノバクテリア http://www.kazusa.or.jp/cyano/
    -根粒菌（共生窒素固定細菌) http://www.kazusa.or.jp/rhizo/
    -高等植物(シロイヌナズナ、ミヤコグサ、ユーカリ、トマト)

# 【実習】検索使い倒し [#c09d8a7d]

## google [#ga0bb654]

ま、とにかく、まずは「ググれ」<br>
http://www.google.co.jp

### google は、なぜ検索できるのか [#db84050e]
- 「ロボット」もしくは「クローラー」がリンクをたどって収集にやってくる（以下はとあるかずさのWWWサーバのアクセスログにあったgooglebotの接続の痕跡）
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:33:55 +0900] "GET /~yn/nekophoto/nekophoto-Thumbnails/82.jpg HTTP/1.1" 200 4612 "-" "Googlebot-Image/1.0"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:36:42 +0900] "GET /~yn/images/ika_kaidan.jpg HTTP/1.1" 200 25334 "-" "Googlebot-Image/1.0"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:37:01 +0900] "GET /~yn/jp/index.php?BusTable HTTP/1.1" 200 26037 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:51:15 +0900] "GET /~yn/jp/ HTTP/1.1" 200 15718 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:02:53:59 +0900] "GET /~yn/tdiary/images/ika_kaidan.jpg HTTP/1.1" 404 315 "-" "Googlebot-Image/1.0"
 crawl-66-249-73-53.googlebot.com - - [11/Jul/2007:03:03:44 +0900] "GET /~yn/jp/index.php?Genome2005Mac%2F2.BLAST HTTP/1.1" 200 23155 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
 ...
    -つまり「どこからもリンクのないページ」は原理的に探索不可能
    -どこかからリンクがあれば、いつかはやってくる
    -他のサイトからのリンクが多いほど、また、更新頻度が高いほど、上位にランクされる

- IE右上の虫眼鏡右にある三角をクリックして、検索先をLive SearchからGoogleに変えときましょう。

- 課題：スペース、ダブルコーテーションありなしの意味は？以下の検索結果を比較しましょう。ヒット数・検索結果がそれぞれ違います。
 統合　データベース　センター   515,000件
 統合データベースセンター　160,000件
 "統合データベースセンター　1,060件
 "統合　データベース　センター　1,060件

- なお、規定値が「日本語のページを検索」になっていると思います。「検索オプション」から検索の対象にする言語を「すべての言語」に変えときましょう。

- スペースやダブルコーテーションを入れる場合、全角・半角で違いがありましたか？
- ダブルコーテーションを閉じる必要は実はない、ということに気がつきましたか？
- ヒット数の違いが生じる理由を検索結果を参照しながら、考察しなさい
    -概略: &color(white){単語を空白で分割して検索：OR検索が明示的にかかっている／ダブルコーテーションなし：自動的に「統合／データベース／センター」に分割された結果も混じるが、明示的に分ける程ではない／ダブルコーテーションで囲むと文字通りのフレイズで検索するのでもっともヒットが少ない（が、これも厳密ではなく、分割はされている。また、最後の例では、空白を無視している）}

- 応用: 遺伝子のアクセッション番号やID, 遺伝子名そのものでググる<br>
これが意外に使える。論文のサプリメントファイルが拾えたりする場合も。

- 応用: 英文、とくに前置詞の使い方がただしいかどうか、ググる<br>
日本人の書いた文章がたくさんかかってくると、怪しいわけですよ。


### 一歩すすんだ検索 [#uf1bc65a]

情報リテラシーを高めましょう

- OR検索
googleはなにも指定しないと「AND 検索」つまり、キーワード全てを含むように検索します。<br>
キーワードのどちらか一部を含んでいればいい、といった検索「OR検索」には文字通り「OR」を使います。<br>

- 実習: 以下の検索の意味を考え、検索結果（特に右上の検索結果数) を比較しましょう。どのように違いますか？
 Xenopus tropicalis laevis
 Xenopus tropicalis OR laevis
- 意味: &color(white){ 上：３つのキーワードが全部入っているページを検索 (216,000件) 下：Xenopusに加え、tropicalis か laevis の「どちらか」が記載されているページを検索 (1,430,000件)};<br>

- 応用：以下はそれぞれ、どのような検索をすることになるのでしょうか。その結果は？
 Xenopus OR tropicalis OR laevis
 "Xenopus tropicalis" OR "Xenopus laevis"
- 解答: &color(white){ 上： 3つのうち、いずれかのキーワードがあればよいという、OR検索(5,410,000件)、下：「Xenopus tropicalis」または「Xenopus laevis」のどちらかのフレイズで検索(1,870,000)};<br>

- 応用：うっかり OR を小文字にしてしまいました。するとどのような結果が得られたでしょうか？orをいれないない場合と比較してみましょう。また、後ろにorをもってくるとどうかわりますか？
 Xenopus tropicalis or laevis
 Xenopus tropicalis laevis
 Xenopus tropicalis laevis or
- 考察: &color(white){「or」のような短い頻出パターンも一応キーワードとして考慮されています。キーワードの入力順も検索の考慮の対象になっていますね。};<br>

- *  ワイルドカードを使ってみる<br>
なにが挟まっていても良いことを示す記号。トランプで言うと「ジョーカー」みたいなものです。以下を検索するとどのような文例が得られるでしょうか。''予測してから''実行しなさい。
 vitamin * is good for *

- ..  一定の数値範囲を指定
 Arabidopsis 2001..2006

//-【現在は利用できず】以前は以下のオプションで期間を指定することができた
//date:3, date:6, date12 - 期間指定
// cat genome date:3
<br>期間を明示的に検索したい場合「検索オプション」で詳細に指定可能。

- -(マイナス)  キーワードを除外
キーワード「mouse」でイキモノのネズミの情報を検索するのはかなり困難だったりする。
 mouse
 mouse -パソコン -ホイール -ワイヤレス -アニメ

- filetype  filetype:ppt, filetype:pdf, filetype.doc, filetype:xls, filetype:txt, filetype:html<br>
ファイルタイプ指定 (Powerpoint, PDF, Word書類, Excel書類, text, html)
 blast filetype:ppt
 mouse filetype:xls

- site: inurl:  特定のサイト／URLで検索
以下はそれぞれ何を検索しようとしているかを考え、実際に検索してみて、検索数の違いを比較しましょう
 東京大学
 東京大学 site:u-tokyo.ac.jp
 東京大学 -site:u-tokyo.ac.jp

    -応用：癌の研究に関係するPDF書類とプレゼンテーションを、文部科学省のサイトで探しなさい
    -解答：&color(white){癌 研究 site:mext.go.jp filetype:pdf OR filetype:ppt};

    -応用：データベース統合に関係するPDF書類を、内閣府のサイトで探しなさい
    -解答：&color(white){データベース統合 site:cao.go.jp filetype:pdf};

- link:  特定のサイトへのリンクがあるページ
 link:www.u-tokyo.ac.jp

- 電卓・通貨
http://www.google.com/intl/ja/help/features.html#calculator <br>
ちょっと便利だったりする。乗算はアスタリスク、アスタリスクが２つでべき乗。では以下を計算する方法は？
 3x2
 3の2乗
    -解答：&color(white){上：3*2　下 3**2 （3^2　でも可)};
    -応用：「8ルート3」の結果は何が得られると思いますか?
    -解答：&color(white){（8 かける（ルート３））の結果ですね};
    -応用：「8の3乗根」を求める方法は？
    -解答：&color(white){3th root of 8　どうやら日本語の表記法は無いようです};
    -「1000円を米ドルに」なんてのも可能

## googleなその他のサーヴィスを使い倒す [#j2913449]

- 学術系検索: http://scholar.google.com <br>
学術専門誌、論文、書籍、要約など、さまざまな分野の学術資料を検索。ISIと契約するお金がなくても、論文引用数の概数を知ることは可能。たとえば<br>
 author:y-nakamura
y nakamura さん多すぎです。所属である kazusa を追加してみよう。
 author:y-nakamura kazusa
この人がかずさに来てから10年間の論文のなかで、いちばん引用されてるのはどれだろうか。

    -応用: BLAST ( basic local alignment search tool ) の初出論文を引用している論文数は膨大なモノだと考えられるが、その数を調べ、また、引用している論文を列挙しなさい

    -解答: &color(white){basic local alignment search tool で検索し、引用元を確認};<br>
文献管理ソフトであるBibTeXやEndnoteに取り込むためのファイルダウンロードが可能。see. 検索オプション

- マップ: http://maps.google.co.jp <br>
学会逗留先の土地勘をつかむ。

- カレンダー: http://www.google.com/calendar <br>
ラボやらサークルの予定表共有に便利。iCal との連係も可能。

        --
[[AJACS1/講習内容]]へもどる
