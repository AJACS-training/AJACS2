[[AJACS1/講習内容]]へもどる

        --
目次

#contents
        --


# 遺伝子機能予測とDB高度化 [#l768f77a]

## 遺伝子の機能を知るためには [#a1ac7aeb]
機能が「本当の意味で」判明している遺伝子は驚くほど少ない。
## 実験で知る・推し量る [#wd90f3d8]
- 酵素活性をはかる
    -遺伝子(DNA)→転写→RNA→翻訳→タンパク質
    -タンパク質をとり、どんな酵素活性をもつのか調べる
- 逆遺伝学
    -古典的遺伝学　形態や現象から遺伝子へ
    -逆遺伝学　遺伝子から形態や現象へ＝遺伝子を「潰す」
- 転写産物の動態を観察する

## 類推する方法は？ [#yc731f6d]
- 配列の類似
    -配列が似ていれば機能も似ている（多分）
    -類似の類似の類似の類似は類似ではないかもしれない
        -「相同 (homology) 人の手＝猫の足＝鳥の羽
        -「相似」(similarity) コウモリと鳥の羽、パンダの親指
    -部分一致している部分は機能と関わらないかもしれない
    -機能とかかわらない領域の部分的な一致が非常に危険

- 「嘘類似」の問題回避法
+配列類似検索の対象は、信頼できるライブラリから順に使う~
    -UniprotKB/Swissprot: http://www.ebi.ac.uk/swissprot/
    -UniprotKB/TrEMBL: http://www.ebi.ac.uk/trembl/
    -NCBI nr: http://www.ncbi.nlm.nih.gov/Education/blasttutorial.html  (description)
+配列類似検索以外の機能予測方法を用いる~
機能に関わるタンパク質の部分配列~
//--モチーフ
//--ドメイン
//--【実習】TAIR にアクセスして「根拠」を知ろう
//--部分配列の保存を見いだす
//[[図：アミノ酸アラインメントと保存領域:http://charles.kazusa.or.jp/~yn/jp/lecture/tmu2007/images/B6.jpg]]~
    -機能に関わるタンパク質の''部分''配列（モチーフやドメイン）
    -Interpro: さまざまなタンパク質機能探索のための統合データベース~
http://www.ebi.ac.uk/interpro
+注釈の「根拠 (evidence)」が明示できる方法で注釈する~
機能アノテーションの「根拠」を記載する方法が提唱されている~
    -see: http://www.geneontology.org/ -> Documentation -> Evidence Code Guide <br>
        -IDA (Inferred from Direct Assay)
        -TAS (traceable author statement)
        -IEA (Inferred from Electronic Annotation)
        -ISS (Inferred from Sequence or Structural similarity) etc.

# 【実習】Interpro・GO・[[CyanoGenes:http://bacteria.kazusa.or.jp/cyanobase/Synechocystis/comments/]]・[[KazusaAnnotation:http://a.kazusa.or.jp]] [#m682fceb]

## Interproscan [#pae0a7cf]

&color(green){モチーフ、プロファイル検索のまとめがけ、Gene Ontrogyにまで到達可能な優れたアミノ酸配列解析総合サイト};

+googleの検索窓に「interproscan」と入れて、googleで探し出す ( http://www.ebi.ac.uk/InterProScan/ )
- Enter or Paste a PROTEIN Sequence in any formatに以下の配列をコピペする (ctl-C then ctl-V)
 >opsin Rh2(Drosophila melanogaster)
 MERSHLPETPFDLAHSGPRFQAQSSGNGSVLDNVLPDMAHLVNPYWSRFAPMDPMMSKIL
 GLFTLAIMIISCCGNGVVVYIFGGTKSLRTPANLLVLNLAFSDFCMMASQSPVMIINFYY
 ETWVLGPLWCDIYAGCGSLFGCVSIWSMCMIAFDRYNVIVKGINGTPMTIKTSIMKILFI
 WMMAVFWTVMPLIGWSAYVPEGNLTACSIDYMTRMWNPRSYLITYSLFVYYTPLFLICYS
 YWFIIAAVAAHEKAMREQAKKMNVKSLRSSEDCDKSAEGKLAKVALTTISLWFMAWTPYL
 VICYFGLFKIDGLTPLTTIWGATFAKTSAVYNPIVYGISHPKYRIVLKEKCPMCVFGNTD
 EPKPDAPASDTETTSEADSKA
+Submit Job をクリックしてジョブをスタート
+グラフィクス表示とTable表示の両方でこの配列がもつモチーフ・プロファイルを確認

- 【発展】どのようなプログラムが使われているのか？それぞれの詳細について調査し理解しましょう

## GO [#ga9671d6]

&color(green){遺伝子機能注釈のための生物共通語彙を提供。evidence が明記されているのはすばらしい};

- http://www.geneontology.org
++DNA bindingで検索
++CCA1, CIRCADIAN CLOCK ASSOCIATED 1 をクリックして遺伝子の詳細を見る 【evidence codeに注意】
++circadian rhythm (GO:0007623) をクリックしてGOの詳細を見る
++Term Lineageのcircadian rhythmの数字の部分をクリックして、タームに関連する遺伝子のリストを表示する【ここでも、それぞれのevidence codeに着目】
++Evidence CodeをIDA (Inferrd from Direct Assay) に限定するfilterをかけてみる。speciesをA. thalianaに限定してみるなどの操作を行ってみる。IDA, TASなど、複数のEvidence codeを反転させたいときは、Macならcommand key+クリック, windowsの場合はCtrl+クリック。

## [[CyanoGenes:http://bacteria.kazusa.or.jp/cyanobase/Synechocystis/comments/]] [#ta4b5d4c]

&color(green){シアノバクテリアの遺伝子単位のコメント受付。オープンアノテーションの最初期の試み};

- http://www.kazusa.or.jp/cyanobase/Synechocystis/comments/

## [[KazusaAnnotation:http://a.kazusa.or.jp]] [#t1c75a37]

&color(green){統合DBプロジェクトにおける、オープンアノテーションへの挑戦。現在進行形};

- http://a.kazusa.or.jp


//**ExPASy [#vfb081e5]
//&color(green){proteomics に関係したオリジナルツール＆他サイトへのリンクが豊富};
//-http://www.expasy.org/ <br>
//The ExPASy (Expert Protein Analysis System) proteomics server of the Swiss Institute of Bioinformatics (SIB) is dedicated to the analysis of protein sequences and structures as well as 2-D PAGE <br>
//--タンパク質の同定 (peptide mass fingerprint, pI, MW etc.): Aldente, TagIdent, MultiIdent, AACompIdent
//--翻訳後修飾や切断部位の推定: Findmod, FindPept, GlycoMod <br>
//などなど、多数のツールを提供。

        --
[[AJACS1/講習内容]]へもどる
