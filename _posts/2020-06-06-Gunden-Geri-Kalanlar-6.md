---
title: Gunden Geri Kalanlar - 6
date: 2020-06-06
---

* Haftasonu kahvemi alip, ayaklarimi uzatip "podcast keyfi" yaparken karsima cikan [Data Skeptic podcastinin yeni bolumu "Black Boxes are not Required"](https://dataskeptic.com/blog/episodes/2020/black-boxes-are-not-required) ile tam bir "down the rabbit hole" deneyimi yasadim diyebilirim. Machine Learning yontemlerinin aciklanabilirlik/anlasilabilirlik kavramina epey radikal bir yaklasimi olan Duke Unv.'den **Cynthia Rudin**, kendi calistigim projede de epey basimi agritan bu konu uzerine, cogu su ana kadar karsilasmadigim bircok yeni bakis acisindan bahsediyordu. Ben de podcast sonrasi, yayinda ustu kapali gectigi yontemlerin/yaklasimlarin neler oldugunu arastirmak adina profilini detaylica inceledigimde bir derya sey buldum. En hizli yoldan fikir almanin yolu, bir yerde verdigi bir "review" lecture var mi diye bakarken, asagidaki ikisini buldum. Birini detaylica ozetledim:

* [Statistics at a Crossroads Webinar](https://zoom.us/recording/play/0y-iI9HamgyDzzP2k_jiTu6jB7JgVVXnjWZKDMbnyRTn3FsxTDZy6Wkrj3_ekx4J?startTime=1538497702000) - "Please Stop Doing 'Explainable' ML" (17. dk'dan itibaren)

	- Bir modelin *explainable* olmasi ile *interpretable* olmasi arasinda fark var [Bu terimlerin Turkce karsiliklarinin ayni kavrami karsilayip karsilamadigindan emin olmadigim icin orijinal halleri ile kullanacagim):
		- Explainable: "Black-box" model kullanip, sonrasinda bu black-box'in ciktilarini anlamaya calismak
		- Interpretable : En bastan "black-box" modeller disinda bir model kullanip, verdigi ciktilari anlamak

	- Cokca kullanilan **variable importances** ve **partial dependence plot**'larin "interpretable ML" olmadini vurguluyor.

	- Modelin explainability/interpretability'si ile modelin (dogruluk) performansi arasinda sanildigi ve iddia edildigi uzere bir ters oranti yok. Hatta cok buyuk orandaki durumda, interpret edilebilir modelleri kullanarak black-box modellerle ayni performans elde edilebiliyor diyor. 

	- Veri bilimi (eski adiyla "knowledge discovery")'nin iteratif bir process oldugunu soyluyor; interpretable bir model yapip, modelin nasil davrandigini anlarsak, buradan ogrendiklerimizle iteratif olarak en bastaki modeli daha da guclendirebiliriz.

	- Tabi bunun gerceklesebilmesi icin elimizdeki verinin **good data representation**'a sahip olmasi gerek; yani structured bir veri ise her bir kolonun olusturulmus bir anlami varsa. Computer vision, time seris ya da NLP problemleri gibi verinin kendi icinde bir yapi barindirmadigi durumlari disarida tutuyor. Bu durumlarin disindaki, **good data representation**'a sahip veri setleri uzerinde hemen hemen tum ML yontemlerinin ayni performansi gosterdini soyluyor! Bu epey guclu bir arguman.

	- Computer vision'i disarida birakiyor dedik ama mevcut vision deep learning yaklasimlarinda, modelin karar verirken gorselin hangi bolumune odaklandigi gibi aciklamalar veren yaklasimlari da elestirip, son donemlerde yayinladiklari birkac makalede bunlara alternatif yontemler onermisler. Interpretability sadece columnar data icin gecerli bir kavram degil kisacasi.

	- Insanlarin neden "black-box" modelleri sevdigini, asagidaki slide ile cok guzel acikliyor:

	<center><img src="/img/2020_06_06_InterpretableML_1.png" ></center>
	<center>Kaynak: C. Rudin </center>

* C. Rudin'in "interpretable" yontemler dedigi yontemleri bastan sona ele aldigi "review talk" ise gecen yil KDD konferansinda verdigi keynote konusma: [KDD - cynthia Rudin KDD 2019 Keynote](https://youtube.videoken.com/embed/wL4X4lG20sM)

* Podcast'te konusma arasinda gecen "artik neden kimse **'Apriori Algorithm'** yontemini ogretmiyor anlamiyorum..." demisti; hicbir ML dersinde, kursunda, kitabinda rastlamamistim bu algoritmaya ben de. **"Veri madenciligi"**nden gelen bir "eski" bir yontem ve [Youtube'daki su harika videodan](https://www.youtube.com/watch?v=WGlMlS_Yydk) izledigim kadariyla da epey "anlasilabilir" ve etkili bir sekilde uygulanabilir hakkaten. Yillardir istatistikcilerin kafa yorduklari problemlere ve getirdikleri yaklasimlara, bilgisayarcilarin "devrim" yapip, gecmisi "hemen hemen" tamamen yok sayip, getirdikleri yaklasimin hic sorgulanmadan icsellestirilmesi problemi de var gibi ayni zamanda. Uzerine dusunulesi...

* Okuma listesine eklemek icin de su makaleyi ["Stop Explaining Black-box Machine-learning Models for High-stakes Decisions and Use Interpretable Models Instead"](https://www.nature.com/articles/s42256-019-0048-x) ve bunun uzerine yazilmis [Morning Paper'daki yorum yazisi](https://blog.acolyer.org/2019/10/28/interpretable-models/)

* Bu arada "interpretable ML" konusunda, zamaninda epey yararlandigim su kaynagi da not edeyim: [Interpretable ML Book](https://christophm.github.io/interpretable-ml-book/)

* Leedtcode'da bugun yine takildim; bu sefer problemi anladim, ilk adimlari da yazabildim fakat bir noktada yine patladi; cozume bakmak durumunda kaldim. Sagolsun [Youtube'daki arkadas daha yarin olmadan cozumu yapip guzelce anlatiyor](https://www.youtube.com/watch?v=HKHkzKvb0J4). Soru ve elemanin cozumu asagida. Cozumden yeni ogrendigim bir sey de `array`'e `insert` metodu ile eleman yerlestirmek oldu. 

```
# Suppose you have a random list of people standing in a queue. 
# Each person is described by a pair of integers (h, k),
# where h is the height of the person and k is the number of people
# in front of this person who have a height greater than or equal to h.
# Write an algorithm to reconstruct the queue.
#
# Note:
# The number of people is less than 1,100.
#
# Example:
# Input:
# [[7,0], [4,4], [7,1], [5,0], [6,1], [5,2]]
#
# Output:
# [[5,0], [7,0], [5,2], [6,1], [4,4], [7,1]]

def reconstructQueue(self, people: List[List[int]]) -> List[List[int]]:
	#sort people higher to lower; if heights equal sort by the key
    sorted_people = sorted(people, key = lambda x: (-x[0], x[1]))
    
    arr = []
    for people in sorted_people:
    	#insert the person at the position given by the key
        arr.insert(people[1], people)
    
    return arr
```

* Bugun, siniflari (label) epey dengesiz bir sekilde dagilmis (%70 vs %30) bir veri setini, dengeli hale getirmek icin birkac yontem uzerinde calistim. Normalde basit olarak **over-sample** ya da **under-sample** edip, ornek sayisi fazla (az) olan siniftan yeni ornekler sample edip cikararak (ekleyerek) siniflar esitlenebilir fakat bu yontem ayni veriyi tekrar ettigimiz icin bircok problem barindiriyor (over-fitting vs). Bunun yerine biraz daha akillica bir seyler yapabilir miyim diye sorarken Python'da bu **Inbalanced Learning** problemi icin ozel bir kutuphane oldugunu ogrendim: ```imblearn``` [link](https://imbalanced-learn.readthedocs.io/en/stable/api.html) ve kutuphane icindeki fonksiyonaliteyi anlatan cok guzel bir Kaggle Kernel'i de mevcut: [Resampling strategies for imbalanced datasets](https://www.kaggle.com/rafjaa/resampling-strategies-for-imbalanced-datasets). 

* Ufak bir guncelleme; bu hafta Almanya Munih'ten teknik mulakat yaptigim sirketten bugun ikinci asamaya gectigim haberi geldi! Iki hafta sonra bolum direktoru ile gorusmem var, sonrasinda da bir proje odevi olacak. Fingers double crossed!

* Son olarak dun rastladigim ve bu notlari paylasma motivasyonumu ve bu surecten kazandigimi su Tweet tek cumlede ozetliyor.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">You understand what you don&#39;t understand once you write about it.</p>&mdash; Orange Book 🍊📖 (@orangebook_) <a href="https://twitter.com/orangebook_/status/1268812904473792512?ref_src=twsrc%5Etfw">June 5, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>