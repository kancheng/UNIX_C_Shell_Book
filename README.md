# UNIX_C_Shell_Book

## 整理者序

自己最早接觸 Linux 是在 2015 年龍華資訊管理系選修 Linux 系統管理與實作的課程，同時也成為了該課堂的學生助教，該課的授課教師後來也是筆者自己直升龍華資訊管理碩士的導師。

當時為了磨練能力，翻閱鳥哥 (Vbird) 的書籍與網站，當時發現鳥哥將此站整站備份，因為是助教之故，利用當下的空檔時間進行整理。存放至龍華科技大學的 Google Driver 上。當時自己還並不會 Git 版本控制，寫程式的能力也並不理想。

2022 年後再回首，自己經歷過龍華資訊管理碩士的資料分析，一年的義務役士官教育班長，兩年在留學顧問公司的資訊部門的前後端開發、申請上北京大學信息工程學院等經歷。自己或許算是可以好好面對自己能力。

藉著 Google Driver 雲端政策的改變，自己再度整理成 Markdown，並找出相對應的說明，而由自己補充的連結則會在該章以 `*KH` 後面編號來做標記，重新放在 GitHub 上。

干皓丞 2022/3/15 於北京大學深圳研究生院


## Mirror 備份

http://mirror.sars.tw/UNIX_C_Shell/


## UNIX C Shell

網路農夫 黃天彥 著


## 種田人的話

這份文件記錄了我一部份學習 UNIX OS 所得的些許微不足道的個人經驗。所以本文的水平稱不上是一份專業、嚴謹的作品。如有網友發現本文有任何的謬誤，請務必來信指證錯誤所在，以免效果適
得其反。

本份文件由於筆者的慵懶，所以尚未完成的部分，建構的速度慢的離奇。文中的第二、三、四篇是在五年多以前完成的，第一篇則經過幾度的重寫，至今尚在陸續搜尋資料完成中...至於第五篇，總覺得用的上的機會已經不大...第六篇，實際上也是草稿份量最大的一個部分，但總覺得撰寫 Shell Script 不應該在使用 C shell，所以至今尚未發表過，這大致上就是這份文件的過往與現況。至於本人由於工作性質的轉變，幾乎已經不再使用 UNIX OS，手上的幾台 SUN 工作站也早已經塵封多時，所以文件的進度也等於停擺了。

儘管如此，我還是會利用空閒的空閒之餘，讓本文能有個告一段落的完整性的。至少我是如此地期許自己。當然，我更期望能在網路上看見我同文同種的同胞能有更多無私的心得交流。
即使今日....

我已接受這世界的現實...
但我卻尚未捨棄心中的理想...

因為

虛幻是存在的.

網路農夫-黃天彥 2001/04/12

> Copyright ©2000 
> 本文作者允許任何人以各種方式自由拷貝傳播本文之部份或全部内容,唯上述之行為均不得涉及商業利益,且本版權明必須存在每份拷貝之中。
> 其他未及詳述之版標明以自由軟體基金會(FreSoftware Foundation)之 GPL (General Public License) 為依循根據
>
> 黄天彥


## 目錄

I.緣起-一場浮士德的交易

第一篇 UNIX 系統簡介

1-1 UNIX 簡史

1-1-1 先前的一個理想

1-1-2 一個遊戲的開始

1-1-3 初期的自由發展

1-1-4 走出貝爾實驗室

1-1-5 一個穩定的基石

1-1-6 一個重要的延續與發展 -- BSD UNIX

1-1-7 UNIX 與 DARPA 交會

1-1-8 商業化的不平坦歷程 -- UNIX 版本的戰爭

1-1-09 讓 UNIX 自由 -- Networking Release 2

1-1-10 誰是"老大哥" -- 版權訴訟

1-1-11 GNU 計劃 -- 開啟了新大道

第二篇 認識 SHELL

2-1 SHELL 是什麼？

2-2 三個主要的 SHELL

2-3 C SHELL 的運用面

第三篇 C SHELL 的基本運用

3-1 在 C SHELL 下 的指令運用

3-2 輸入 / 輸出重導向

3-3 檔名擴展的運用

3-4 管線的觀念與運用

3-5 History 的設定與運用

3-6 別名的設定與運用

3-7 工作控制的運用

3-7-1 前景工作（foreground jobs）

3-7-2 背景工作（background jobs）

3-7-3 背景工作的控制管理

3-7-4 關於背景工作使用的注意事項

3-8 C SHELL 的內建指令

3-8-1 umask 指令

3-8-2 exit 指令

3-8-3 source 指令

3-8-4 limit, unlimit 指令

3-8-5 dirs 指令

3-8-6 echo 指令

3-8-7 time 指令

3-8-8 nice 指令

3-8-9 rehash, unhash, hashstat 指令

3-8-10 exec 指令

3-8-11 eval 指令

3-8-12 repeat 指令

3-8-13 pushd, popd 指令

3-9 引號的運用與指令的關係

3-9-1 單引號（ ' ）的運用（single-quotes）

3-9-2 雙引號（ " ）的運用（double-quotes）

3-9-3 倒引號（ \` ）的運用（backquote）

3-9-4 倒斜線“ \ ”的運用（backslash）

第四篇 C SHELL 變數的整體介紹

4-1 環境變數的設定影響（Environment Variables）

4-1-1 PATH 環境變數

4-1-2 環境變數 HOME 與預設變數 home

4-1-3 環境變數 SHELL 與預設變數 shell

4-1-4 LOGNAME 與 USER 環境變數

4-1-5 環境變數 MAIL 與預設變數 mail

4-1-6 EXINIT 環境變數

4-1-7 TERM 環境變數

4-2 預設變數的設定影響 （Predefined Variables）

4-2-1 path 指令搜尋路徑變數

4-2-2 cdpath 改變工作目錄搜尋路徑變數

4-2-3 prompt 提詞變數

4-2-4 history 儲存指令使用記錄變數

4-2-5 histchars 指令使用記錄之特殊符號變數

4-2-6 savehist 指令使用記錄檔案儲存變數

4-2-7 time 執行時間變數

4-2-8 echo 與 verbose 指令顯示變數

4-2-9 status 執行狀態變數

4-2-10 cwd 目前工作目錄變數

4-2-11 hardpaths 實體路徑變數

4-2-12 ignoreeof 忽略使用 eof 退出變數

4-2-13 noclobber 禁止覆寫變數

4-2-14 noglob 變數

4-2-15 nonomatch 變數

4-2-16 notify 變數

4-2-17 filec 檔名自動續接變數

4-2-18 fignore 變數

4-2-19 nobeep 不准叫變數

第五篇 製定 C SHELL 的使用環境

5-1 login 的型態與起始檔案讀取的關係

參考資料

## I.緣起-一場浮士德的交易

I went to the woods because I wished to live deliberately,
to front only the essential facts of life,
and see if I could not learn what it had to teach,
and not,
when I came to die,
discover that I had not lived.

Henry David Thoreau1817-1862
Walden [1854] ,†2, Where I Lived, and What I Lived For

這是梭羅在他的著作"湖濱散記"裡一段令我相當心折的文句，也是觸使我開始寫這份文件的理由。

記得剛接觸 UNIX 時，我連目錄（directory）是什麼都搞不清楚，由於工作上的需要，開始努力一點一滴地去學習當時我認為是巨大怪物的 UNIX Operation System。慢慢地，她變成了在工作中最吸引我的一部份。

到如今，我還記得第一次接觸 UNIX 那整夜慘痛的經驗，當時我是一個 IC Layout 工程師，那一天下班後，一個人逛到書店買了這輩子第一本關於電腦的書，又一個人回到已經沒有人
的辦公室坐在 SUN workstation 前面，一面看著有看但實在是沒有懂的 vi 篇，開始編輯我在 UNIX OS 上的第一個檔案，幾個小時過去，當檔案確定編輯完成後，我滿足地在空無一人的辦公室
內，燃起一根紙煙。看著隨著生命的氣息所散布在空中的白色煙霧，感覺自己似乎已經完成了一件了不起的事。當抽完一根再燃上一根回到電腦前時，我呆了…… 那一夜沒有睡覺的我置身在白色的生
命煙霧中。也於是乎開始了一場我與魔鬼的交易。


## 1-1 UNIX 簡史

## 1-1-1 先前的一個理想

UNIX 系統自 1969 年 Ken ThompsonKen Thompson 與 Dennis RitchieDennis Ritchie 在美國貝爾電話實驗室（Bell Telephone Laboratories）發展出雛形至今，已歷經近 30 年。而 "UNIX" 這個字典上查不到其原意的怪字，其實是戲謔 MULTICS（MULTiplexed Information and Computing System）作業系統的大而無當所產生的諧音字。

在 1957 年 10 月，前蘇聯發射了第一枚人造衛星，此舉讓當時的美國總統艾森豪決定投下巨額的經費用以支援及發展科學，美國高等研究計劃署(ARPA, Advanced Research Projects Agency)便是在這個時空下設立了，該單位負責推動系統發展等相關計畫，成為當時美國電子計算機發展的重要推手。

J.C.R. Licklider1960 年代是大型電腦的發展年代，當時的麻省理工學院因最先實現了相容分時系統 (CTSS, Compatible Time-Sharing System)，在電子計算機領域享有相當崇高的地位。

1963 年，麻省理工的里克萊德 (J. C. R. Licklider, 1915 - 1990) 推動了 MAC 計畫，MAC 以 IBM 的大型電腦做為主體，連接了將近 160 台終端機，這些終端機就四散在學區以及教職員的家中，可讓 30 位使用者同時共享電腦的資源。


這項計畫到了 1965 年便不堪負荷，於是麻省理工便決定開發更大型的分時電腦系統。新的計畫便是 -- MULTICS，一個電腦史上最為龐大的分時電腦系統，企圖連接 1000 部終端機，支援 300 的使用者同時上線的分時電腦系統。她面臨的是，作業系統的分時觀念還在各學術與研究機構中探索成形，電腦硬體亦需重新設計修改的雙重挑戰。

當時麻省理工原本想找 IBM 配合這項計畫，但 IBM 正忙著應付自己的問題而無意配合 MULTICS 計畫。此時，通用電子公司（General Electric Company）也就是奇異公司正好在發展自己的大型主機，見機不可失，便極力邀請麻省理工參予她們的 GE 645 大型主機的規格制定。有了奇異熱心主動的電腦硬體配合，麻省理工找上的不能販售電腦卻人才濟濟的貝爾電話實驗室來負責承包軟體工程。於是乎，MULTICS 的計畫便在 1965 年由麻省理工學院、奇異公司及貝爾電話實驗室這三個成員開始共同發展。

1969 年，MULTICS 計畫在歷經四年的奮戰後，仍舊未達到原先規劃設計的理想，貝爾電話實驗室決定退出計畫。

功能不足的 MULTICS 還是安裝在奇異公司的 GE 645 大型電腦上供麻省理工使用。奇異公司在該計畫草草結束後不到一年的便完全淡出的大型電腦的市場。日後失敗的 MULTICS 計畫，被嘲解為 Many Unnecessarily Large Table In Core Simultaneously。

農夫我個人認為， MULTICS 計畫誕生在大型電腦將開始鼎沸的 1965 年，夭折於大型電腦最為輝煌的 1969 年。她如果適時在 1960 年代末期成功的話，絕對可以助長當時已經普遍被電腦權威人
士視為理想的『電腦公用事業』，至少可以讓大型電腦的發展與資源集中的應用模式就不至於會在 1970 年代初期就迅速萎縮。

因為 MULTICS 計畫如果成功，至少能讓當時的大型電腦的應用規模大上 10 倍左右。然而，MULTICS 計畫失敗了。她嚴重地打擊了當時依賴大型電腦主機的電腦公用事業業者在發展上的信心。更由於沒有相似的計劃後繼進行，使得集中式的大型電腦主機沒有明顯的使用效能提昇，而加速催化計算機工業的轉變，以尋找新的道路。另一方面，MULTICS 計畫失敗的經驗亦讓當時參與該計畫的軟體工程師們得到相當寶貴的經驗與正面的影響。幾年後，MULTICS 計畫這個不同凡響的失敗換來的一個不同凡響的成功。一個嘲笑她的名字誕生了 - UNIX。

## 1-1-2 一個遊戲的開始

PDP-71969 年貝爾實驗室的計算機科學研究中心（Computing Science Research Center）成員退出 MULTICS 計畫的同時，貝爾實驗室本身其實也沒有一套完善便利的交談式計算機服務環境。
在其中不少工程師們也正為了改善程式設計環境努力著， Ken Thompson、Dennis Ritchie 和其同事們在當時草擬一個新的檔案系統架構，這個檔案系統也就是早期的 UNIX 作業系統的檔案系統的前身。

當時的 Ken Thompson 忙著使用 Fortran 語言將原本在 Multics 系統中開發的 game 叫 "Space Travel"（太空旅遊）轉移到 GECOS System 上開發。當時 GECOS System 大型電腦
的 CPU Time 相當昂貴（一秒要 75 塊美金），同時控制 "spaceship"（太空船）的效果不甚理想，於是 Ken Thompson 不得不尋找替代的開發環境。Thompson 看上了一台很少被人使用的
Digital Equipment Corporation PDP-7 迷你電腦，當時 PDP-7 使用的是 Graphic-II 顯示器，具有不錯的圖形處理能力。Brian kernighan 於是 Ken Thompson 便與 Dennis Ritchie 聯手將程式設計轉移到 PDP-7 型電腦上。 

Ken Thompson 在移轉工作環境的同時為了得到較好的發展環境，便與 Dennis Ritchie 共同動手設計一套包含 File System、Process Subsystem 及一小組
Utility 的作業系統，當時這套系統僅能支援 2 個使用者使用。由於貝爾實驗室對於 MULTICS 計畫失敗的陰霾還未消散， Brian Kernighan 這位仁兄開玩笑地戲稱這套新的作業系統為
UNiplexed Information and Computing System，縮寫為 UNICS，之後大家取諧音便叫她為 "UNIX"，沒想到這個開玩笑的名字會被人叫到今天。

## 1-1-3 初期的自由發展

事實上該套 "UNIX" 系統在當時僅是私下的被使用，也並沒有得到多大的重視，一直到 1971 年的一個正式的計畫，UNIX 才正式被搬上台面。

1970 年，當時貝爾實驗室的專利部門（Patent department）缺乏一套文書處理系統，為了設計開發的需要，於是買了一台 PDP-11 電腦。當時 PDP-11 電腦的交機過程並不順利，處理器先到，硬碟則是等了好幾個月。

當 PDP-11 一切準備妥當後，他們便將 UNIX 移植到擁有 512K bytes 硬碟的 PDP-11/20PDP-11/20 型電腦上，並在此系統之下開發了一套文書處理工具。而這套工具便是後來 nroff / troff 的前身。那時的 UNIX 提供 16K bytes 給系統、8K bytes 給使用程式，檔案最大的極限是 64K bytes。

而此套含有文書處理工具的系統，也正式獲得貝爾實驗室的專利部門採用，系統名稱並被編為 "First Edition"。在 UNIX 移植成功後 Thompson 用 B 語言為它添加了 Fortran Compiler，但因為 B 語言屬於一種解譯語言（interpretive language），執行成效並不是很好，於是 Ritchie 又將它 -- Compiler 發展成可產生機器碼、允許定義資料形態及結構，Ritchie 稱它為 C 語言。

1973 年並以 C 語言改寫全部 UNIX 原始程式，UNIX 於是首度出現正式版本--第五版。

此時的 UNIX 慢慢地在貝爾實驗室內部蔓延開來，裝機數也變成了 25 部之多。由於當時的貝爾實驗室實際上是掌控在美國電信電話公司（AT&T）及其子公司西方電器公司的手上，實驗室主要是負
責研究改進西方電器公司製造的和美國電信電話公司在貝爾系統中使用的電信設備。

同時根據軍方合同，從事與國防有關的研究與改進的工作。而 AT&T 本身由於有反托拉斯法的限制並不能從事於任何有關電腦方面的銷售，所以 AT&T 的主管階層們對於當時 UNIX 的發展並沒有太多的支持，因而當時貝爾實驗室內部對於 UNIX 的發展並不是相當在意也無意於將之推廣。

不過為了應付實驗室內各部門日益增加的 UNIX 使用以及 UNIX 的技術支援需求，還是成立了 UNIX System Group（簡稱 USG）。不過該組織也僅只是提供技術上的支援，並未賦予繼續發展的任務。所以當時的 UNIX 發展，全靠 AT&T 的工程師們的努力。這段期間 UNIX 的發展完全沒有組織及系統性可言，而玩家盡是一些工程師們，於是乎種下了 UNIX 日後較難以被一般人所接受的命運。


## 1-1-4 走出貝爾實驗室

1974 年 Thompson 與 Ritchie 共同在 Communications of the ACM 發表了一篇 UNIX 論文 "UNIX Time-Sharing System" 得到相當大的迴響。 

1975 年 UNIX 發表第六版（V6）﹐其提供的強大功能更勝過當時昂貴大電腦的作業系統，其最大特點是以高階語言寫成，僅需要做少部份程式的修改便可移植到不同的電腦平台上。

UNIX V6 版本並附有完整的程式原始碼在 1976 年正式從貝爾實驗室內部傳播到各大學及研究機構，UC Berkeley 也就是依據這個版本開始研究並加以發展，並在 1977 年發表 1 BSD（1st Berkeley Software Distribution）版本的 UNIX OS，其後續的發展更為 UNIX OS 貢獻良多且影響深遠，此點稍後再為你說明。

同年 UNIX 因它提供良好程式發展環境、網路傳輸服務與及時服務 (Real-Time Services)，而廣得各電話公司採用。Interactive System Corporation 更因 Value Added Reseller (VAR) 運用 UNIX 來強化辦公室自動化環境，成為第一家應用 UNIX 作業系統的公司。

此年 UNIX 亦被修改並第一次裝到 Interdata 8/32 型電腦上。這也是 UNIX 作業系統首次安裝在非 PDP 型的電腦上。自此 UNIX 系統開始被移植改裝到各型微處理機及新電腦上。

## 1-1-5 一個穩定的基石

1978 年 UNIX 發表對今日影響最重大的 UNIX 第七版（UNIX Time-Sharing System，Seventh Edition）也就是 V7。

此版本包含 Fortran 77 compiler、Shell（只有 Bourne Shell）、文件處理工具（nroff/troff、roff、MS mocro 等）、UNIX-to-UNIX-file-Copy（用來支援兩台 UNIX 機器間的檔案傳輸）、資料處理工具（AWK、SED 等強悍的工具）、除錯工具（ADB）、程式發展工具（MAKE）、Lexical analyzer generator（LEX、YACC 等）、簡單的繪圖工具、並支援 C 語言及 LINT verifier，主要執行於 PDP-11 及 Interdata 8/32 型電腦上。

在當時那個年代來說其系統的架構與功能已經是相當的完備的了。Bourne Shell 的原作者稱她為 "improvement over all preceding and following Unices"，在今日也有人稱這個版本是 "last true Unix"。由此可見 V7 在 UNIX 發展里程上的扮演了相當重要的磐石角色。

當農夫我還在聯華電子工作時，王林正同事是我工作上的導師兼撞球球友。在他出國留學前送我一本 V7 的使用手冊。這本書對我的幫助很大。雖已事隔多年，但指導之恩永生難忘。在此表示對王林正
前輩的由衷感謝。

事實上，V7 的使用手冊分成兩個部分，Volume 1 中有一篇簡短的系統簡介以及所有指令的使用說明。Volume 2 則是比較深入的單元介紹，此部份原本分為 2a, 2b 兩部份，儒林出版社發行時則將之合併為一冊。我手上有的便是這一本手冊。

前些日子，我在網路上閒逛，意外地在 Bell Laboratories 發現了 V7 的使用手冊。總算宿願得償，看到了 Volume 1。我個人認為，V7 的使用手冊，事實上寫得相當好，比起市面上某些書籍介紹的還要完整。有心學好 UNIX 的人，最好能花點時間看看 Volume 2 的部份，該份文件您可以在到以下的網址找到。

http://plan9.bell-labs.com/7thEdMan/bswv7.html

在當時 DEC 公司推出了一款 32-bit supermini 主機 -- VAX，搭配的 VAX 的作業系統叫做 VMS。

這款迷你級電腦的硬體無可挑剔〈直到今日她的穩定度仍是被諸多老一輩的系統管理者所讚許的〉，但 DEC 對 VMS 作業系統的支援性卻讓貝爾實驗室的工程師們寧願使用 UNIX OS 。而這項工作則是由 John Reiser 和 Tom London 所共同完成。他們以 V7 為基礎轉移 UNIX OS 到 VAX 電腦上使用。這個版本被稱為 UNIX V32。同時為了轉移的方便性，他們把 32-bit 的 VAX 當成是大一點的 PDP-11(因為 DEC 的 PDF-11 型電腦是 16-bit)，同時為了執行的效率，V32 放棄使用 VAX 硬體提供的一項 paging 功能(DEC 的 VMS OS 有支援 paging 功能，也由於 V32 捨棄這項功能，所以 V32 沒有虛擬記憶體的功能)。即使是如此，V32 支援的位址已高達 4Gb。就這樣沒有支援 paging 功能的 V32 開始被廣泛的安裝在 VAX 的機器上運作。

DEC 則是在 1984 年左右推出來自己的 UNIX OS，叫做 ULTRIX。


`*KH` :

1. https://no.wikipedia.org/wiki/UNIX_versjon_7


## 1-1-6 一個重要的延續及發展 -- BSD UNIX

時間回到 1973 年 11 月， Ken Thompson 和 Dennis Ritchie 在印第安那 Purdue 大學的一場作業系統原理的座談會。會場上、坐著一位柏克萊大學（U.C. Berkeley）教授，名字叫 Bob Fabry。

當天的 K&R 所發表的 UNIX 立刻引發 Bob Fabry 的極度興趣。當時的柏克萊還是處在使用大型電腦主機、批次執行程式的階段，並沒有像 UNIX 這樣的交談式作業環境。會後，他便決定將 UNIX
帶回柏克萊。

於是柏克萊的計算機科學、數學與統計三個系所合買的一台 PDP-11/45，準備用來迎接 UNIX。

1974 年 1 月，Bell Labs 寄來了一捲 V4 的磁帶，學生 Keith Standiford 便開始進行安裝 V4 的工作。安裝時 Standiford 碰到了問題，便轉向 Bell Labs 求援。人在新澤西州的 Thompson 便透過柏克萊這端速度只有 300-baud 的數據機在線上進行偵錯。

在 UNIX 的發展史上，這是 Bell Labs 與 柏克萊的第一次接觸。完成除錯後，V4 便順利地在柏克萊這台新買的 PDP-11/45 電腦上工作了。當時這台是三個系所合買的，計算機科學好不容易裝上了 UNIX，卻碰到數學與統計系所要使用 DEC's RSTS system，所以在一陣協調後，UNIX 與 DEC's RSTS system 以 8:16 小時的比例分配，供三個系所輪流使用。

一段時日後，具交談式功能的 UNIX 在效能上的表現得到絕多數學生們喜愛，紛紛將自己的計畫轉向 UNIX 的時段。而一天佔了 16 個小時的批次處理時段卻乏人問津。當時 Eugene Wong 與 Michael Stonebraker 教授，看上了 UNIX 提供的便利性，便打算將他們的 INGRES 資料庫計畫重原先批次處理的電腦環境轉移到 UNIX 系統上面。在 1974 年，他們為這執行計畫添購了一台新的 PDP-11/40 電腦，上面安裝了 V5。

這個計畫也就是柏克萊的第一個將作業環境轉移到 UNIX 的案子。UNIX 作業環境的需求，在柏克萊迅速地成長。為了應付需求，Michael Stonebraker 與 Bob Fabry 教授決定再申請購買兩台 PDP-11/45。1975 年初，DEC 推出 PDP--11/70，價格差不多等於兩台 PDP-11/45，但功能強過 PDP-11/45，所以他們便決定改
購買一台 PDP-11/70。

這台機器引來了 Ken Thompson、碰上 Bill Joy 以及日後產生了 1BSD。她就宛如是一塊 UNIX 史上的地標，沿襲自 Bell Labs，豎立在伯克萊，承先啟後並開創新局。農夫個人認為，她應該被供
在博物館。

當這台機器在 1975 年終運達伯克萊時；同一時間，Thompson 受邀回母校(柏克萊)當客座教授，科目就是 UNIX。Thompson 在校期間與 Jeff Schriebman 和 Bob Kridle 一起動手將新版的 V6 安裝在 PDP--11/70。

Bill Joy

1975 年，一位密西根州大學的畢業生來到了伯克萊，他的名字就是 Bill Joy。當時 Joy 和同學 Chuck Haley (tar 就是他寫的)喜歡一起泡在電腦房裡面，Thompson 也時常插上一腳。他們
不但改善了 Pascal 的解譯能力，也提高了 Pascal 的偵錯能力加快解譯與執行的速度。另外換裝上 ADM-3 的螢幕後，他們覺得 ed 文字編輯指令並不合用；於是根據另外一個相似的 em 指令，發展了自己的覺得滿意的文字編輯工具，也就是指令 ex。

1976 年夏天，Thompson 結束了他的休假回到 Bell Labs。此時的 Joy 和 Haley 已經開始著手探索 UNIX kernal，甚至還做了一些修改。1977 年初，Joy 製作了一捲磁帶，上頭寫著 "Berkeley Software Distribution."，這就是 1BSD。其中包含新的 Pascal compiler 與 ex 編輯器。

次年，來了幾台新螢幕 -- ADM-3a，這種螢幕支援游標位址顯示，Joy 在這種螢幕上完成了有人愛不釋手；有人恨之入骨的文字編輯器 -- vi。

接著不久，Joy 便發現一個問題，老舊的螢幕裝備，還是會被用在其他的電腦上。為了支援上的方便，Joy 針對此現象設計了一個介面，用來管理、支援不同的螢幕裝備。這個介面就是現在的 termcap。1978 年中，包含了功能加強的 Pascal 與 vi 及 termcap 的 "Second Berkeley Software Distribution," 也就是 2BSD，迅速地取代了原先的版本。

1979 年，至少有 75 部 PDP-11 的機器上安裝 2BSD 在運作著。自此在 DEC PDP-11 系列上執行的 BSD 版本便一直以 2.xBSD 作為識別。由於 PDP-11 電腦實在相當長壽，持續到今日
農夫我仍然在網路上發現過關於 PDP 電腦的網站。似乎到今日它們仍舊在某些地方默默地工作著。 2.xBSD 最近的一次改版是在 1987 年，使用 4.3 BSD 為主架構改寫，版本定為 2.10 BSD。

在 BSD UNIX 中登場的重要功能當中，有一個直到今日仍然叫人又愛又恨的指令 – vi。我接觸過不少學習 UNIX OS 的人，大部分的人對 vi 的使用與掌握都不算順手，其中恨死這個指令的也大有
人在，前些日子農夫我還看到某個網站公開討論起 vi 是否阻礙了 UNIX 的發展？實在誇張了一點！

Bill Joy 多次公開地說，他要是知道 vi 會如此受"歡迎"的話，他寧願當初沒有寫 vi 這隻程式。不過 Bill Joy 也說過，當時他原本還想加入一項 Multiple Windows in vi 的功能，不過當他在寫這部分程式的時候，磁帶機壞了，所以 Bill 只好在沒有備份的情況下繼續工作，想不到 "屋漏偏逢連夜雨"，程式寫到一半，他使用的硬碟也跟著掛了。在無可挽救又沒有備份磁帶的情況下，Bill 宣告放棄為 vi 增加 Multiple Windows 這項功能。事後 Bill 為前一版的 vi 寫好使用說明後就繼續作其他的事。所以 vi 就長成今天那付德性。農夫我認為這或許是福不是禍！搞不好當初要是連 Multiple Windows 這項功能一起發表的話，上頭的圖可能就是遺照了。

當時有位 Richard Fateman 教授，原先使用一台 PDP-10 上進行著他的 Macsyma 研究計劃。但他需要更大的記憶體位址來執行程式，所以在 1978 年初，他看上了當時迪吉多新發表的 VAX-11/780。

好不容易，他聯合了其他的部門才湊足購買 VAX 的經費。剛開始時，機器原本安裝的是 VMS 作業系統。不過別的成員要執行 UNIX 作業系統，於是 Fateman 安裝上了 V32。但問題來了，V32 並不支援虛擬記憶體，Fateman 便找上了 Domenico Ferrari 教授，希望他與他的研究小組能為 UNIX 加上這項功能。當時一位學生叫 Ozalp Babaoglu，他想到了一些解決的方法似乎可行，但因為牽涉到 VAX 硬體與 UNIX kernal 的問題，於是他找上了 Joy 幫忙。

就在只有一台 VAX 的狀況下，他們努力奮戰著。1979 年 1 月，在 VAX 上支援虛擬記憶體的 UNIX 版本終於誕生，V32 從此走入歷史。緊接著 Peter Kessler 與 Marshall Kirk McKusick 為他加上了 Pascal；Joy 也將 2BSD 移轉了 ex、vi 編輯器以及 C shell。這個版本就是 3BSD。

一個首次支援虛擬記憶體、demand paging 和 page replacement 的 UNIX OS。


## 1-1-7 UNIX 與 DARPA 交會

1970 年代末，美國國防部先進研究計劃機構（Defense Advanced Research Projects Agency - 簡稱 DARPA）正在為 AI(Artificial Intelligence), VLSI 及計算機視覺等研究(vision research)找尋一個可共通作業的電腦環境。

硬體方面的首選是迪吉多的 VAX 主機。配合的作業系統是 VMS。這樣的組合因擁有相當接近 DARPA 需求的功能被列入優先的考量，但在 DARPA 與 DEC 商談對於 VMS 的支援事宜之後，DARPA 並沒有得到滿意的答案。這迫使他們考慮朝向 UNIX 發展。但當時 UNIX OS(指的就是 32V) 搭配 VAX，最大的缺憾就是沒有支援虛擬記憶體；但此時已經有人克服了。

在 1979 年末，Bob Fabry 教授寫了一份建議書給 DARPA，建議他們以伯克萊支援虛擬記憶體的 3BSD 為基礎，發展成為計畫所需。這份企劃書引發了 DARPA 的高度興趣。之後 3BSD 也實際獲得了 DARPA 相關計畫的成員們的良好風評，也因此最後柏克萊大學打敗了卡奈基梅隆大學與BBN(Bolt Baranek & Newman, Inc.)，讓 Bob Fabry 成功地獲得了 DARPA 的資助合約。這份合約開始於 1980 年 4 月，為期 18 月。

此後的 DARPA 便以 UNIX OS 為標準作業系統。 Bob Fabry 教授在取得 DARPA 合約後，依約成立了一個支援機構，也就是 Computer Systems Research Group 簡稱 CSRG。Bob Fabry 找上了 Bill Joy 來負責軟體發展。Joy 迅速地以先前的 3BSD 為基礎，整合新的功能。如 Job Control(作者是 Jim Kulp)、auto reboot、1K block file system。同時也整合入 Pascal compiler、Franz Lisp system、enhanced mail handling system。 這就是在 1980 年所發表的 4BSD。沒多久她便被安裝在將近 500 台 VAX 上。

DARPA 採用了這個版本作為當時 DARPA 的標準 UNIX 作業系統。樹大招風，當時，有位在 Stanford Research Institute 的仁兄叫 David Kashtan，寫了一份關於 VMS 與 BSD UNIX 在 VAX 上的執行效率評估。該份報告指出 BSD UNIX 在效率上不如 VMS 來的好。Joy 知道這件事之後，花了不到一個星期的時間，重新調整 UNIX kernal。然後也寫了一份報告，證明他們的 BSD 在 VAX 上要比 VMS 優越多多。1981 年 6 月，這個 Joy 調整過的系統，加上了 Robert Elz 寫的 auto configuration，以 4.1BSD 的版本發表了。

當時的 DARPA 對伯克萊 4.1BSD 的表現相當滿意，於是續簽了兩年的新約，金額更是先前合約的 5 倍。

其中有一半的金額用在資助伯克萊繼續發展 BSD UNIX 。錢多的相對代價就是要求高。當時，DARPA 對 UNIX 的期望開出了明確的目標；更迅速、更有效率的檔案系統、支援程序可執行位址
達 multi-gigabyte、提供彈性的解譯溝通能力、具整合支援網路能力。

在此同時，為了達到計畫的目標，DARPA 成立的一個指導委員會；主要的成員有伯克萊的 Bob Fabry, Bill Joy, Sam Leffler、BBN 公司的 Alan Nemeth and Rob Gurwitz、貝爾實驗室的 Dennis Ritchie、史丹佛大學的 Keith Lantz、卡內基．梅倫大學 Rick Rashid、麻省理工學院 Bert Halstead、資訊科學協會 Dan Lynch、DARPA 的 Duane Adams and Bob Baker 以及加州．洛杉磯大學的 Jerry Popek。

不久，Joy 便開始整合早先 BBN 的 Rob Gurwitz 所發表的 TCP/IP protocols，不過他對 BBN 這些程式的執行效率並不滿意，於是 Joy 與 Sam Leffler 重新寫的一版自己的程式。另外，並加入了一些支援網路的工具 rcp, rsh, rlogin, rwho。他們稱她為 4.1aBSD，這個版本並沒有正式發表，在 1982 年 4 月開始供內部使用。

雖是如此，在 4.2BSD 未正式發表之前，她還是繁殖的到處都是。6 月，4.1aBSD kernal 加上了新完成的檔案系統，版本更新為 4.1bBSD。


rcp, rsh, rlogin, rwho 這群指令。因安全機制上的理由，逐漸被另一群新的指令群所取代，新的指令群叫 SSH (Secure Shell)。

1982 年的春季末，早就厭倦了在柏克萊環境的 Bill Joy ，受邀加入當年剛創辦的 Sun Microsystems, Inc.，成為 SUN 的第四號創辦人。那年的整個夏季他就在兩地奔走。之後他對修改中的彈性解譯溝通機制及改寫 UNIX kernal 到一個段落之後，由 Leffler 接手了他的工作。

由於合約期限的因素，Leffler 在 1983 年 4 月發表了 4.1cBSD ，提供給參予 DARPA 各項相關計畫的成員試用。6 月，DARPA 的指導委員會第二次會議招開，驗收與檢討最新版的 BSD 成果。繼續整合 UNIX 系統的 Leffler，在 1983 年 8 月，發表了 4.2BSD。她達到了 DARPA 的預定的需求；足以應付 CAD/CAM 影像處理與 AI 研究的高速的檔案系統及擴展強化的虛擬記憶體功能；提供能分散處理的解譯溝通機制；支援 56-Kbit 速度的 ARPA Internet 網路連結，以及 10-Mbit/s Ethernet 的區域網路；還有經過重組架構已模組化的 kernal code ，提供更有效率的電腦平台移植。

SUN 以生產 RISC 架構的工作站電腦為主，使用的正是以 BSD 為基礎所的 UNIX OS。在當時以不遜色於大型電腦的多人多工、具網路溝通功能的 UNIX OS、加上價格低廉的硬體（相對於 mini 級
電腦而言），廣獲得工程界的青睞，而 mini 級大電腦的命運自此注定開始逐漸式微。電腦軟體的應用因為有了網路於是也開始朝向 Client-Server 的架構發展。

1982 年，SUN 有了自己的作業系統 -- SUN OS 1.0 -- 承襲自 4.1BSD。一直到 1982 年，SUN 才向 System V 靠攏，並將作業系統的名稱改為 Solaris 發表在商業有所成就的 SUN
Microsystems 對 UNIX 的發展倒也做出了一項重大的貢獻；如 1984 年發表的 NFS (Network File System)與其後在 1986 年發表的 PC-NFS。

## 1-1-8 商業化的不平坦歷程 - UNIX 版本的戰爭

UNIX 商業化實質上即意味著將產生各種獨立化的 UNIX 版本，這點大概是最顯而易見的事實。如果以商品要具備獨特性與獨占性的利益來做考量的話，其實一點也不意外。

因此 UNIX 開始衍生的相當多的版本。這種現象，對使用者以開發應用程式的廠商而言，已經造成了某成程度上困惑，一種無所適從的無力感才該開始。

1984 年 1 月 1 日， AT&T 這個擁有 1495 億美元資產、1,009,000 位員工的龐大巨獸，終於被格林 (Harold H. Greene) 法官以反扥拉斯法 (antitrust) 強制拆解成七家 RBOCs (Regional Bell Operating Companies) 。 AT&T 也因而在一夕間解體成為區域性網路公司，從此失去了長途電話的壟斷性地位。這種時空的轉變讓 AT&T 對 UNIX 的態度有了 180 度的轉變(其實，農夫我指的是收費的態度)。

先前已經提過 70 年代初期的 AT&T，已經在長途電話市場上佔有絕對壟斷的優勢，因而被美國政府的限制不得涉足與從事電腦與其他行業，也正因而造就了 UNIX 發展初期的自由開放。直到 1979
年，AT&T 才宣佈要將 UNIX 商業化的計劃。1981 年 11 月，AT&T 屬下的 USG 發表了 System III。次年又更新為 System IV。稍後於 1983 年，AT&T 將 CRG, USG 合併成立了 UNIX System
Development Lab. 一般簡稱為 USL，從其名稱就不難清楚她將要扮演的角色。該年 System V 上市了。

此時 AT&T 發覺每次版本更新都得花不少宣傳費，實在不划算，所以決定在 System V 以後，名字就不再做變動了。1984 年，System V Release 2 發表，簡稱為 SVR2。在這個版本中，
才終於看到來自 BSD 版本的 Virtual memory 功能，農夫我不得不驚嘆 AT&T 的穩健作風。SVR3 則是到了 1986 年才發表，隨後 1987 年又發表了 SVR3.2。

1987 年，在工作站市場上已占有一席之地的 SUN，找上了 AT&T，打算將 System V 與 BSD 這兩大版本歸為一統。1988 年初，雙方更簽訂了合作合約，AT&T 取得 SUN 的一席董事，同時亦
有權買下 SUN 百分之二十的股份。這項合作計劃，原本有機會整合當時版本紛亂的 UNIX OS。但那是理想。實際上這個計劃反而讓 UNIX 族群裡的其他成員恐慌萬分，特別是 IBM、DEC、HP 這
幾個產業龍頭。為了抵制這項行動，他們組織了一個反對聯盟。因此「開放軟體基金會」也就是 Open Software Foundation 簡稱 OSF 在 1988 年正式誕生；成員除了前面的三巨頭外，尚有多達三十幾家電腦硬體製造廠商與系統諮詢顧問公司，也相繼以行動投入到此反對的行列中。然而 AT&T 與
SUN 也不示弱地組織了 UNIX International，也就是 UNIX 國際公司，成員數量雖然不比 OSF 陣營來的多，但 Intel、Toshiba、Unisys、Motolora、Fujitsu，這幾個大塊頭也很夠看頭。


企業自身的利益在現實世界裡始終是以個體的考量為優先，所以這兩大陣營始終沒能再達成任何共識，就連當時所制定的 UNIX 統一標準規格，嚴格來說也從不曾被實現過。這種企業利益上的衝突與矛盾其實也存在於同一個陣營中不同的成員之間。兩大陣營對峙，可以說是 UNIX 有史以來最重大的產業衝突事件。由於商業利益的政治考量大過技術問題的考量，也因此奠定了 UNIX 將繼續分裂下去的命運。AT&T 在 1989 年發表了 SVR4，SUN 在日後也將她的 SUN OS 4.1.3 開始冠上Sorlair 的字眼，OSF 則是在 1990 年發表了 OSF/1。

UNIX 版本的問題因而更加混亂了。但有趣且可笑的是，開放系統 -- Open System，這個雙方都標榜的理念與觀念卻因此在電腦產業界引起了迴響，這點倒是原先所始料未及的。不久 AT&T 撤銷了對 SUN 的投資，同一個陣營的成員彼此也因此而勞燕分飛。USL 在 1991 年正式轉變了一家獨立的商業公司。但 UNIX 在商業市場上的價值卻出現了變化...


## 1-1-9 讓 UNIX 自由 -- Networking Release 2

自從 UNIX 走出貝爾實驗室後，研究機構與學術界就扮演了繼承與發展的雙重角色。在 1979 到 1984 年這段期間，UNIX 的擁有者 AT&T，對於學術界的授權政策尚可用『大方』來形容；同時也對學術界做某種程度的資助與合作。

當時的學術界，得助於 AT&T 的大方授權與分享程式原始碼，研習 UNIX 這個分時作業系統開始在學術界蔚為一股風氣，甚至可以說是一種潮流，一種流行。其中，像柏克萊 BSD 對 UNIX 的貢獻，就是一個公開的事實。但早期的 BSD 使用者，是必需向 AT&T 支付授權金的。這點，從產業界資助學術界的角度來看是一點也不值得驚訝的。因為資金的援助為了就是取得其成果。

所以當時基於 AT&T 原始碼所發展的成果，均歸屬 AT&T 所有。也因而 AT&T 掌控了 UNIX 的所有權。到了 1984 年以後，AT&T 開始更積極地保護 UNIX 的原始碼；AT&T 甚至還要求各大學的使用人員簽訂保密條約，想藉此防堵 UNIX 的原始碼從學術單位流出，以影響到商業利益。

在 DARPA 資助柏克萊從事 BSD OS 發展的過程中，誕生了 TCP/IP 這項廣泛影響現今電腦與網際網路的通訊協定。由於 DARPA 對於資助開發的軟體專案有明文規定接受資助者必須無條件地釋
出程式的原始碼，所以 TCP/IP 的原始碼與程式的版權並不屬於 AT&T 所有。這點在現今看來其意義是不凡的。也正因為有此一條件，柏克萊的 CSRG(Computer System Research Group)因應
BSD Vendors 需求，在 1989 年 6 月發表了 Networking Release 1，她包含了 TCP/IP source code 以及一些工具，提供給當時正開始起步發展的個人電腦製造業者使用。Networking Release 1 授權收費僅 1000 美元，而且不需要 AT&T 的商業授權，取而代之的是柏克萊大學的開放式授權。

農夫我看柏克萊授權方式，幾乎可以說是一種良心式授權方式，在實質的運用上她完全沒有限制。她允許原始碼或執行檔在任何情況下修改並且允許將修改後的程式從事商業行為而無須任何回饋，當然也沒有絕對要求開發者必須要釋出原始碼。如果你改都不改地加以販售，她也沒有意見。但有一點不可違反的限制，就是必須在衍生物的版權聲明上提到柏克萊的貢獻。這種做法在日後，也沒有多少改變，而這樣的授權方式也成為了柏克萊的授權精神。

Keith Bostic 由於 Networking Release 1 所得到的回應實在遠超過 CSRG 成員的預估，這個不算差的成果，讓柏克萊的 CSRG 覺得有必要釋出更多屬於 BSD 的程式原始碼。於是激發 CSRG 的成員 Keith Bostic 開始組織志願工作者從事一項就算不能夠驚天也足以動地的程式寫作計劃，計劃的主要目的在當時還真讓人感到有點烏扥邦，農夫我個人喜歡戲稱她為『解放 UNIX 計劃』。


Marshall Kirk McKusick 這項計劃大體上分成兩個部分，作業系統工具 (Utility) 與核心 (kernal)。而且參與人員必須在完全沒有參考 AT&T UNIX source code 的情況下進行撰寫程式的工作。因為只有在這種條件下，寫出來的程式碼，才能擺脫 AT&T 的著作權束縛。當然這也絕對不是一件容易的事。Keith Bostic 四處奔走，組織了超過四百名熱心的軟體工程師，經過了長達十八個月的奮戰之後，作業系統主要的工具與程式庫才算改寫完成。Marshall Kirk McKusick 負責改寫當時的核心程式。但系統核心的部分，由於長期以來柏克萊與 AT&T 一直就彼此分享 UNIX 原始碼，所以各自所加上去的程式碼早已混雜難分了。為了徹底的釐清雙方各自撰寫的部分，他們下決心進行逐行比對。

首先花了好幾個月的時間，將核心程式每一行每一個檔案都建立轉換比對的資料庫。然後接著進行移除來自 AT&T 32V 的程式碼並改寫她們。即使是如此，仍舊有 6 個核心程式讓他們束手無策，因而無法將核心程式徹底完整地改寫。最後，他們還是決定將他們所做的所有成果發表。授權的方式沿用 Networking Release 1 的授權方式，授權的磁帶依舊是 1000 美金。這個版本就是 Networking Release 2，也有人稱她為 4.3BSD NET/2。發表的時間在 1991 年 6 月。雖然這是個不完整的作業系統，但在今日看來，卻有著劃時代的意義 -- UNIX OS 自由了。


## 1-1-10 誰是"老大哥" - 版權訴訟

AT&T 的 USL 在 1991 年正式轉變了一家公司。當然，這意味著她將更重視 UNIX 在商業上的利益。當時的 UNIX OS 早以稱霸高階的電腦市場；從 Cray 超級電腦、IBM 的大型電腦主機、迷你
級電腦到工作站，均是 UNIX 的天下(這一點，直到現在 21 世紀，仍舊沒有多大的改變)。即使在 80 年代中期後開始迅速發展的個人電腦，雖然當時被戲稱為是玩具電腦，但也仍舊有像 XENIX [1] ,Interactive UNIX [2] 等幾種向 AT&T 繳過稅的商業化版本。UNIX 簡直就是 AT&T 的一棵搖錢樹。

但這一切在 Networking Release 2(以後簡寫為 Net/2)出現之後，起了變化！

首先，一位 i386 處理器的玩家名叫 Bill Jolitz，在拿到 Net/2 之後，很快地就將 Net/2 kernal 缺少的程式補齊了。BSD kernal 這時可算是大功告成了。當時 Bill Jolitz 將他們放在網際網路與其他人共享他的原始碼，並且得到了不少正面的回應。由於這個版本是使用在 i386 微處理器的個人電腦上，所以就命名為 386BSD，在 1992 年 2 月正式發表。這該算是 BSD 首度功能完整且版權獨立的版本。Bill Jolitz 是當時唯一的 kernal 維護者。在他離開這個計劃之後，繼起的 BSD 玩家們延續了這個版本，日後衍生了 FreeBSD，然後又從其中分支出裂 NetBSD 版本。

另一個將 Net/2 完整化的是一家叫 Berkeley Software Design, Incorporated 的公司，簡稱 BSDI [3]。由於 Net/2 的版權聲明中，宣稱其原始檔案的合法性，並且允許使用者，從事衍生物的商業行為，所以 BSDI 將他們修改後的系統命名為 BSD/386。他們並將成果打包，刊登廣告以 995 美金的售價販售 BSD/386，而且含原始碼，而且還提供免費服務電話的諮詢，電號號碼是 "1-800-ITS-Unix"。

時間大約是在 1992 年 1 月。當時，USL 的 System V 含 source code 的價格大約是 BSD/386 價格的一百倍左右。這可驚動了老大哥 AT&T。並且正式地書面嚴重警告 BSDI 違反的註冊商標法(電話號碼裡有 Unix 的字眼)，並公開宣稱 AT&T 擁有 UNIX 的註冊商標。 BSDI 再次刊登廣告公開反擊 AT&T，聲明她的商業行為完全合法。果不期然， BSDI 的博命演出讓雙方手牽手走上法庭。

AT&T 的 USL 控告 BSDI 剽竊他的 UNIX 原始碼，要求法官還他公道。在聽證會上，BSDI 祭出早已準備好的法寶；自己在無任何 AT&T source code 的條件下寫出的合法檔案，以及來自於 BSD 授權的 Net/2 source code。前面的證據足以讓 BSDI 立於不敗之地，後者讓 BSDI 置身在暴風圈外。BSDI 的辨證獲得了法官的採信。

但 At&T 豈會就此罷手，他們將焦點轉移到 Net/2 的 BSD 授權上面，並且重新提出控訴，被告的對象變成了 BSDI 與柏克萊大學；同時 AT&T 還申請法庭禁止 BSDI 一切的 BSD/386 銷售行為。就這樣，柏克萊大學也對號入坐了。

農夫我認為，畢竟 AT&T 是營利企業，她得維護她的商業利益，這點是天經地義的事。雖然柏克萊大學與 AT&T 在 UNIX 發展上有著非比尋常的關係，但商業利益是現實的。企業資助學術界的研究計劃，多半是基於商業上的考量；我相信，學術界的少數高層在尋求奧援時不會不明白這一點，即

使這有可能讓大部分的學術人士無法接受或不願接受。不管如何，這一記醒棍倒再次挑起了這一點事實。成為被告的柏克萊大學，只好無奈地面對這場無情的商業訴訟。但他們也同樣不甘示弱地對 AT&T 的 Systerm V 著作權提出質疑，因為在 AT&T 的 UNIX 授權聲明中完全沒有提及柏克萊的貢獻。

所以柏克萊反控 AT&T 違反的 BSD 的授權條款。柏克萊的反擊讓戰況越演越烈，訴訟案一路從 AT&T 的老家新澤西州的聯邦法庭打到柏克萊大學的所在地加州法院，但依舊沒有結果。到了 1993 年，官司還在進行中，但 AT&T 卻已經打包 USL 準備以一億美元的價格找尋買主了。

最後 AT&T 將 USL 以八千萬美元代價的賣給了 Novell。而新買主也當仁不讓地加入了這場混戰。但卻也因此，戰況露出了一線平息的曙光。訴訟案在 1994 年 1 月宣告終結，以庭外和解收場。實
際的協議內容僅有當事人知情。

如果從勝負的角度來看這場訴訟，或許柏克萊與 BSDI 是勝利的一方。但如果從 UNIX 發展的腳步來看這場訴訟，就可能根本沒有任何一方是勝利者了。

事件平息後的 1994 年 6 月，柏克萊的 CSRG 風光地發表了 BSD 4.4 Lite。在這個版本中，有 70 個檔案引用的一份新修改的版權聲明，闡述的 AT&T 與 BSD 雙方的貢獻，並明確地給予檔案自由散播的權利。但不知為何，應該有能力完整發表的 BSD 4.4 Lite 還是缺少了三的檔案。

當時，農夫我也很高興地買了一本 BSD4.4-Lite CD-ROM Companion，含一張光碟，現在拿在手上，看來總覺得有點呆。

掌握 UNIX source code 以及 UNIX 商標的 Novell，將 UNIX 商標交給 X/open 管理，自己則發展了一套命名為 UNIXWave 的作業系統。推出後市場的反應並不熱絡。不久，Novell 與 SCO 接頭，在 SCO 保證繼續支援 UNIXWare 的條件下，UNIX 在 1995 年二次易主，新主人是 SCO。

備註：

[1] Intel 在 1978 年發表 4.77 MHz 的 8086 微處理器。1980 年，Microsfot 便以 V7 為基礎，發表了在微處理器(microprocessor-based computers)上執行的版本也就是 XENIX。到了 1982 年，一家成立於 1979 年的軟體公司 Santa Cruz Operation，成為微軟的合作開發廠商。之後她這家公司便一直致力於這個領域裡延續到今日，縮寫就是今日的 SCO。

[2] Interactive IS/1 (以 V6 為主體)。這個版本後來演化為比較讓人熟之的名字 -- Interactive UNIX。後來因為 Sun Microsystems 致力發展 Solaris for X86，被財力雄厚的 Sun Microsystems 合併了，如今已經不見蹤跡了。

[3] 就在我反覆修改的時候，BSDI 這家公司已經被 Wind River 合併了，改名為 iXsystems。


## 1-1-11 GNU 計劃 -- 開啟了新大道

在 1983 年 9 月 27 日，麻省理工學院人工智慧實驗室(MIT Artificial Intelligence Lab)的 Richard M. Stallman (以下簡稱為 RMS)，在 net.unix-wizards 以及 net.usoft 的 newsgroups 貼上了一份標題為 "new UNIX implementation" 的訊息。這就是如今廣為人知的 GNU 計劃的開始。

在那則被視為「GNU 宣言」草稿的信息中，RMS 闡述個人的理念與計劃的目的 -- 完成一個命名為 GNU 的 "Free UNIX" 作業系統，希望藉此尋喚理念想同者共襄盛舉。


『如果我喜歡一個程式的話，那我就應該分享給其他喜歡這個程式的人』，這是 RMS 的座右銘。此點也似乎正是促使其決心運作 GNU 計劃的原動力。當時的 RMS 是想寫出一套免費的作業系統。

能夠讓每個人如空氣般地自由的取得與使用。選擇“UNIX 相容”的來設計的主要原因是；RMS 表明，UNIX 並非他個人理想中的作業系統；他僅閱讀一些相關資料，但未曾使用過 (MIT 使用作業
系統是"ITS--Incompatible Timesharing System")；但他認為 UNIX 作業系統具有優良的本質特性。

他相信如果 GUN 與 UNIX 相容將更容易令人接受。所以 RMS 承襲 MIT 用遞迴縮寫字命名的傳統為 GNU 釋譯界定 Gnu is Not Unix。

1984 年 1 月，RMS 為了展開他的理想而決心離開已經待了十幾年的 MIT AI Lab.。當他向他老闆 Patrick Winston 辭職時，Winston 試圖挽留地說：「你還是要辭職？」。RMS 不為所動的回答：「是」。Winston 顯然得到預料中的答案，於是接著說出了思緒裡關懷：「你想要保留你的鑰匙嗎？」。

於是 RMS 就從此開始專心地"失業"在他的老東家。一個人窩在他原來的舊辦公室中，規劃著如何開始他的 GNU 計劃。但想開發一套新的 UNIX 相容的作業系統，即使是財力、人力資源雄厚的頂
級電腦公司，也絕對不是一件說想做就能夠做到的事。當擬妥他的「GNU 宣言」之後，他正式向全世界呼喚、表明其將所為。種子落地了。

GNU 計劃的第一隻程式要算是孤軍奮戰的 RMS 在 1984 年 9 月開始撰寫的 Emacs 編輯器。 1985 年初，Emacs 已進入可用的階段。

於是 RMS 將她放在 pre.ai.mit.edu 這台機器的 FTP server 上，免費地讓 amonymous 的到訪者自由下載使用。不久後，Emacs 強捍的功能引發了一些玩家們的注意，由於附上了 source code，玩家們能自己動手為它添加新的功能或除錯，很快地，Emacs 獲得了相當熱烈的迴響。

隨著名聲漸播，開始有人相繼地加入 GNU 計劃的程式寫作陣營。 "此道不孤"讓 RMS 備感振奮與喜悅。

當時的網際網路並未十分普及。所以有不少人雖然對 Emacs 程式有興趣，卻沒辦法經由 FTP 的管道取得，因而有人透過其他管道向 RMS 詢問能如何取得時，這可讓當時處在失業狀態的 RMS 看
到能夠支持他繼續奮戰下去的資金來源--販售"自由軟體"。

一個人、一個獨立的個人，要想在現實中實行自己的理念，最先得接受"現實"。唯有接收它是事實，實行理念的道路，才獲得比較穩固的起點與開始。 -- 網路農夫如是說。


不管如何，RMS 真的開始以一捲磁帶 150 塊美金的代價，開始服務有需要的人。也因為基於這個開始與基礎，RMS 當年便創立了自由軟體基金會 -- Free Software Foundation (以後簡稱為 FSF)。

這對 GNU 計劃而言，意味著它已跨越個人化理念的構思階段，並進入了有群體組織化的運作階段。同時，RMS 也制定出了屬於 GNU 計劃的軟體版權。RMS 使用 "copyleft" 用來形容她，其實就是與著作版權(copyright) "對立"之意。這也就是 GPL -- General Purpose License (通用公共授權)。GNU 計劃的種子，就這樣生根發芽了。

從販賣 GNU 自由軟體擴展到其他的相關軟體與參考手冊，提供軟體技術支援，並接受電腦器材與資金的捐助(捐助者依法享有一定額度的減稅)，為企業代訓軟體人才。

FSF 努力地開闢財源卻仍舊是運作資金捉襟見肘。RMS 本人不支薪，FSF 聘請軟體工程師的待遇，也僅是軟體業界薪資水平的一半。但這絕不表示 GNU 計劃的軟體水準是半桶水。GCC 編譯器是 GNU 計劃在 1987 年 3 月開始發表的免費編輯器，當時的版本是 0.9 測試版。如今最新的版本則是 3.0。

這個編譯器可以說是今日自由軟體寫作的基石。GCC 所解譯的機器碼，其可靠度絕對不遜於商業化的編譯器產品，甚至可以說是優越過商業編輯器。90 年代初，GNU 計劃暨已完成了質量與數量均十分可觀的系統工具。這些工具被廣泛的使用在當時各種工作站的 UNIX 系統上。雖然已有如此的成就，但這畢竟還不是 "Free UNIX"，他們知道缺少的是什麼--一支"核心程式(kernal)"。

UNIX 在 4.2BSD 之後，越寫越大 kernal 開始帶來一些不便與問題。因而當時便開始有另一個寫作理念逐漸在發展--微核心(microkernal)理念。1985 年，卡內基大學(Carnegie Mellon University 簡稱 CMU)暨以 4.3BSD 為發展基礎，並將之一拆為二，分成 micro kernal 與 single server 兩的部分，該計劃也就是"Mach"。該計劃也成了這方面的先河。

GNU 原本有打算直接採用"Mach"計劃。但無奈，這一等，從 80 年代中等到了 90 年代初，在幾經商量之後，他們打算採用微核心的寫法，成立自己的計劃，名稱叫 "Hurd"。這項計劃，如今仍在奮戰中，雖然 microkernal 的做法讓他們吃了不少苦頭；但可喜的是，0.2, 0.3 測試版本已經發表。

直到 21 世紀的今日，RMS 依舊努力不懈地耕耘著他的夢土。儘管他本人認為還未真正地、完全地實現他的「GNU 宣言」；但他的理念與自由軟體寫作族群們的努力下，一條新的大道通往新的世界。大道旁，枝葉已然繁茂的樹蔭下，可口果實一如禮物般地為所有的人成熟。人們稱她 - Linux。

## 第二篇 認識 SHELL

在我個人接觸 UNIX 的初期，時常會在學習中要求系統管理者幫我做一些系統環境上的改變亦或權限上的開放。

當我開始累積 UNIX 的使用經驗後，回頭猛然發現，事實上絕大部份當初菜鳥時期的我，問的問題簡直是有夠呆。當時的我有一點深刻的體認 ── 認識 shell 是使用 UNIX 作業系統的一個基礎，這點如果一個身為使用者的人無法做到的話， UNIX 的龐大與強悍將會成為使用者最深的負擔與恐懼。


一個使用者如果能先建立對 UNIX OS 機能與適用性的正確認識，保持與系統管理者之間的良性互動。我相信，這樣的工作經驗將會是愉快的。

## 2-1 SHELL 是什麼？

開門見山的說， shell 是一個程式，負責解譯及執行使用者所下達的指令。

由於身負如此之重任，所以通常她必須在使用者簽入（login）系統後，便必須載入記憶體中，這個 shell 有一個專有名詞，我們叫她做 login shell。

她會為使用者處理輸入、輸出及系統的錯誤訊息顯示（standard input, standard output and standard error）；並讀取特殊的起始檔案（startup files）用來設定使用者個人所制訂的環境變數與預設變數（environment variables and predefined variables）。

當然只要使用者還停留在系統中，shell 便會為使用者解譯輸入的指令。直到使用者退出系統前，login shell 都會存在記憶體中為使用者默默地服務著。如果您是身為 UNIX 的使用者而
不知道 shell 為您做如此多的事，實在是太對不起她了。

## 2-2 三個主要的 Shell

UNIX 作業系統在這 20 幾年的發展過程當中，實際上產生過的 shell 實在是不計其數的多。但在各版本之間通用且具有重要的地位的，只有三個。如果依產生的前後次序來排列的話，它們分別是 Bourne shell、C shell 及 Korn shell。

以下是一個簡單的對照表。


| Shell | 創作者 | 符號 | 指令名稱 |
| :----: | :----: | :----: | :----: |
| Bourne | S.R.Bourne | $ | sh |
| C | Bill Joy | % |csh  |
| Korn | David G. Kron | $ | ksh |
   
## 2-2-1 Bourne Shell

UNIX 系統最早出現的 Shell。開發於貝爾實驗室（Bell Laboratories, Murray Hill, New Jersey.），它的創造者是 S. R. Bourne，所以命名為“Bourne Shell”。一直到今天，在各版 UNIX 作業系統內所採用的 Standard Shell 一直均是以它為主。所謂的 standard shell 的意思便是指當一個使用者在沒有指定要使用何種 shell 的情況下，作業系統會自動幫你設定的 shell，我們稱它為 standard shell。

當然它也已經被視為是 UNIX 作業系統必備的一部份了。

因為 Bourne Shell 在執行效率上優於其他的 Shell，所以你也可在 UNIX 系統中找尋到以它的語法所寫成的執行檔。但是它並不支援 aliases 與 history 功能，同時在 Job control 的功能上也比較簡單。它的前景與背景工作是無法任意調換的。在整體的功能上，對今日的使用者而言已明顯地有些不足之處。所以也有一些 shell 以它為基礎，發展出包含新功能的新版本。譬如，你可以在 UNIX System V Release 4 版本中發現到有一個 shell 叫作 “jsh”。

它便是改進了關於 job control 功能的 Bourne Shell 版本。另外還有 Free Software Foundation 也有發展一個 shell 叫 “bash”，縮寫的意思是“bourne-again”。它的整體功能趨近於後來所發展出來的“Korn shell”。

不過它並不包括在各 UNIX 作業系統中。 Bourne Shell 所使用的起始檔案名稱為“.profile”和“.login”。

在變數上支援局部變數（local variables）與整體變數（global variables）兩種。整體變數必須以 export glo_var_name 的方式宣告之。所支援的控制程序有“if-then-else”，“case”，“for”，“while”及“until”等。但請注意在 Bourne Shell 中是沒有“goto”功能的（這是比較嚴謹的作法）。

## 2-2-2 Korn Shell

Korn Shell 出現在 Bourne Shell 與 C Shell 之後，在功能上則吸收了 C Shell 的 aliases, history 等。而語法則是與 Bourne Shell 相容，所以在 Bourne Shell 之下所開發的 shell script，也可以在其中執行。它也是以作者的名字命名的 shell。

原作者是 David G. Kron。Korn Shell 也是開發於美國貝爾實驗室（AT&T Bell Laboratories, Murray Hill, New Jersey.）。

因為在開發的時間上比較晚，現今有支援它的版本，除了 UNIX System V Release 4 版本已將它列為標準配備外，其他版本的 UNIX 作業系統中並不多見。在大部份的 BSD 版本的 UNIX 作業系統並不支援。Korn Shell 所使用的起始檔案名稱與 Bourne Shell 所使用的名稱相同也叫做 “.profile” 和 “.login”。

## 2-2-3 C Shell

C Shell 發展於美國加州州立大學柏克萊分校（University of California, Berkeley, California.），原始版本的 C Shell 創作者是 Bill Joy（這位大哥後來任職於 Sun Microsystems），當時這位大哥還是柏克萊的研究生。由於這個 shell 的語法與 C 語言（C Language）極相似而得此名。此 Shell 對慣用 C 語言的使用者而言無疑是一大福音。

它出現的時間相當早，早到在 UNIX Time-Sharing System, Sixth Edition 中便已支援。所以如今各版本的 UNIX 作業系統中，BSD 版本的 UNIX 作業系統均有支援，而 SYSTEM V 版本的 UNIX 作業系統，要找到不支援 C Shell 也實在是“很難”（因為我目前找不到不支援 C Shell 的 UNIX OS）。所以可以說 C shell 已經是今日 UNIX 作業系統的一部份了。


在特殊功能上，它是最早提供“別名（aliases）”、“指令使用記錄（history）”與“工作控制（Job Control）”功能的 shell。在今天，這幾樣功能幾乎可以說是 UNIX 作業系統的重要特色。C Shell 所使用的啟始檔案名稱與前面的兩個 shell 不同。它的特殊檔案為 “.cshrc”、“.login”與 “.logout”。在其中所使用的設定語法也不相同，所以在使用上並不能相容。 C Shell 所提供的變數有預設變數（predefined variables）及環境變數（environment variables）兩種。分別以內建指令 set 及 setenv 去設定它們。在目前 C Shell 也有他的更新版，不過並非由原作者操刀，而是在 1980 年左右，由一群工商與學術界的人士共同合作的成果 -- 也就是今天的 'T' C Shell，簡稱與指令相同叫 tcsh。 

tcsh 目前發展的相當不錯，除了修更 csh 的一些 bugs 外，還增加了不少新的功能，有空的話不妨換他還試試看有何不同。

## 2-3 C Shell 的運用面

對於一個使用 C shell 作為人機使用界面的 UNIX 作業系統使用者而言，C shell 到底提供了你什麼樣的功能呢？讓我們分別從“指令行模式下”、“製定使用環境”與“程式設計”這三個方面來為你說明。

希望您能藉此先行建立與瞭解 C Shell 應用面的概念。

## 2-3-1 指令行模式下

我相信這應該是使用者最為熟悉的運用層面。所以我使用幾個關鍵性的功能名詞來做為區隔為您分項扼要的說明：

1. 輸入/輸出重導向（I/O redirerction）：

提供一套規則讓使用者可將執行所需的輸入或執行所得的輸出做重導向的組合運用。如重導向輸出為檔案，或將檔案重導向作為指令的輸入等。這個項目可以說相當基礎，是有必要全盤瞭解的。


2. 特殊符號（Regular Expressions）：

C Shell 定義了一套關於特殊符號的功能定義叫做 Regular Expressions。一般所提到的 wildcard 以及各項的括符引號、斜線、倒斜線等定義及使用的法則均包含在裡面。這一套符號規則常式要說簡單嗎？可算是簡單，只要理解的話，不管在指令的使用或者是 sed、awk 的應用都可事半功倍。（不過老實說，一段時日沒接觸的我看到了，回頭看以前自己寫的符號堆，有時也頗具催眠作用）


3. 管道（Pipes）：

此功能則是讓你輕易地將一個指令的輸出結果，做為另一個指令的輸入。個人建議您善用這項功能。


4. 過去指令使用記錄（history）：

可以迅速地將已使用過的指令再次執行，或者是做部份引數上的修改並重新加以執行。看似簡單的理念，不過可以做到相當複雜的變化，可以說是一項非常好用但可以使人懶到極點的好功能。


5. 別名（aliases）：

提供使用者自行設定簡單的字串來取代複雜的指令選項或多個指令的連續組合。這一項使用者絕對不可不會。

6. 工作控制（job control）：

在單一的終端機螢幕模式下，掌控具分時多工特性的 UNIX 作業系統。此功能可能在現今 X-Windows 介面下變的比較不重要了，不過還是建議您多少看一下，因為事實上，這項功能還是相當好用的。

7. 內建指令（Build-in command）：

在這個模式下，C Shell 負責解譯與執行 UNIX 指令，同時也提供一些常用的內建指令提昇系統的使用效率。這些所謂的內建功能我認為多少還是要瞭解一點，雖然你有可能常使用而不自覺。


## 2-3-2 制訂使用環境

當一個使用者想要主動去瞭解如何制訂與如何改變使用環境時，便算是已經來到進階門檻之前了。

以一個使用 C Shell 的使用者而言，簽入（login）UNIX 系統後，系統會幫你啟動一個 C Shell 做為你的 login shell，此 login shell 將會常駐在記憶體中，一直到你簽出（logout）UNIX 系統為止。

C shell 定義了預設變數（predefined variables）及環境變數（environment variables）用來控制使用者的使用環境，設定的方式是在使用者簽入系統時由 login shell 讀取特殊的起始檔案（startup files）作為設定的依據，如果使用者沒有屬於自己的起始檔案，則 login shell 將會讀取系統的預設檔案來加以設定。

C shell 所定義的三個起始檔案分別是“.login”、 “.cshrc”、 “.logout”，這三個起始檔案的檔案格式是一般的文字檔，使用 vi 便可編輯。在使用者 login 後 login shell 會先讀取 “.cshrc” 然後再呼叫“.login”，依據這兩個起始檔案的內容制訂出使用者的使用環境（至於兩類變數應設定在那一個起始檔案中，稍後再做討論）；

當使用者要 logout 時 login shell 則會讀取“.logout”並執行該特殊檔案的設定，然後才會退出系統。

使用者個人的啟始檔案必須放在自己的 home 目錄下，如果你用指令 ls 看不到的話請不用驚訝，因為我們前面已經提過它們是特殊檔案，你必須使用指令 ls -a 才會顯示出來。如果還看不到，這也用不著奇怪，這可能是因為你的系統管理者為你建立 account 時忘了幫你拷貝的緣故吧。如果您使用了 UNIX 作業系統已有一段時日，到今天您才發覺到您根本沒有自己的 “.cshrc” 及 “.login” 啟始檔案的話，你一定會質疑它們必須存在的必要性與重要性？因為過去你沒有這些檔案還不是用的
好好的！

事實上並非如此，因為當你個人的 home 目錄下沒有這些啟始檔案時，shell 依舊是必須去讀取系統為你準備的原始的啟始檔案，所以說如果你沒有這些啟始檔案，你可以在 UNIX 的檔案系統找到系統原始的啟始檔案，以 Sun OS 4.1.X 而言檔案的位於 /usr/lib 目錄內，檔案名稱是 Cshrc 及 Login。

你可以將它們拷貝一份到你的 home 目錄下作為參考，以便於你在學習中做為設定的範本。（在此說明，以後我們所討論的啟始檔案都將是以你的 home 目錄下的必須有這些啟始檔案為前提。）

以下針對這三個檔案分為做功能上的區隔簡介（說明的部份僅只是建議，因為這三個檔案的使用具有相當大的彈性）。


- “.cshrc” 檔案

對我個人而言，這是個令我印象深刻的特殊檔案，也就是曾經把菜鳥時代的我最喜歡亂設定，然後電腦就罷工的特殊檔案“.cshrc”（其意大概是為 C Shell resource control）。對 login shell 而言，這是第一個讀取的啟始檔案（啟始檔案的位置在使用者的 home dir.下）。使用者必須知道一點就是 login shell 產生 sub shell 時，sub shell 也會讀取“.cshrc”檔案，但 sub shell 不會再讀取

- “.login”，此運作法則請務必注意。

一般而言“.cshrc”使用者必要作改變的環境變數（environment variables），由於前面提到過 login shell 產生 sub shell 時也會讀取“.cshrc”，所以設定的變數是會遺傳的這點也請切記（所以在不確定的因素下，不建議自己作不必要的環境變數設定，以免後患無窮）。至於預設變數（predefined variables）的部份，牽涉到的大都是屬於 C shell 本身所提供的操作功能，建議您視變數的特性作必要的設定（因為並非全部的變數都適合在“.cshrc”中設定的）。設定上的實際例子我放在第四、五章中有相關內容時再作說明。

- “.login”檔案

login 進入 UNIX 系統的方式大致說來可分為從 console login，remote login 兩類。前者比較單純，也就是在主機簽入系統，所以螢幕、鍵盤等設定使用的是主機系統的周邊，一般而言都不會有問題。而後者是藉由網路或連線裝置從系統外簽入 UNIX 系統，譬如由另一個 UNIX 主機使用 rlogin 簽入系統；又譬如，從 MS Windows 的個人電腦使用 telnet 簽入系統，或者是從 VT220 的終端機遷入系統等等，由於使用的並非是主機的周邊，有時候必須針對這種情況先加以判斷，然後再加以設定特殊的周邊裝置參數，否則時常會發生如鍵盤或者編輯上（特別是使用 vi 指令時）的小問題。
適當的“.login”檔案設定可以應付上述的情況，設定的情況得視實際的狀況而定。

- “.logout”檔案

這個特殊檔案是 C Shell 專有的，它的用途我想你應該猜的到，就是在你退出系統前才會執行的特殊檔案。也就是在你的 login shell 要終止之前，C shell 會到你的 home 目錄之下去尋找這個特殊檔案，並依其內容的設定加以執行。由於在功能上屬於非並必要性，所以在一般的 UNIX 系統中，這個特殊檔案並不像“.cshrc”及“.login”在系統中的有預設檔案的存在。如果使用者個人需要的話，必須自己使用文字編輯工具作自己的設定。

我個人認為 C shell 的這項功能非常適合來做一些暫存檔案的清除，或者是個人工作資料與記錄的整理及備份，或者是一些備忘錄資料的顯示等等。

對於 UNIX 系統的起始檔案，最好能有系統的預設檔案，這部份應該是系統管理者的責任。使用者個人在有正確的認知情況下，可依據個人的需求再加以調整與設定，當然調整設定後的後果，正確的說使用者應自行負責。對於起始檔案，使用者應該要有自己設定的做修改與設定。如果一個 UNIX 系統的管理者與使用者無法共同做到此點，便應該再自我提昇對系統的使用能力。

## 2-3-3 程式設計

C Shell 雖然是一個負責解譯及執行指令的使用者界面，但是它的功能卻不僅只限於此而已（事實上，在 UNIX 系統中，三個 shell 均具有此特性，而這點特性，便是我喜歡 UNIX 系統的主要原因）。 C Shell 提供在語法上類似於 C Language 的流程控制（control flow），也正是 C Shell 得其名的主因。由於具有此項功能，在程式設計上對於一個學習過 C Language 的使用者而言相當容易適應。


同時 C Shell 的包容性上也比 Bourne Shell 及 Korn Shell 來得好。不過事實上，有些 UNIX 作業系統的專家相當反對使用 C shell 來撰寫程式，如 Tim O‘Reilly 及 Jerry Peek 兩位 UNIX 的先進大師在其 UNIX 的偉大著作 UNIX POWER TOOLS 中，就以一個章節的篇幅來說明 C Shell 在撰寫程式時會產生的限制及 bugs。（UNIX POWER TOOLS 第49章 “C Shell Programming ... NOT”）。

原因事實上很簡單，就是不夠嚴謹，且有一些致命性的 bug 存在。原本我的寫作計畫中，想對此部份做比較深入的介紹，後來也受到此篇文章的影響，修改過不少 script 範例，不過仍然無
法擺脫其陰影。所以目前此部份正在重寫中。建議有心想要瞭解這部份的使用者，可以讀一讀 GAIL ANDERSON 與 PAUL ANDERSON 合著的『The UNIX C SHELL FIELD GUIDE』，我相信您絕對能有相當大的收穫。

## 第三篇 C SHELL 的基本運用

3-1 在 C SHELL 下 的指令運用

3-2 輸入 / 輸出重導向

3-3 檔名擴展的運用

3-4 管線的觀念與運用

3-5 History 的設定與運用

3-6 別名的設定與運用

3-7 工作控制的運用

3-7-1 前景工作（foreground jobs）

3-7-2 背景工作（background jobs）

3-7-3 背景工作的控制管理

3-7-4 關於背景工作使用的注意事項

3-8 C SHELL 的內建指令

3-8-1 umask 指令

3-8-2 exit 指令

3-8-3 source 指令

3-8-4 limit, unlimit 指令

3-8-5 dirs 指令

3-8-6 echo 指令

3-8-7 time 指令

3-8-8 nice 指令

3-8-9 rehash, unhash, hashstat 指令

3-8-10 exec 指令

3-8-11 eval 指令

3-8-12 repeat 指令

3-8-13 pushd, popd 指令

3-9 引號的運用與指令的關係

3-9-1 單引號（ ' ）的運用（single-quotes）

3-9-2 雙引號（ " ）的運用（double-quotes）

3-9-3 倒引號（ \` ）的運用（backquote）

3-9-4 倒斜線“ \ ”的運用（backslash）