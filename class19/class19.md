# Class 19: Cancer Mutation Mini Project
Kiana Bohanon (A17802316)

``` r
library(bio3d)

seqs <- read.fasta("A17802316_mutant_seq.fa")

seqs
```

                   1        .         .         .         .         .         60 
    wt_healthy     MPPRPSSGELWGIHLMPPRILVECLLPNGMIVTLECLREATLITIKHELFKEARKYPLHQ
    mutant_tumor   MPPRPSSGELWGIHLMPPRILVECLLPNGMIVTLECLREATLITIKHELFKEARKYPLHQ
                   ************************************************************ 
                   1        .         .         .         .         .         60 

                  61        .         .         .         .         .         120 
    wt_healthy     LLQDESSYIFVSVTQEAEREEFFDETRRLCDLRLFQPFLKVIEPVGNREEKILNREIGFA
    mutant_tumor   LLQDESSYIFVSVTQEAEREEFFDETRRLCDLRLFQPFLKVIEPVGNREEKILNREIGFA
                   ************************************************************ 
                  61        .         .         .         .         .         120 

                 121        .         .         .         .         .         180 
    wt_healthy     IGMPVCEFDMVKDPEVQDFRRNILNVCKEAVDLRDLNSPHSRAMYVYPPNVESSPELPKH
    mutant_tumor   IGMPVCEFDMVKDPEVQDFRRNILNVCKEAVDLRDLNSPHSRAMYVYPPNVESSPELPKH
                   ************************************************************ 
                 121        .         .         .         .         .         180 

                 181        .         .         .         .         .         240 
    wt_healthy     IYNKLDKGQIIVVIWVIVSPNNDKQKYTLKINHDCVPEQVIAEAIRKKTRSMLLSSEQLK
    mutant_tumor   IYNKLDKGQIIVVIWVIVSPNNDKQKYTLKINHDCVPEQVIAEAIRKKTRSMLLSSEQLK
                   ************************************************************ 
                 181        .         .         .         .         .         240 

                 241        .         .         .         .         .         300 
    wt_healthy     LCVLEYQGKYILKVCGCDEYFLEKYPLSQYKYIRSCIMLGRMPNLMLMAKESLYSQLPMD
    mutant_tumor   LCVLEYQGKYILKVCGCDEYFLEKYPLSQYKYIRSCIMLGRMPNLMLMAKESLYSQLPMD
                   ************************************************************ 
                 241        .         .         .         .         .         300 

                 301        .         .         .         .         .         360 
    wt_healthy     CFTMPSYSRRISTATPYMNGETSTKSLWVINSALRIKILCATYVNVNIRDIDKIYVRTGI
    mutant_tumor   CFTMPSYSRRISTATPYMNGETSTKSLWVINSALRIKILCATYVNVNIRDIDKIYVRTGI
                   ************************************************************ 
                 301        .         .         .         .         .         360 

                 361        .         .         .         .         .         420 
    wt_healthy     YHGGEPLCDNVNTQRVPCSNPRWNEWLNYDIYIPDLPRAARLCLSICSVKGRKGAKEEHC
    mutant_tumor   YHGGEPLCDNVNTQRVPCSNPRWNEWLNYDIYIPDLPRAARLCLSICSVKGRKGAKEEHC
                   ************************************************************ 
                 361        .         .         .         .         .         420 

                 421        .         .         .         .         .         480 
    wt_healthy     PLAWGNINLFDYTDTLVSGKMALNLWPVPHGLEDLLNPIGVTGSNPNKETPCLELEFDWF
    mutant_tumor   PLAWGNINLFDYTDTLVSGKMALNLWPVPHGLEDLLNPIGVTGSNPNKETPCLELEFDWF
                   ************************************************************ 
                 421        .         .         .         .         .         480 

                 481        .         .         .         .         .         540 
    wt_healthy     SSVVKFPDMSVIEEHANWSVSREAGFSYSHAGLSNRLARDNELRENDKEQLKAISTRDPL
    mutant_tumor   SSVVKFPDMSVIEEHANWSVSREAGFSYSHAGLSNRLARDNELRENDKEQLKAISTRDPL
                   ************************************************************ 
                 481        .         .         .         .         .         540 

                 541        .         .         .         .         .         600 
    wt_healthy     SEITEQEKDFLWSHRHYCVTIPEILPKLLLSVKWNSRDEVAQMYCLVKDWPPIKPEQAME
    mutant_tumor   SEITEQEKDFLWSHRHYCVTIPEILPKLLLSVKWNSRDEVAQMVCLVKDEPPIKPRQAME
                   ******************************************* ***** ***** **** 
                 541        .         .         .         .         .         600 

                 601        .         .         .         .         .         660 
    wt_healthy     LLDCNYPDPMVRGFAVRCLEKYLTDDKLSQYLIQLVQVLKYEQYLDNLLVRFLLKKALTN
    mutant_tumor   LLDCNYPDPMVRGFAVRCLEKYYTDDKLSQYLIQLVQVLKYEQYLDNLLVRFLLKKALTN
                   ********************** ************************************* 
                 601        .         .         .         .         .         660 

                 661        .         .         .         .         .         720 
    wt_healthy     QRIGHFFFWHLKSEMHNKTVSQRFGLLLESYCRACGMYLKHLNRQVEAMEKLINLTDILK
    mutant_tumor   QRIGHFFFWHLKSEMHNKTVSQRFGLLLESYCRACGMYLKHLNRQVEAMEKLINLTDILK
                   ************************************************************ 
                 661        .         .         .         .         .         720 

                 721        .         .         .         .         .         780 
    wt_healthy     QEKKDETQKVQMKFLVEQMRRPDFMDALQGFLSPLNPAHQLGNLRLEECRIMSSAKRPLW
    mutant_tumor   QEKKDETQKVQMKFLVEQMRRPDFMDALQGFLSPLNPAHQLGNLRLEECRIMSSAKRPLW
                   ************************************************************ 
                 721        .         .         .         .         .         780 

                 781        .         .         .         .         .         840 
    wt_healthy     LNWENPDIMSELLFQNNEIIFKNGDDLRQDMLTLQIIRIMENIWQNQGLDLRMLPYGCLS
    mutant_tumor   LNWENPDIMSELLFQNNEIIFKNGDDLRQDMLTLQIIRIMENIWQNQGLDLRMLPYGCLS
                   ************************************************************ 
                 781        .         .         .         .         .         840 

                 841        .         .         .         .         .         900 
    wt_healthy     IGDCVGLIEVVRNSHTIMQIQCKGGLKGALQFNSHTLHQWLKDKNKGEIYDAAIDLFTRS
    mutant_tumor   IGDCVGLIEVVRNSHTIMQIQCKGGLKGALQFNSHTLHQWLKDKNKGEIYDAAIDLFTRS
                   ************************************************************ 
                 841        .         .         .         .         .         900 

                 901        .         .         .         .         .         960 
    wt_healthy     CAGYCVATFILGIGDRHNSNIMVKDDGQLFHIDFGHFLDHKKKKFGYKRERVPFVLTQDF
    mutant_tumor   CAGYCVATFILGIGDRHNSNIMVKDDGQLFHIDFGHFLDHKKKKFGYKRERVPFVLTQDF
                   ************************************************************ 
                 901        .         .         .         .         .         960 

                 961        .         .         .         .         .         1020 
    wt_healthy     LIVISKGAQECTKTREFERFQEMCYKAYLAIRQHANLFINLFSMMLGSGMPELQSFDDIA
    mutant_tumor   LIVISKGAQECTKTREFERFQEMCYKAYLAIRQHANLFINLFSMMLGSGMPELQSFDDIA
                   ************************************************************ 
                 961        .         .         .         .         .         1020 

                1021        .         .         .         .       1068 
    wt_healthy     YIRKTLALDKTEQEALEYFMKQMNDAHHGGWTTKMDWIFHTIKQHALN
    mutant_tumor   YIRKTLALDKTEQEALEYFMKQMNDAHHGGWTTKMDWIFHTIKQHALN
                   ************************************************ 
                1021        .         .         .         .       1068 

    Call:
      read.fasta(file = "A17802316_mutant_seq.fa")

    Class:
      fasta

    Alignment dimensions:
      2 sequence rows; 1068 position columns (1068 non-gap, 0 gap) 

    + attr: id, ali, call

We can score residue conservation

``` r
cons <- conserv(seqs)
mutation.sites <- which(cons < 1)

paste(seqs$ali[1, mutation.sites], mutation.sites, seqs$ali[2, mutation.sites])
```

    [1] "Y 584 V" "W 590 E" "E 596 R" "L 623 Y"

``` r
wt <- paste(seqs$ali[1,], collapse="")
wt
```

    [1] "MPPRPSSGELWGIHLMPPRILVECLLPNGMIVTLECLREATLITIKHELFKEARKYPLHQLLQDESSYIFVSVTQEAEREEFFDETRRLCDLRLFQPFLKVIEPVGNREEKILNREIGFAIGMPVCEFDMVKDPEVQDFRRNILNVCKEAVDLRDLNSPHSRAMYVYPPNVESSPELPKHIYNKLDKGQIIVVIWVIVSPNNDKQKYTLKINHDCVPEQVIAEAIRKKTRSMLLSSEQLKLCVLEYQGKYILKVCGCDEYFLEKYPLSQYKYIRSCIMLGRMPNLMLMAKESLYSQLPMDCFTMPSYSRRISTATPYMNGETSTKSLWVINSALRIKILCATYVNVNIRDIDKIYVRTGIYHGGEPLCDNVNTQRVPCSNPRWNEWLNYDIYIPDLPRAARLCLSICSVKGRKGAKEEHCPLAWGNINLFDYTDTLVSGKMALNLWPVPHGLEDLLNPIGVTGSNPNKETPCLELEFDWFSSVVKFPDMSVIEEHANWSVSREAGFSYSHAGLSNRLARDNELRENDKEQLKAISTRDPLSEITEQEKDFLWSHRHYCVTIPEILPKLLLSVKWNSRDEVAQMYCLVKDWPPIKPEQAMELLDCNYPDPMVRGFAVRCLEKYLTDDKLSQYLIQLVQVLKYEQYLDNLLVRFLLKKALTNQRIGHFFFWHLKSEMHNKTVSQRFGLLLESYCRACGMYLKHLNRQVEAMEKLINLTDILKQEKKDETQKVQMKFLVEQMRRPDFMDALQGFLSPLNPAHQLGNLRLEECRIMSSAKRPLWLNWENPDIMSELLFQNNEIIFKNGDDLRQDMLTLQIIRIMENIWQNQGLDLRMLPYGCLSIGDCVGLIEVVRNSHTIMQIQCKGGLKGALQFNSHTLHQWLKDKNKGEIYDAAIDLFTRSCAGYCVATFILGIGDRHNSNIMVKDDGQLFHIDFGHFLDHKKKKFGYKRERVPFVLTQDFLIVISKGAQECTKTREFERFQEMCYKAYLAIRQHANLFINLFSMMLGSGMPELQSFDDIAYIRKTLALDKTEQEALEYFMKQMNDAHHGGWTTKMDWIFHTIKQHALN"

``` r
cat(seqs$ali[1,])
```

    M P P R P S S G E L W G I H L M P P R I L V E C L L P N G M I V T L E C L R E A T L I T I K H E L F K E A R K Y P L H Q L L Q D E S S Y I F V S V T Q E A E R E E F F D E T R R L C D L R L F Q P F L K V I E P V G N R E E K I L N R E I G F A I G M P V C E F D M V K D P E V Q D F R R N I L N V C K E A V D L R D L N S P H S R A M Y V Y P P N V E S S P E L P K H I Y N K L D K G Q I I V V I W V I V S P N N D K Q K Y T L K I N H D C V P E Q V I A E A I R K K T R S M L L S S E Q L K L C V L E Y Q G K Y I L K V C G C D E Y F L E K Y P L S Q Y K Y I R S C I M L G R M P N L M L M A K E S L Y S Q L P M D C F T M P S Y S R R I S T A T P Y M N G E T S T K S L W V I N S A L R I K I L C A T Y V N V N I R D I D K I Y V R T G I Y H G G E P L C D N V N T Q R V P C S N P R W N E W L N Y D I Y I P D L P R A A R L C L S I C S V K G R K G A K E E H C P L A W G N I N L F D Y T D T L V S G K M A L N L W P V P H G L E D L L N P I G V T G S N P N K E T P C L E L E F D W F S S V V K F P D M S V I E E H A N W S V S R E A G F S Y S H A G L S N R L A R D N E L R E N D K E Q L K A I S T R D P L S E I T E Q E K D F L W S H R H Y C V T I P E I L P K L L L S V K W N S R D E V A Q M Y C L V K D W P P I K P E Q A M E L L D C N Y P D P M V R G F A V R C L E K Y L T D D K L S Q Y L I Q L V Q V L K Y E Q Y L D N L L V R F L L K K A L T N Q R I G H F F F W H L K S E M H N K T V S Q R F G L L L E S Y C R A C G M Y L K H L N R Q V E A M E K L I N L T D I L K Q E K K D E T Q K V Q M K F L V E Q M R R P D F M D A L Q G F L S P L N P A H Q L G N L R L E E C R I M S S A K R P L W L N W E N P D I M S E L L F Q N N E I I F K N G D D L R Q D M L T L Q I I R I M E N I W Q N Q G L D L R M L P Y G C L S I G D C V G L I E V V R N S H T I M Q I Q C K G G L K G A L Q F N S H T L H Q W L K D K N K G E I Y D A A I D L F T R S C A G Y C V A T F I L G I G D R H N S N I M V K D D G Q L F H I D F G H F L D H K K K K F G Y K R E R V P F V L T Q D F L I V I S K G A Q E C T K T R E F E R F Q E M C Y K A Y L A I R Q H A N L F I N L F S M M L G S G M P E L Q S F D D I A Y I R K T L A L D K T E Q E A L E Y F M K Q M N D A H H G G W T T K M D W I F H T I K Q H A L N
