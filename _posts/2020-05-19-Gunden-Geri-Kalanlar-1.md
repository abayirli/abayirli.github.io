---
title: Gunden Geri Kalanlar - 1
date: 2020-05-19
---


Calisma gunlugu niteliginde, gunden geri kalanlari ufak ufak paylasacagim serinin ilki ile baslayalim. Cogu zaman 'kendime notlar' seklinde olacak kisa not, hatirlatma ve baglantilardan faydalanan baska birileri de olursa ne ala...


* Yeni basladigim Colombia Unv'den, ayni zamanda `scikit-learn` kutuphanesinin de gelisitiricilerinden Andreas Muller'in [Applied Machine Learning](https://www.cs.columbia.edu/~amueller/comsw4995s20/schedule/) dersi cok iyi basladi. Bugun ucuncu ders "Introduction to Supervised Learning"te dikkatimi ceken noktalar:

	- [Bugunun ders notlari](https://amueller.github.io/COMS4995-s20/slides/aml-03-supervised-learning)
	- k-Nearest Neighbor'da k'in kucuk degerleri icin model karmasikligi daha fazla (ve overfit'e yatkinken), buyuyen k degerleri icin model karmasikligi azaliyor (belirli bir yere kadar) - tam tersi gibi dusunmusumdur hep, demek ki yeterince dusunmemisim!
	- Overfit olup olmadigini dogrudan `train_score` ve  `test_score` arasindaki farka bakarak kontrol etmek. Bu farkin buyumeye baslamasi "overfit"e karsilik gelirken, ikisinin birbirini yakindan takip etmesi ise "underfit" durumu. Ideal nokta ise `test_score`un tepe yaptigi fakat `train_score`dan da biraz farkli oldugu bir nokta [bknz](https://amueller.github.io/COMS4995-s20/slides/aml-03-supervised-learning/#p13)
	- kD-tree kullanarak prediction time dusuk boyutlu (p) veriler icin (bu buyuk kisitlama) O(k * log p )''ye indirilebiliyor.
	- Cross-validation'in tum olayi, ayri bir validation set koyup tek bir validation score elde etmek yerine olabildigince stable ve uzerindeki hatasi da belli olan bir score elde etmek. 
	- Siniflandirmada, cross-validation yaparken sinif-dengesini gozetmek icin "Stratified Sampling" onemli - `scikit-learn` siniflandirmada otomatik olarak `StratifiedKFold` kullaniyormus zaten. Train-test ayriminda da direkt uygulanabiliyormus meger: `train_test_split(X, y, stratify=y)`
	- `scikit-learn`de default baseline olarak dummy classifier diye bir sey varmis - ornegin otomatik olarak en sik rastlanan sinifi atayan bir dummy classifier icin: `dc = DummyClassifier('most_frequent')` 
	- non-iid veriler icin cross-validation yaparken rastgele secim yapmak yerine, verinin siniflarina ya da korelasyonu goz onune alarak bu ayrimi yapmak onemli. Ornegin bir zaman serisinde belirli bir pencere belirleyip, gecmis veriyi train, gelecek veriyi de test olarak almak gibi (aksi takdirde rastgele secim yapildiginda train'de yer alan bir veri noktanin hemen yakinindaki bir test verisi cok yuksek ihtimalle perfect olarak tahmin edilecek intrinsic correlation sebebiyle). `scikit-learn`'de non-iid ve zaman serileri icin ozel coss-validation metodlari da varmis: `GroupKFoldSplit` ve `TimeSeriesSplit`.
	- cross-validation'in sadece accuracy ve hatayi degil ekstra bircok seyi dondurebilmesi icin su fonksiyon epey kullanisli:

	```
	res = cross_validate(KNeighborsClassifier(), X, y,
						 return_train_score=True,
                     	 scoring=["accuracy", "roc_auc"])
    ```

* Udacity'de '[Design of Computer Programs](https://www.udacity.com/course/design-of-computer-programs--cs212)' dersine basladim. Python uzerinden CS temellerini sIkI bir sekilde atmak icin birebir gorunuyor. Dersi Google Research direktoru Peter Norvig'in vermesi ise ayri bir efsane. Ilk haftaya verilen poker ellerinin kazananini bulmak uzerine bir program yazmak ile basladik. Dersin sonunda Poker'e saricam gibi duruyor.

* PyIstanbul'un bugunku online seminerinde ["Python Programcilari icin JavaScript"](https://www.youtube.com/watch?v=EEXFcdTmgZM) konusmasi epey keyifliydi. Python'u baska bir dille karsilastirmali olarak gormek hem Python'a hem de o yeni dile yonelik epey sey ogretiyor. Bu konusma tam da gecen gun karsima cikan Real Python'daki ["Python vs JavaScript for Pythonistas"](https://realpython.com/python-vs-javascript/) yazisinin uzerine gelmesi de manidar oldu. Ufak ufak kanim isinmaya basliyor JS'e, haftasonu P5.js ile ufak tefek seyler yapmaya baslamayi hedefliyorum.

* Gunun ilginc bilgisi: Python -5 ile 256 arasindaki tam sayi degerlerini her seferinde atamak icin hafizada yer ayirmak yerine bu veriler 'cache'leyip her atandiginda ayni nesneyi isaret ediyor. Bu sayi araligi cok sIk kullanildigindan boylece surekli memory allocation ile ugrasmayip hem zamandan hem yerden kazaniyormus mus... Ilgili blog yazisi: [Python Caches Integers](https://arpitbhayani.me/blogs/python-caches-integers)

* Br diger ilginc bilgi, floating-point aritmatiginin yan etkilerinden haberdardim fakat Python'da `0.1 + 0.2 == 0.3`'un ```False``` donecegini hic dusunmemistim!
 
--------------------------