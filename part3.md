[[AJACS1/講習内容]]へもどる

        --
目次

#contents
        --

# 塩基配列の注釈(annotation)の基礎 [#sa5d9189]

## ゲノムの注釈 genome annotation [#bda4c807]

- 構造注釈 structural annotation~
遺伝子の構造を記載したアノテーション
- 機能注釈 functional annotation~
遺伝子の機能を記載したアノテーション

- http://www.ncbi.nlm.nih.gov/entrez/viewer.fcgi?db=nuccore&id=4732164   (F10A2 entry)<br>
featuresなどの注釈がどのようについているのか、眺めてみましょう。

- Three major DNA databanks
    -JP: http://www.ddbj.nig.ac.jp/
    -EU: http://www.ebi.ac.uk/embl/
    -USA: http://www.ncbi.nlm.nih.gov/Genbank/

- examples of genome database
    -cyanobacteria: http://www.kazusa.or.jp/cyanobase/   (photosynthesis)
    -rhizobia: http://www.kazusa.or.jp/rhizobase/   (nitrogen-fixation)
    -Arabidopsis: http://www.arabidopsis.org/   (TAIR: flowering plant model)
    -Ensembl: http://www.ensembl.org/   (human, animals, disease-related)

## 遺伝子の「構造 structure」を予測すること [#j89c2b23]
- DNAは読めるが、それだけでは遺伝子はわからない
- ゲノムを読んだら遺伝子の構造を把握することがまず第一
//-遺伝子の位置決めはゲノム解析の基盤＝インフラ整備
//-ゲノムが決まってもその中身はこんなにわかっていない、というお話

## 遺伝子構造アノテーションの基礎 [#q9fdb41d]
//***ORF (open reading frame) [#l8a4b34d]
//--「読み枠」reading frame とは
//--開いた読み枠は遺伝子か
//--【実習】開いた読み枠を探してみよう
### 類似配列検索 [#rebbc40e]
- 既知の遺伝子に類似な配列は遺伝子たぶん
- オーソログ ortholog （種分化と同時に遺伝子が分離）
- パラログ paralog （種のなかで遺伝子が重複）

- NCBI BLAST
    -http://www.ncbi.nlm.nih.gov/BLAST/
- DDBJ BLAST
    -http://blast.ddbj.nig.ac.jp/top-j.html
    -日本語・clustalwへの連続技が可能
- BLAT
    -http://genome.ucsc.edu/cgi-bin/hgBlat
    -高度な一致を検索する。やたらと高速


# 【実習】遺伝子発見ツール [#md656140]

## Genemark.hmm [#x185ce9c]

- http://exon.gatech.edu/genemark/
    -http://exon.gatech.edu/genemark/gmhmm2_prok.cgi   (for prokaryotes)<br>
Prediction models have been pre-computed for a 265 completely sequenced prokaryotic genomes from the NCBI RefSeq database.

## Glimmer [#u38779c8]

- http://www.cbcb.umd.edu/software/glimmer/
- http://www.ncbi.nlm.nih.gov/genomes/MICROBES/glimmer_3.cgi  (server)<br>
（long ORFs からマトリクスを作り、遺伝子発見（ここでかけるにはjobが大き過ぎるのでパス）

# 真核生物のゲノム注釈 [#m3883d2b]

## 原核生物よりも困難な理由 [#j2f2d67d]
+遺伝子密度が低い
+遺伝子構造が複雑
    -エクソン＝イントロン構造
    -エクソンはタンパク質を指定する情報が載っている「コード領域」
    -イントロンは転写後にスプライシングにより切り捨てられる「非コード領域」
    -イントロンが切り出されることをスプライシングという
    -イントロンが切り出される位置をスプライスサイトという~
スプライスサイトをきちんとおさえないと、コード領域が「ズレ」てしまう

## 真核生物は「コード領域予測＋スプライスサイト予測の組み合わせ」 [#r60e1c65]

## コード領域予測の方法 [#ff7ae0c2]
- 配列類似＋遺伝子予測法（原核生物と同じ）
- expressed sequence tags (EST) を貼り付ける方法
    -dbEST: http://www.ncbi.nlm.nih.gov/dbEST
    -転写されたRNAを逆転写したものがcDNA (complementary DNA)
    -cDNAの端だけを重複をゆるして大量に読んだものがEST
    -転写(transcription)されたRNAを網羅的に研究する→「transcriptome」である
- 大量に存在するESTや、アミノ酸配列を貼り付けることで遺伝子を探す
    -GT-AGルールに従うのがキモ

- おすすめmapping tools
    -BLAT: http://genome.ucsc.edu/cgi-bin/hgBlat
    -sim4: http://globin.cse.psu.edu/globin/html/docs/sim4.html
    -wise: http://www.ebi.ac.uk/Wise2/  <br>
(protein sequence to a genomic DNA sequence, allowing for introns and frameshifting errors)

## スプライスサイトの予測 [#lca1700f]
    -保存されている短い配列パターンをコンセンサスという
    -スプライスサイトのコンセンサスは GT-AG しかない
    -スプライスサイトの周辺の微弱な情報を「総合」
        -ニューラルネットワークによるモデル化~
モデル化に際しては、学習データの厳選が重要！
    -NetGene2 <br>
http://www.cbs.dtu.dk/services/NetGene2/

## 真核生物ゲノムの遺伝子発見の実際 [#caa761ab]
- 複数の解析方法の組み合わせによる画像化
- 手作業による「編集」が必須である
- それでも最大65%の精度~
実験の情報のフィードバックにより修正が必要
//--【実習】遺伝子発見法を組み合わせて遺伝子を見つけてみよう

# 【実習】スプライスサイト予測・Martでデータ取得 [#meafb78a]

## Netgene2 [#n68b0d1b]

- http://www.cbs.dtu.dk/services/NetGene2/

    -Human, C. elegans（線虫）, A. thaliana（シロイヌナズナ）
    -シロイヌナズナのマトリクスは双子葉植物の多くに使える（すくなくとも、ミヤコグサとトマトでは実用になることを確認した）

## C. elegansのcDNAの配列ををゲノム塩基配列にマップして、その結果とスプライスサイト予測の結果を比較しよう [#q5d691f9]

- C. elegansのcDNAもしくはmRNAの配列をどのようにして取得するか?<br>
++"Caeno..."のつづりが思い出せなかったので、NCBI Taxonomyに行って nematode で検索
++Caenorhabditis elegansがでてきたので、開く
++Nucleotideの横の数字(384,898)をクリックしてEntrezを開いた
++検索窓の txid6239[Organism:noexp] に "full length cDNA" を追加して問い合わせすると２配列が得られた
++L39939を開いてfeaturesの「mRNA」をクリックし、以下のcDNA塩基配列を得た。
 >(gi|675503:276-323, 373-448, 496-590, 634-729, 923-1264, 1319-1591, 1639-1856, 2003-2114) Caenorhabditis elegans cathepsin B-like cysteine proteinase (cpr-6) gene, complete cds
 AAGCGACGACAACTTGCGATCAACACGCTGACCGTCGACGCCAACATGAAGACGTTGCTCTTCCTTTCCT
 GCATAGTGGTAGCAGCTTATTGCGCATGCAATGATAACCTTGAGTCCGTTTTGGACAAATATCGCAATCG
 TGAAATTGACTCAGAAGCAGCTGAGCTTGACGGAGATGACTTGATCGACTATGTCAATGAAAACCAAAAT
 CTTTGGACGGCTAAGAAACAAAGACGTTTTTCATCGGTCTACGGAGAGAACGACAAGGCGAAATGGGGAT
 TGATGGGTGTCAACCATGTCAGACTTTCTGTTAAGGGCAAACAACACTTGTCCAAGACCAAGGATCTCGA
 TTTGGACATTCCAGAAAGCTTTGATTCTCGTGACAATTGGCCAAAATGCGATTCCATCAAGGTCATCAGA
 GACCAGTCAAGCTGTGGATCCTGCTGGGCTTTCGGAGCCGTTGAGGCAATGTCTGATCGTATTTGCATTG
 CTTCCCATGGAGAACTTCAAGTTACACTTTCCGCTGATGATCTTCTCAGTTGCTGCAAAAGCTGTGGATT
 CGGATGTAACGGAGGAGATCCATTGGCTGCCTGGCGCTACTGGGTGAAGGATGGAATCGTTACTGGATCA
 AACTACACCGCTAACAATGGGTGCAAGCCATACCCATTCCCACCATGTGAGCATCACTCGAAGAAAACCC
 ACTTCGATCCATGTCCACACGATTTGTACCCAACTCCAAAATGTGAAAAGAAGTGCGTTTCTGATTACAC
 TGACAAGACTTACTCCGAGGACAAATTCTTTGGCGCCAGCGCGTACGGAGTCAAGGATGACGTTGAAGCC
 ATCCAGAAAGAATTGATGACTCACGGACCCCTTGAGATCGCTTTCGAGGTTTACGAGGATTTCTTGAACT
 ATGACGGTGGAGTCTATGTTCACACCGGAGGAAAGCTCGGAGGAGGACACGCCGTCAAGCTTATCGGATG
 GGGTATTGACGATGGAATCCCATACTGGACAGTTGCCAACTCTTGGAACACCGACTGGGGAGAGGATGGA
 TTCTTCCGTATCCTGAGAGGAGTTGATGAGTGTGGAATTGAATCTGGAGTTGTTGGAGGAATTCCAAAGC
 TCAATAGTCTTACCTCAAGACTTCACAGACACCACCGCCGCCACGTCTACGATGACAACTACTGAACCAT
 CATTCCATTTGAACAAAACCTTTATTTCTTTTAAATTTCTATATGTATAAAAATGAATGAGTTAATCAAT
++ゲノムへのマッピングはBLATが高速で良い。UCSCを使う ( http://genome.ucsc.edu/ )
++BLAT -> C. elegans でサーチする。一瞬で結果が返るのでびっくりする。
 browser details 675503:276-323  1253     1  1260  1260 100.0%     X   +    6607162   6609000   1839
が最も良くマッチしているので、browserでマッピングの状況をながめる。画像をたたくとdetailsのリンク先と同じ情報が表示される。BLATはGT-AGルールにしたがってcDNAの配列をゲノムにマッピングしていることに注意されたい。ゲノム上のポジションになっているのでわかりにくいが、8つのエクソンがただしくゲノム上に対応づけられている。
++次に、Entrezから、このcDNA配列を含むゲノムの塩基配列を得る（単にfasta formatでこのエントリの全体を表示した結果）
 >gi|675503|gb|L39939.1|CELCPR6G Caenorhabditis elegans cathepsin B-like cysteine proteinase (cpr-6) gene, complete cds
 ATTAGGTTTTTCCATCATATAACCCTTTCAAACGAAATTAATGTGCTAAATCTGTTAAGTTTCAATATTT
 TCCTTGTCTTTAGGTCAATCTTCTTTGCCACACAGTTCAAACTACTACCGCCGAGTCACGTCACACCATC
 ACAGGATAGTGACCGGTCCTAGGATGTACCCTGACACTGTGATGGACGCAGCCGACACTCTTATCGAAAT
 GCACAGGGCCAAATTTGATAACGAAAACATGTTCTATAAAAGCATGCTGATAAAAGCGAGCAGTCAAGCG
 ACGACAACTTGCGATCAACACGCTGACCGTCGACGCCAACATGGTAGGCTTTTGAACTTTGAAGTAATTT
 TTAGAGAAAATTTGAATTCTAGAAGACGTTGCTCTTCCTTTCCTGCATAGTGGTAGCAGCTTATTGCGCA
 TGCAATGATAACCTTGAGTCCGTTTTGGGTAGGTTGGATATTGATGAAGCTTTCTGAAAATTTCAATTTA
 TTAAGACAAATATCGCAATCGTGAAATTGACTCAGAAGCAGCTGAGCTTGACGGAGATGACTTGATCGAC
 TATGTCAATGAAAACCAAAATCTTTGGACGGTAAACTTATACTCACAAAATATTCATCTAATGGATTTTT
 CAGGCTAAGAAACAAAGACGTTTTTCATCGGTCTACGGAGAGAACGACAAGGCGAAATGGGGATTGATGG
 GTGTCAACCATGTCAGACTTTCTGTTAAGGTATGCACATCAAATTTGAATTCGGTTATTTGAAAACGTCA
 ATTGTTTTGATTGATAGACGGCTTATCACAAAATAGAAGAGAATCAGACTGAAACATCAGGTGATCAAGT
 TATAGATAGTGATCTTATATTCAAACAGTGCCTATCACTTCACTCACGTGCTCAACCATTCCACCCAAAC
 AGCACTTTTCAGGGCAAACAACACTTGTCCAAGACCAAGGATCTCGATTTGGACATTCCAGAAAGCTTTG
 ATTCTCGTGACAATTGGCCAAAATGCGATTCCATCAAGGTCATCAGAGACCAGTCAAGCTGTGGATCCTG
 CTGGGCTTTCGGAGCCGTTGAGGCAATGTCTGATCGTATTTGCATTGCTTCCCATGGAGAACTTCAAGTT
 ACACTTTCCGCTGATGATCTTCTCAGTTGCTGCAAAAGCTGTGGATTCGGATGTAACGGAGGAGATCCAT
 TGGCTGCCTGGCGCTACTGGGTGAAGGATGGAATCGTTACTGGATCAAACTACACCGCTAACAATGGGTG
 CAAGGTACAAATAGTACAAGAATAAAAAGATTTCAAACTAGAACCTAACCTTTTTCAGCCATACCCATTC
 CCACCATGTGAGCATCACTCGAAGAAAACCCACTTCGATCCATGTCCACACGATTTGTACCCAACTCCAA
 AATGTGAAAAGAAGTGCGTTTCTGATTACACTGACAAGACTTACTCCGAGGACAAATTCTTTGGCGCCAG
 CGCGTACGGAGTCAAGGATGACGTTGAAGCCATCCAGAAAGAATTGATGACTCACGGACCCCTTGAGATC
 GCTTTCGAGGTTTACGAGGATTTCTTGAACTATGACGGTGGAGTCTATGTTGTGAGTTGTACTGTTATTT
 GACATAAAAACCTGAAAAAAAAATTCAGCACACCGGAGGAAAGCTCGGAGGAGGACACGCCGTCAAGCTT
 ATCGGATGGGGTATTGACGATGGAATCCCATACTGGACAGTTGCCAACTCTTGGAACACCGACTGGGGAG
 AGGATGGATTCTTCCGTATCCTGAGAGGAGTTGATGAGTGTGGAATTGAATCTGGAGTTGTTGGAGGAAT
 TCCAAAGCTCAATAGTCTTACCTCAAGACTTCACAGGTGAACTTTTCAGCTATATTGCACGTGACATCTA
 AAAAAAATATGATGTGATTTCGTTTCATGACTCCCATGCCAATGCCCAATTTCCTAAACGGAAACCTACT
 TTTTATCTACTTAACTACTAAACCAACTTTTTTATGTTTCAGACACCACCGCCGCCACGTCTACGATGAC
 AACTACTGAACCATCATTCCATTTGAACAAAACCTTTATTTCTTTTAAATTTCTATATGTATAAAAATGA
 ATGAGTTAATCAATATTTGCATTATAGAATGTTTCTAGAAGAAGTTCGTGGCCGATAGAACTTTAACTGA
 AATCCTAACAACACACTAAATCATTTGTAATTCTGCGCTCAGTTCCGATTGTGTCAAATGTTTTGCAAAG
 TTTTCGTGCTGTTGTTCTCTCCGGCAATATCTTTTTTCTTTCTAGAAAC
++これをNetGene2 serverで解析してみる。
 Donor splice sites, direct strand
 ---------------------------------
               pos 5'->3'  phase strand  confidence  5'      exon intron    3'
                   324       1     +        1.00       CGCCAACATG^GTAGGCTTTT H
                   344       0     +        0.74       GAACTTTGAA^GTAATTTTTA
                   449       1     +        0.85       TCCGTTTTGG^GTAGGTTGGA
                   453       2     +        0.74       TTTTGGGTAG^GTTGGATATT
                   591       0     +        1.00       TCTTTGGACG^GTAAACTTAT H
                   712       0     +        0.96       TGTCAACCAT^GTCAGACTTT
                   730       0     +        1.00       TTCTGTTAAG^GTATGCACAT H
                  1265       0     +        1.00       TGGGTGCAAG^GTACAAATAG
                  1857       1     +        1.00       GACTTCACAG^GTGAACTTTT H

 （complement略)

 Acceptor splice sites, direct strand
 ------------------------------------
               pos 5'->3'  phase strand  confidence  5'    intron exon      3'
                    83       2     +        0.00       TTGTCTTTAG^GTCAATCTTC
                   105       2     +        0.86       TGCCACACAG^TTCAAACTAC
                   400       1     +        0.61       TCCTGCATAG^TGGTAGCAGC
                   409       1     +        0.65       GTGGTAGCAG^CTTATTGCGC
                   633       0     +        0.94       GATTTTTCAG^GCTAAGAAAC
                   787       0     +        0.81       TGATTGATAG^ACGGCTTATC
                   806       1     +        0.54       CACAAAATAG^AAGAGAATCA
                   868       0     +        0.80       ATTCAAACAG^TGCCTATCAC
                  1318       0     +        0.56       CCTTTTTCAG^CCATACCCAT
                  1638       0     +        0.87       AAAAATTCAG^CACACCGGAG
                  2002       1     +        0.95       TATGTTTCAG^ACACCACCGC
++Acceptorの正解／不正解は 373 x, 496 x, 634 o, 923 x, 1319 o, 1639 o, 2003 o
++Donorの正解／不正解は 324 o, 448 o, 590 o, 729 o, 1264 o, 1591 x, 1856 o
    -Acの予測がより困難であることと、Ac/Dnどちらもfalse positivesが報告されることがわかる。

- 課題：うっかりHumanのパラメータで予測させてしまうと、どのくらい違う結果が返ってくるでしょうか？

## Ensmart [#o24349fc]
Martでデータ取得。自分で解析しなくても、解析済みのデータが取得できる場合も多い。十分に活用しよう。<br>
ライフサイエンス統合データベースセンターが発信する動画によるデータベースやウェブツールの使い方コンテンツ置き場（アルファ版）をさっそく活用してみる。<br>
- http://togotv.dbcls.jp/
    -http://togotv.dbcls.jp/20070806.html#p01 <br>
マウスを例に、Ensembl Gene IDに対応するRefseq ID、EntrezGene IDとAffymetrix mouse430 2のIDを対応づける表を作成し、タブ区切りテキストにしてダウンロードしてくる手順を解説

    -http://www.biomart.org/  からstartする

    -http://togotv.dbcls.jp/20070927.html <br>
脂肪細胞のマーカーとして用いられることの多いFABP4(Fatty Acid Binding Protein4)の発現パターン（発現プロファイル、発現プロフィールも同じ）を調べ、それと似た発現パターン（＝脂肪細胞で発現が高い）を持つ遺伝子をリストアップし、それらの遺伝子のゲノム上の上流配列をEnsemblのBioMartを用いて一気に取得する方法を紹介

    -http://togotv.dbcls.jp/swf/070709biomart1.html <br>
Ensemblのbiomartを用いて、特定のGOID（GO:0003700, 転写因子活性）を持つものをヒトの全遺伝子から抽出して数え、それらに対応するAffymetrixとAgilent両方のProbeIDを付してタブ区切りテキストにしてダウンロードする。

    -http://www.biomart.org/  からstartする

    -http://togotv.dbcls.jp/swf/070709biomart2.html <br>
Ensemblのbiomartを用いて、全ての遺伝子の転写開始点から上流の配列1kbをマウスゲノムから抽出してFASTA形式で得る

    -http://www.biomart.org/  からstartする

## Gramenemart (植物) [#e614c5ea]

&color(green){植物のbiomart。同じbiomartシステムを使っていますが、ちょっとバージョンが古く、操作方法がEnsemblと若干違います。};

&color(red){困ったことにIEでは使えないようです。時間があればdemoだけします};

- 手順例: イネ TIGR ver. 4 で GO:0003700 (転写因子活性) が注釈されている遺伝子514本の上流(5'-UTR)1 kbの配列を全部取得したい
++http://www.biomart.org/ を開き、Gramene へのリンクをクリックする
++dataset に Rice gene models (TIGRv4) を選び、nextをクリック
++Filterの画面になるので、欲しいデータセットを指定する (Region, Gene type, Ontologyなど)<br>
ここでは、Gene>Gene type>protein codingをcheck<br>
Gene ontology>Molecular functionにGO:0003700 を入力し、nextをクリック<br>
++Attributeのページになるのでsequenceを選ぶ
++Type of Sequence to ExportでFlank (Gene)をcheck
++Upstream flankをcheckして、長さに1000 (bp)を指定する
++export をクリックすると、514本の転写活性因子と注釈された遺伝子の上流1 kbの配列がまとめ取りできる

- http://www.gramene.org/tutorials/GrameneMart_tutorial.pdf   (資料)

もしある特定の遺伝子群の上流に、何らかの共通のシスエレメントを探したいのなら、こういう方法で上流配列をまとめどりし、それを MEME ( http://meme.sdsc.edu/meme/meme.html ) のEM(期待値最大化)アルゴリズムを用い、上流の塩基配列セットから共通の特徴的な配列パターン (motif) を抽出できないものか、試みるのも良いかもしれません。ま、普通は情報処理だけでそー簡単に結果がでるほど甘くはありませんが、deletion 実験のヒントは得られるかもしれません。

        --
[[AJACS1/講習内容]]へもどる
