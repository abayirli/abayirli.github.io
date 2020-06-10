---
title: Gunden Geri Kalanlar - 9
date: 2020-06-09
---

* [Design of Computer Programs](https://classroom.udacity.com/courses/cs212) dersinin ikinci haftasi yine 'beyin yakan' modda bitti. Her hafta birbirinden ilginc problemler ve bunlara olabilecek en zarif cozumlerle gelebilmeyi basariyor Norvig amcamiz. Bu haftaki dersten geriye kalanlar:

	- Ugrastigimiz problem **cryptarithmetic** diye adlandirilan, harflerle kodlanmis aritmetik islemleri *decode* etmek uzerineydi. Ornegin `AB + AB = CDF` seklinde verilmis ve her harfin farkli bir sayiyi, ayni harfin ayni sayiyi ifade ettigi tipte cebirsel ifadeleri saglayan sayilari bulmak amac.

	- Harfleri sayilarla eslemek icin `string` modulundeki `maketrans` ve `translate` metodlarini kullanarak *translation table* olusturup, elimizdeki *string* ifadeyi cebirsel bir ifadeye ceviriyoruz.

	```console
	>>> formula = "ABABCDF"
	>>> table = string.maketrans("ABCDF", "76152")
	>>> 
	>>> formula.translate(table)
	'7676152'
	```

	* String manipulasyonu icin bol bol **Regular Expression** (regex) kullanmak gerekiyor; birkac kere kullansam muhtemelen alisacagim bu ifadelere her gordugumde "what kind of black magic is this?" seklinde yaklasiyorum... Note to self: [Real PYthon'daki Regex tutoriali](https://realpython.com/regex-python/) muhtemelen isini gorur.

	* Yazdigimiz bir kodun calisirken, kodun hangi kisimlarinda ne kadar zaman harcadigini gormek icin harika bir tool var `cProfile` adinda. Dogrudan komut satirindan cagrilabiliyor; isleyisin nerelerde tikandiginin/yigildiginin cok guzel bir ozetini sunuyor. Su sekilde cagirabiliyoruz:

	```console
	$ python -m cProfile 03_TwoCity_Scheduling.py                                                                                                      
	33352186
	         1206735 function calls (1206692 primitive calls) in 0.319 seconds

	   Ordered by: standard name

	   ncalls  tottime  percall  cumtime  percall filename:lineno(function)
	        1    0.036    0.036    0.072    0.072 03_TwoCity_Scheduling.py:11(twoCitySchedCost)
	   100000    0.013    0.000    0.017    0.000 03_TwoCity_Scheduling.py:13(<lambda>)
	        1    0.042    0.042    0.244    0.244 03_TwoCity_Scheduling.py:39(<listcomp>)
	        1    0.001    0.001    0.319    0.319 03_TwoCity_Scheduling.py:9(<module>)
	       	....
	       	....
	```

	* Sonrasinda bu bilgiden yola cikarak, en cok zaman harcanan kismi acaba optimize edebilir miyim diye dusunmek kaliyor. Fakat bu esnada D. Knuth'un meshur lafini unutmamak gerekiyor: **"Premature optimization is the root of all evil"**. Cunku optimizasyonda unutulmamasi gereken onemli bir kavram var, **Law of Diminishing Returns**. Kodunuzun %10 zaman gecirdigi kismi 10 kat hizlandirirsaniz, toplamda kodunu sadece %10 hizlandirmis olacaksiniz, cunku asil *bottleneck* gerideki %90'lik kisimda. Tabi cogu zaman %10'luk hizlanma bile buyuk olcekli islerde onemli bir kriter olabiliyor, o ayri.

	* String olarak verilmis bir ifade `eval` fonksiyonu ile dogrudan bir Python ifadesiymis gibi calistirilabiliyor. Ornegin `eval("1 + 2 == 3")` ifadesi `False` donduruyor. Bu tip ifadeyi farkli parametrelerle surekli dondurme durumunda, sureci hizlandirmak icin, her string ifade icin arka planda sifirdan bir parse tree olusturulup, evaluate ettirmek yerine, eger yapi sabit ise bunu bir `lambda` fonksiyonu icine yazip, bunu parametrelerle cagirmak cok daha efektif olacaktir: `lambda x,y,z : x + y == z` gibi...

* Bugun biraz `numpy` alistirmasi olsun diye hem, kompleks sistemlerde karsimiza cikan **Cellular Automata** simulasyon programlari yazmaya basladim. Bu yapilar standart kurallarla, elinizdeki ornegin 1-boyutlu bir grid'deki *hucrelerin* bir sonraki zaman adiminda nasil degisecegini tanimliyor. Standart taniminda, degistireceginiz hucreye ve bir yan komsularina bakarak karar veriyorsunuz. Bu uc hucrenin 8 farkli durumu var, her durum icin hucreyi 1 (siyah) ya da 0(beyaz) yapabilirsiniz. Dolayisiyla bu sekilde toplam 256 tane kural tanimlamak mumkun. Her bir kural buna gore 0'den 255'e kadar isimlendiriliyor. Her bir kuralin zamanla evruminde epey enteresan ve cogu zaman karmasik sonuclar cikiyor ortaya. Tum kurallar ve ciktilari icin: [ref](https://plato.stanford.edu/entries/cellular-automata/supplement.html)

<center><img src="/img/Rule_3.png" ></center>
<center>Rule #3 olarak bilinen kurala gore olusturdugum Cellular Automata'nin ufak bir gorseli; sekli taniyanlar vardir belki, karsinizda Sierpiński Ucgeni </center>


* Bugunku [Leetcode challange](https://leetcode.com/explore/challenge/card/june-leetcoding-challenge/540/week-2-june-8th-june-14th/)'i aslinda cok zor degildi fakat test icin koyulan "edge case"'leri dikkate almadigim icin biraz ugrastirdi. Verilen iki string'den birini, digerinin icindeki karakterlerle sirali bir sekilde olusturabiliyor muyuz problemi. Problem ve cozumum asagida:

```
# LeedCode June Challange Day 9
# Is Subsequence Problem

# Given a string s and a string t, check if s is subsequence of t.

# A subsequence of a string is a new string which is formed from the original string
# by deleting some (can be none) of the characters without disturbing the relative
# positions of the remaining characters. 
# (ie, "ace" is a subsequence of "abcde" while "aec" is not).

# Example 1:

# Input: s = "abc", t = "ahbgdc"
# Output: true

# Example 2:

# Input: s = "axc", t = "ahbgdc"
# Output: false


def isSubsequence(self, s: str, t: str) -> bool:
	#check for empty string
    if(s == ""): return True
    i = 0
    j = 0

    # move index j until the end of the string t and stop when
    # all elements of s are found
    while(j < len(t) and i != len(s)):
        if(s[i] == t[j]):
            i += 1
        j += 1

    return (i == len(s))
```

* Bugun bir arkadasin yonlendirmesiyle dikkatimi ceken bir makalede, Facebook AI grubundan arastirmacilarin Python. C++ ve Java dillerini bir biri arasinda ceviren (transpiler) bir sistem gelistirdiklerini ogrendim: [arXiv link](https://arxiv.org/abs/2006.03511). Ustelik bunu "unsupervised" olarak yapmislar. Problemin ne kadar kazik olabilecegini hayal ederken makaledeki orneklere goz gezdirdigimde hakikaten cok etkileyici sonuclar elde ettikleri bir gercek. Baseline olarak kullandiklari piyasa standardi birkac ceviricinin performansini, en temel implementation ile sollamislar zaten. Birkac iyilestirme ile bunun epey uzerine cikmislar. Sistemin yaptigi hatalarin cogu da C++ ve Java konusunda compilation hatalari, gayet makul. Makaleyi bastan sona, ilgili prensiplerle anlatan [guzel bir Youtube videosu](https://www.youtube.com/watch?v=xTzFJIknh7E&feature=youtu.be) ile de bir suredir uzak kaldigim cesitli NLP yontemlerini de tekrar etmis oldum.

<center><img src="/img/2020_06_09_ML_traspiler.png" ></center>
<center>Modelin Python'dan C++'a yaptigi basarili cevirilerden birkac ornek... Kaynak: Marie-Anne Lachaux, et al., 2020 </center>

* **Bugun ogrendim ki** `scikit-learn`'deki tipik modelleri GPU gibi donanim hizlandiricilarinda, tensor operasyonlariyla etkili bir sekilde kullanmak icin Microsoft'un gelistirdigi **Hummingbird** adinda [bir proje](https://github.com/microsoft/hummingbird) varmis; arayuzu de epey kullanisli gorunuyor. Bunu mutlaka deneyecegim:

<center><img src="/img/2020_06_09_Hummingbird.jpeg" ></center>
<center>Hummingbird arayuzunde scikit-learn ile yazilmis bir Random Forest modeli GPU'da calistiriliyor </center>

* Python'da siklikla karsima cikan kavramlardan biri de **Decorators**. Bir fonksiyonu arguman olarak alip, turlu turlu isler yapmaya yarayan bu *meta-fonksiyon* kavrami konusunda Medium'da guzel bir yazi okudum: [Level up your code with Python decorators](https://towardsdatascience.com/level-up-your-code-with-python-decorators-c1966d78607) Kisaca anladigim en basit kullanim alani:
	
	- Eger bir fonksiyonun basinda, sonunda veya isleyisi sirasinda standart bir islem yapmasini istiyorsak ve bu sey baska fonksiyonlarla da kullanilacak jenerik bir sey ise (mesela logging, type checking vs), bir fonksiyonu parametre olarak alan meta bir fonksiyon tanimlayip, bunun icinde fonksiyonu cagirip, gerekli seyleri yapip sonucu donduruyoruz. Bu ozelligi kullanmak istedigimiz fonksiyonun da basina kullanacagimiz decorator fonksyinonu `@decorator_name` olarak belirtmemiz yetiyor.

	```python
	def logger(function):
		def new_function(*args):
			print("Execution started")
			result = function(*args)
			print("Execution ended")
			return result
		return new_function

	@logger
	def sum(x,y):
		return x + y
	```

* **Note to Self**: TO-READ: [Getting machine learning to production](http://veekaybee.github.io/2020/06/09/ml-in-prod/) and related [We are still in the steam powered days](https://vicki.substack.com/p/were-still-in-the-steam-powered-days) and [Attic ofBasement of Apps](http://veekaybee.github.io/2019/04/11/attic-compsci/)

* G. Strang [Matrix Methods in Data Analysis, Signal Processing, and Machine Learning](https://www.youtube.com/watch?time_continue=8&v=or6C4yBk_SY) dersinin ikinci dersinde 50 dakikada *sihir* yapip Lineer Cebir'deki en onemli matris ayristirma yontemlerinin uzerinden gecip, dersin sonunda *Fundemenetal Theorem of Linear Algebra* dedigi, bir matris ile iliskili dort temel uzayi ve bunlarin iliskilerini gosterdi.

	- Bir matrisin, satir x sutun seklinde ifade edilisine asinaydim fakat tam tersi olan sutun x satir'larin toplami olarak ifade edilmesi cok daha fazla bilgi barindiran bir gosterim sekli oldugunu anliyorum. Ornegin simetrik bir matrisi ortonormal eigenvectorler ve iliskili eigenvalue'larin carpiminin toplami olarak yazabiliyoruz ornegin (Bu acilimim S = Q λ Q^T olarak gosteriliyor ve **spectral decomposition** olarak adlandiriliyor.) Bu sekilde acilim, fizikte kuantum mekaniginde Hermitian operatorleri actigimiz baz vektorleri hatirlatti bana. Bu hafta buna dair detayli bir blog yazma karari aldim.

	- Ikinci onemli ayristirma ise, bir A matrisini, alt ucgensel (lower triangular) ve ust ucgensel (upper triangular) iki matrisin carpimi olarak yazabilmemiz. A matrisini sutun x satir olarak ifade ettigimizde, sutunlar L'nin sutunlarindan, satirlar da U'nun satirlarindan geliyor!

	- **Fundemental Theorem of Linear Algebra**:
		- m x n boyutlarinda r rank'a sahip bir A matrisi (ve transpozu A^T) icin:
			- sutun uzayi C(A) ve rank'i r
			- satir uzayi (ya da A^T'nin sutun uzayi) C(A^T) ve rank'i yine r
			- A'nin sifir uzayi N(A) (null-space)'in rank'i n-r
			- A^T'nin sifir uzayinin N(A^T) rank'i m-r
			- C(A^T) ve N(A) birbirine diktir
			- C(A) ve N(A^T) birbirine diktir

* Coursera'nin universite ogrencilerine yonelik yaptigi, [sertifikali kurslara ucretsiz kaydi saglayan kampanyasindan](https://www.coursera.org/for-university-and-college-students) yararlanip, birkac derse kaydoldum. Uzun zamandir dogru durust bir SQL dersi dinlemek istiyordum. Veri bilimi icin ozellesmis bir programi olan [SQL for Data Science](https://www.coursera.org/learn/sql-for-data-science) kursunda karar kilip, kollari sivadim. Ilk hafta guzel basladi; en temel konularin uzerinden yavas yavas gecilse de SQL'deki statement'larin temel syntax'inin uzerinden gectik. `SELECT`, `CREATE TABLE`, `CREATE TEMPORARY TABLE` ile SQL dunyasina "merhaba"!