---
title: Gunden Geri Kalanlar - 4
date: 2020-06-04
---

* Bugun veri yapilarinda `Tree` yapilarina devam. Bu yapilarin `linked-list` ve `array`'lere gore avantajinin herhangi bir deger arama ya da arama iliskili bir fonksiyonun ortalamada **O(log(n))** zaman karmasikligina sahip oldugunu ogrendim. En kotu durumda (tum Node'larin arkasi arkaya birbirne bagli oldugu, 'maximum height') yine ayni hesaba geliyor fakat ortalamada avantajli gorunuyor. 

	- Bu ortalama **O(log(n))** nasil elde edildigini anlamak icin ufak bir simulasyon yazmayi dusundum. Hem de sifirdan Python'da bir **Binary Search Tree** class'ini sifirdan yazayim diye kollari sivadim. Fakat C++'da alisik oldugum pointer'lardan sonra Python'daki referencing olayi epey bir kafami karistirdi. Ozellikle `None` degerine sahip bir attribute'u alip, sonra buna deger atama kismi epey kafami karistirdi, biraz takildim. Biraz daha ugrasmam gerekiyor sanirim.

	- Ayrica **Computerphile**'da gecen hafta yayinlanan `Tree` videosu da epey kafami acti: [Coding Trees in Python - Computerphile](https://www.youtube.com/watch?v=7tCNu4CnjVc&t=12s) "Syntax Trees" ornegi uzerinden ML'deki turev alma kavramina kadar getirdi konuyu. Bu yapi uzeriden turev almayi nasil tanimlariz, uzerine dusunulesi... Ayrica meger amcanin Python kitabi da varmis; epey ozgun gorunuyor yaklasimi: [Conceptual Programming with Python](http://www.cs.nott.ac.uk/~pszit/cp.html#Videos)

* Bugunku LeetCode challange epey bir kolaydi; karakterlerden olusan bir listeyi tersine cevirmemiz bekleniyordu. Fakat bunu yaparken yeni bir obje olusturmadan **"in-place"** gercekelestirilmesi bekleniyordu. Python'da bunu yapan dogrudan bir standart kutuphane metodu oldugundan biraz hileli bir sekilde hizlica cozmus oldum. Fakat bir listeyi farkli sekillerde tersine cevirmenin yollari icin de D. Bader'in su referans yazisi burada dursun: ["How to Reverse a List in Python"](https://dbader.org/blog/python-reverse-list). Kisaca cozumum surada:

```
# LeedCode June Challange Day 4
# Reverse a String Problem
# Write a function that reverses a string. The input string is given as an array of characters char[].
# 
# Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.
# You may assume all the characters consist of printable ascii characters.

def reverseString(self, s: List[str]) -> None:
    """
    Do not return anything, modify s in-place instead.
    """
    s.reverse()
```

* Python tarafinda ise:

	- R. Lerner'in [Ace Python Interviews]() serisinde Python'daki **"mutable" vs "immutable"** kavramini inceleyen kisa bir video izledim. `string` ve `tuple`'larin "immutable" oldugunu biliyordum fakat `int`, `float`, `boolean` gibi "built-in type"'lari immutable olarak dusunmemistim. Ayrica bu sebebpten `string` bir objenin uzerine herhangi bir metod kullandigimizda (orn: `s.upper()`), bahsi gecen objeyi degistirmeyip yepyeni bir obje donduruyor. Immutable type'lari bir tercih sebebi, Python'da `const` degiskenler olmadigi icin, degistirilmesini hic bir sekilde istemedigimiz degiskenler icin bunlari kullanabiliyoruz anladigim kadariyla.

	- Arada sirada Twitch'den yayinlarina goz attigim, Python'un gelistirilmesine de katki koyan Anthony S., Youtube kanalinda Python ogrenenler icin farkli seviyelerde aciklayici/ogretici videolar yayinliyor. Bugun serinin ilk videosu: [python cli tested with pytest](https://www.youtube.com/watch?v=sv46294LoP8)'i izledim. Basit bir `print` statement yazan bir komut satiri programi yazdi fakat arka planda `argparse`, `pytest`, `sys` ve `mypy` gibi modulleri kullanarak ayaklari her yonden yere basan bir program nasil olusturuluru gosterdi diyebilirim. 

	- Gunun sonlarina dogru Twitter'dan gordugum bir paylasimla **Sinan Erdinc**'in Python'da `zip`, `map`, `reduce`, `filter` fonksiyonlarinin anlatimi ve sonunda guzel bir ornekle sundugu [cok guzel bir yaziya](https://www.sinanerdinc.com/python-map-zip-reduce-filter-kullanimi) denk geldim. Sanirim bu tip islemler Python'daki "fonksiyonel programlama" yaklasiminin izlerini iceriyorlar. Mapreduce kavrami "big data" komunitesinde epey yaygin zaten fakat Python'un standart kutuphanesindeki fonksiyonaliteyi kesfettikce daha da bir vuruluyorum bu dile...

* [MIT'nin "Fundementals of Statistics"](https://courses.edx.org/courses/course-v1:MITx+18.6501x+2T2020) dersinde, istatistigin temeli **Central Limit Theorem**(CLT) ve **Normal Distribution** ile devam ettik. Bu iki kavrami da deneysel parcacik fizikcisi olarak surekli kullaniyor olsam da, yillardir cesitli vesilelerle bircok kez karsilasmis olsam da derste epey guzel yeni "insight" edindim:

	- CLT ortalamalarin gercek ortalamaya (buyuk N degerleri icin) nasil yakinsadigini soyleyen bir teorem ve sonunda olceklenmis bir normal dagilima yakinsadigini soyluyor. Istatistikte de biz genellikle ortalamalarla ilgilendigimiz icin her yerden Normal dagilim elbette cikiyor. Guzel bir perspektif.

	- CLT uzerinden, elimizdeki ortalamanin gercek degere ne kadar iyi yakinsadigini hesaplayabilmemizi sagliyor; fakat bunun icin N degerinin yeteri kadar buyuk olmasi sart (genellikle N > 30). Peki bu sart saglanmadigi durumda bir ust sinir koyabilmemiz saglayan birseyler var mi? Ta daaamm: **Hoeffding Esitsizligi** (bknz. asagidaki slayt). Bu esitsizlige zamaninda izledigim Caltech'teki ["Learning from Data"](https://work.caltech.edu/lectures.html#lectures) dersinde **"Is Learning Feasabile?"** tartismasinda karsilasmistim ve epey etkileyici gelmisti.

      <center><img src="/img/hoeffding.png" ></center>
      <center>Kaynak: MITx Fundementals of Statistics </center>

      <center><img src="/img/hoeffding_caltech.png" ></center>
      <center>Kaynak: Caltech Learning from Data - Lecture 2 </center>

	- Bununla iliskili ayni zamanda bir de **Chebyshev**  ve **Markov** esitsizlikleri de dusuk N degerleri icin bir kestirim veriyor.

	- Normal dagilimla iliskili, cok uzerinde durmayip simdi fark ettigim, aslinda bu dagilimin bir "support"'unun olmamasi; eksi sonsuzden arti sonsuza tum degerleri (ortalamadan uzak degerleri cok dusuk olasikla olsa da) alabiliyor. Fakat bu rasgele degisken modeli fiziksel surecleri modellemek icin gayet gonul rahatliiyla kullaniyoruz! Hakikaten enteresan...

* Gunumun zirve noktasi sanirim [ACM Bites](https://learning.acm.org/bytecast) podcastinde efsanevi bilgisayar bilimcisi [Donald Knuth ile yapilmis bir roportajin podcastini](https://www.podbean.com/media/share/pb-qcwtt-de8e75?utm_campaign=w_share_ep&utm_medium=dlink&utm_source=w_share) dinlemekti sanirim. 

	- Roportajda tum problemleri algoritma perspektifinden dogal olarak goren %2'lik bir gruptan bahsediyordu; bu sinifa dahil olmadigima adim gibi eminim :)

	- Tum basarilarina ragmen muthis mutevazilikte bir kisilige sahip olmasi ve ogretmeye yonelik tutkusunu anlatisi cok guzeldi.

	- Seksen yasini asmis olmasina ragmen her hafta dort gun duzenli olarak ofisine gidip, daha bu sabah ugrastigi kodda buldugu bug'i duzeltisini heyecanla anlatiyor olmasi epey etkileyiciydi.

	- Tum hepsinin uzerine muzik meraki ve org icin besteledigi eserinin dunyanin farkli yerlerinde premierlerinin yapilmasi hikayesi cabasi sahane!

	- Son olarak her yil, **Art of Programming**'in o yil yayinlanmis bolumuyle ilgili Standrford'da verdigi [**Christmas Lecture**'larin herbirinin Youtube'da](https://www.youtube.com/playlist?list=PLoROMvodv4rOAvKVR_dyCigSBMcYjevYB) oldugunu ogrendim. Iste gunun kesfi!

  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>