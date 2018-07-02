[[AJACS1/講習内容]]へもどる

        --
目次

#contents
        --

# 塩基配列決定プロジェクトとは [#x0abd262]

## ゲノムとは [#a095499e]
- 「ome」は「総体」を示す接尾辞
    -遺伝子 gene の全体像が gene+ome=genome「ゲノム」
    -ほかには transcriptome, proteome, interactome, phenome などなど
    -こうした網羅的な研究群を「オーミクス omics 」という
    -geneの総体であるgenomeを全部とりつくそうってのが genome sequencing project
- omics のなかでの genome の位置＝最下層＝基盤 infrastructure ＝縁の下の力持ち

## シークエンシング [#j77c6a3b]
- 蛍光によるdideoxy法~
[[図：DNAの鎖の伸長:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p13-1.8.jpg]]~
[[図：１塩基（ヌクレオチド）の違いを見分ける電気泳動:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p179-6.1.jpg]]~
[[図：dideoxy法による塩基配列決定法(1):http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p180-6.2.jpg]]~
[[図：dideoxy法による塩基配列決定法(2):http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/DNAp140.jpg]]~
[[図：蛍光dideoxy法による自動塩基配列決定:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p185-6.7.jpg]]~


## かずさのゲノム塩基配列決定プロジェクト [#idac9f83]
- 光合成 photosynthesis と窒素固定 nitrogen fixation に着目して

## 配列決定戦略 [#x7ec99f5]
- クローンバイクローン clone by clone 法~
クローン毎に、小分けにしてから
- ショットガン shotgun 法~
全ゲノムをばらばらにして、再構成 (assemble)

## ゲノムの構成 [#m0e2a985]
[[図：ゲノムの比較:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p36-2.2.jpg]]~
生物種によって違う

### 原核生物（真性細菌と古細菌） [#e950c2c0]
[[図：大腸菌の核様体:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p55-2.18.jpg]]~
- 塩基配列のほとんどの領域はタンパク質遺伝子

### 真核生物 [#je6f391f]
[[図：ヒト染色体:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p43-2.8.jpg]]~
[[図：ヒトゲノムの構成:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p25-B1.4.jpg]]~
- 塩基配列の多くは繰り返し配列
- エクソン＝イントロン構造
//-ほとんどは無駄な領域と言われてきた → 7割が機能？
- ゲノムデータベース~
    -http://www.ensembl.org/
<br>など

# 【実習】配列情報データベースへのアクセス [#i5e967c0]

## Entrez/Pubmed [#h94237b8]

&color(green){配列と論文に関連した情報を何でも引けるNational Center for Biotechnology Information (NCBI)の生物系検索決定版};

- googleでentrezを検索→Entrez cross-database search ( http://www.ncbi.nlm.nih.gov/Entrez/ )がそれ
- Entrezをひらき、眺める（大量のデータベースの複合体）
- "interleukin-2" で検索してみる
- AND human を追加して絞ってみる ("interleukin-2" AND human で検索)
- AND cDNA
- AND Taniguchi<br>
などでしぼりこみ、NucleotideのACCESSION: J00264 のデータに到達する。
- それぞれのFeatures（からのリンク）を確認しよう。

- 応用：猫アレルギーの人が猫を飼うための猫洗いのテクニックを、学術論文で検索しなさい。(ヒント: wash allergy)
- 解答: &color(white){cat wash allergy で検索＞「Evaluation of different techniques for washing cats: quantitation of allergen removed from the cat and the effect on airborne Fel d 1.」をみよ};

- 応用：「My NCBI」に登録すると、どのようなすばらしいサービスが受けられるのかを確認しましょう。まだ使ってない人はぜひ使いませう。

## GOLD [#l9aeb4fa]

&color(green){世界中のゲノムプロジェクトとESTプロジェクトを網羅したすごいテーブル};

- http://www.genomesonline.org
    -終了したプロジェクト published
    -進行中の古細菌プロジェクト ongoing archaea
    -進行中の原核生物プロジェクト ongoing bacteria
    -進行中の真核生物プロジェクト ongoing eukaryotes
    -メタゲノムプロジェクト（複数の生物をまとめて読んでしまうやりかた） metagenomes

- 生物の種名の調べ方
    -いきなりgoogleとかでもいいんですよ~
http://www.google.co.jp/
//--NCBI taxonomy~
//http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=Taxonomy
    -【実習】猫の学名は？
    -【実習】猫の遺伝子はいくつ知られている？
    -【実習】http://www.genomesonline.org/ を始点にして、ネコゲノムプロジェクトについて調べてみましょう（ヒント:  猫は真核生物）
        -どんな組織が実行している？
        -データは公開されている？
        -で、なんでまた、猫ゲノム？
    -【実習】あなたが興味のある生物種のプロジェクトはないか調べてみよう

## NCBI Taxonomy [#r0d47773]

&color(green){生物分類と配列情報を関連させて調べたい場合にはここ};

- http://www.ncbi.nlm.nih.gov/sites/entrez?db=Taxonomy

## [[CyanoBase>http://bacteria.kazusa.or.jp/cyanobase]] [#ye3ea7e0]

&color(green){光合成細菌シアノバクテリアゲノムデータの世界中心};

- シアノバクテリア '''Synechocystis''' sp. PCC 6803株のゲノム情報はどのように提供されているか
http://www.kazusa.or.jp/cyanobase/ ~
- 典型的なバクテリアゲノムとしてのPCC 6803
- 典型的なゲノムデータベースとしてのcyanobase

# 類似配列の検索法 [#jdb0fd4a]

[[図：配列アラインメント（塩基配列）:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p541-16.8.jpg]]~
[[図：配列アラインメント（タンパク質＝アミノ酸の配列）:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/B5.jpg]]~
[[図：配列アラインメントのためのドットプロット:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/p541-16.9.jpg]]~
[[図：ドットプロット(1):http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/Bp171.jpg]]~
[[図：ドットプロット(2):http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/Bp172.jpg]]~
[[図：ドットプロットの方法(1):http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/Bp169-4.1.jpg]]~
[[図：ドットプロットの方法(2):http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/Bp176-4.1.jpg]]~
//[[図：ドットプロットからのアラインメント例:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/Bp218-4.6.jpg]]~
//[[図：ドットプロットからのアラインメント例:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/Bp218-4.6.jpg]]~

//**アミノ酸配列のアラインメント [#f7b2516b]
//***「マトリクス」＝類似の程度を示す [#j18f41ca]
//-PAM250
//-BLOSUM62

### ダイナミックプログラミング = DP [#kf4d0708]
- 「最適経路中の部分経路もまた最適経路になっている」
- 動的計画法は、この原理を利用して最適化問題を解く。
- ある問題を、多段階に「バラす」ことができる場合、動的計画法によって各段階の最適解(経路)を求め、それをたどることで、全体の問題を解くことが可能になる。

### まじめにDPやるとタイヘンなんで、はしょる [#y88f8f8a]
- FASTA
    -よく似た領域の周囲だけをDPで探索
- BLAST
    -「ワード」の一致を発見
    -そこからアラインメントを横へ伸ばす。伸びなくなったらあきらめる。
    -きわめて高速で巨大配列も探索可能
- BLAST検索のprogram option
|program|Query|DB|概要|
|BLASTN|核酸配列|核酸配列|問い合わせ配列と類似の核酸配列を検索|
|BLASTP|アミノ酸配列|アミノ酸配列|問い合わせ配列と類似のアミノ酸配列を検索|
|BLASTX|核酸配列|アミノ酸配列|問い合わせ核酸配列をアミノ酸に翻訳した配列で、類似のアミノ酸配列を検索|
|TBLASTN|アミノ酸配列|核酸配列|アミノ酸配列を核酸配列のデータベースを翻訳したものと類似の配列を検索|
|TBLASTX|核酸配列|核酸配列|問い合わせ核酸配列を全フレーム翻訳したものを、核酸配列データベースを全フレーム翻訳したものとの類似を検索|
|PSI-BLAST|アミノ酸配列|アミノ酸配列|問い合わせ配列とアミノ酸データベースとの検索を繰り返すことで、弱い類似しかない配列を検索可能にする方法|
|PHI-BLAST|アミノ酸配列|アミノ酸配列|配列の「パターン」で類似の配列を検索する|

# 【実習】BLASTあれこれ [#h3678dfb]

&color(green){配列検索のホームラン王};

- http://www.ncbi.nlm.nih.gov/blast/ を開く<br>
- 「protein BLAST」を選択
- 「Search」窓に以下の配列をコピペする (cmd-C then cmd-V)
// >opsin Rh2(Drosophila melanogaster)
 MERSHLPETPFDLAHSGPRFQAQSSGNGSVLDNVLPDMAHLVNPYWSRFAPMDPMMSKIL
 GLFTLAIMIISCCGNGVVVYIFGGTKSLRTPANLLVLNLAFSDFCMMASQSPVMIINFYY
 ETWVLGPLWCDIYAGCGSLFGCVSIWSMCMIAFDRYNVIVKGINGTPMTIKTSIMKILFI
 WMMAVFWTVMPLIGWSAYVPEGNLTACSIDYMTRMWNPRSYLITYSLFVYYTPLFLICYS
 YWFIIAAVAAHEKAMREQAKKMNVKSLRSSEDCDKSAEGKLAKVALTTISLWFMAWTPYL
 VICYFGLFKIDGLTPLTTIWGATFAKTSAVYNPIVYGISHPKYRIVLKEKCPMCVFGNTD
 EPKPDAPASDTETTSEADSKA
- 「Choose database」で「swissprot」を選択
- 「BLAST」ボタンをクリック<br>
- CCDが示される
- 画像の7tm_1をクリック<br>
conserved domainとして「pfam00001, 7tm_1, 7 transmembrane receptor (rhodopsin family)..」が見いだされた（７回膜貫通型receptor; Pfam00001）
- （戻る）
- 配列リストの右の「G」は「Entrez gene (遺伝子ごとに情報をとりまとめたデータベース)」へのリンク
- 下へスクロールして「Alignments」の上から順に数本にチェック入れる
- 「Distans tree of results」をクリック
- 「Tree Method」を「Fast Minimum Evolution」から「Neighbour joining」に変更したり、樹型を「rectangle」から「slanted」「radial」などに変更してみましょう

- 応用:「マトリクス」をかえて検索してみましょう。
- 応用:table format は大量にサーチする際に便利です。

//-e-valueとは？
//-E = Kmn^(e-λS)
//<br>そのライブラリで偶然に同じスコアでヒットする''本数''の期待値

        --
[[AJACS1/講習内容]]へもどる
