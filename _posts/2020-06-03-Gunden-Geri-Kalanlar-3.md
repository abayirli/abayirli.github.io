---
title: Gunden Geri Kalanlar - 3
date: 2020-06-03
---
* Bugun biraz programlama agirlikli gecen bir gundu; uzerine tekrar amacli yeni basladigim Istatistik dersi ve Python ile ilgili izledigim videolarin gunun one cikanlari oldu.

* [Accelerated Computer Science](https://www.coursera.org/learn/cs-fundamentals-2) dersinde bu hafta `Tree` veri yapilari isledik; uzun zamandir benim icin epey mistik gorunen seylerin bir anda gozumun onunde aydinlanmasi deneyimi yasadim resmen. Machine learning'de surekli karsima cikan 'acyclic computational graph' kavramindan, cebirsel bir islemi encode etmenin yontemine kadar bircok guzel ornekle anlatti dersi veren kisi de. 
	- `LinkedList`'ten sonra epey bir kafama oturdu `Tree` yapilari...
	- Sonrasinda `BinaryTree` yapisi uzerinde durup bir `Dictionary` ile `key`-`value` ikililerini bir tree icerisine yerlestirip. etikili bir sekilde arama yontemleri uzerinde durdu. 
	- "pre-order", "in-order" ve "post-order" yontemleri ile bir tree'yi nasil traverse edebilecegimi ogrendim. Artik kimse "bir tree'yi traverse edemiyorum" diye beni sorgulayamayacagi icin de mutluyum! :)

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Google: 90% of our engineers use the software you wrote (Homebrew), but you can’t invert a binary tree on a whiteboard so fuck off.</p>&mdash; Max Howell (@mxcl) <a href="https://twitter.com/mxcl/status/608682016205344768?ref_src=twsrc%5Etfw">June 10, 2015</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

* Bugunun LeetCode Challange'i **"Two City Scheduling"** adli bir "optimizasyon" [problemiydi](https://leetcode.com/explore/challenge/card/june-leetcoding-challenge/539/week-1-june-1st-june-7th/3349/). Algoritma konusunda epey bir kafa yormam gerekti, internetten de cozume dair bir ipucu alarak cozmus olsam da yine de epey sey ogretti. Problem ve kendi cozumumum asagida:

```
# LeedCode June Challange Day 3
# Two City Scheduling Problem
#
# Definition:
# There are 2N people a company is planning to interview. 
# The cost of flying the i-th person to city A is costs[i][0], 
# and the cost of flying the i-th person to city B is costs[i][1].
#
# Return the minimum cost to fly every person to a city such that
# exactly N people arrive in each city.

def twoCitySchedCost(costs):
	n = int(len(costs)/2)
	cost_diff = sorted(costs, key = lambda k: abs(k[0] - k[1]), reverse = True)

	sum_cost = 0
	n0, n1 = (0,0)
	k = 0
	while(k < 2*n):
		t0 = cost_diff[k][0]
		t1 = cost_diff[k][1]

		if((t0 <= t1 and n0 < n) or n1 == n):
			sum_cost += t0
			n0 += 1
		else:
			sum_cost += t1
			n1 += 1
		k += 1
	return sum_cost
```

* Gunun highlight'larindan biri de uzun suredir kullandigim **SublimeText** editorunun [kisa yollarini](https://shortcutworld.com/Sublime-Text/linux/Sublime-Text_Shortcuts) etraflica ogrenmek oldu. Uzerine bir de C++ ve Python icin otomatik tamamlama yapan, parantezleri kontrol eden vs. eklentileri ekleyince sahane oldu!

* MIT'nun edX'de yeni yayinladigi ["Fundementals of Statistics"](https://www.edx.org/course/fundamentals-of-statistics) dersi cok iyi basladi. Tarihin tozlu raflarindan kalmis istatistik derslerinden farkli olarak, epey "modern" bir yaklasimi var dersin ve ve dersi veren kisinin. Ilk derste istatistik ve olasilik arasindaki iliskiyi anlatirken soyledigi sey epey hosuma gitti: **"Statistics is reverse-engineered probability"**. Derste istatistik-olasilik-modelleme konusundan bahsederken kullandigi asagidaki slaytta cok guzel ozetlemis olayi gercekten.

![MIT_Stats](/img/mit_stat_week1.png) 

* Python tarafinda birbiriyle iliskili iki guzel videoda Python'da ozellikle **"list comprehension"** gibi ifadelerin aslinda arka tarafta nasil calistigi ve normal `for` dongulerinden nasil daha efficient olduklarina sahit oldum. Her hafta basinda posta kutuma dusen muthis bulteninden tanidigim  Reuven Lerner'in su iki videosu bahsettigim:
	- [Python's list comprehensions vs. "for" loops — behind the scenes](https://www.youtube.com/watch?v=KnJPJxqmPrA&feature=youtu.be)
	- [How efficient are Python's generator expressions?](https://www.youtube.com/watch?time_continue=22&v=dOhDmHjK5PM&feature=emb_logo)

* Bu arada yukaridaki videoda da gecen, Python'daki `dis` modulu bir fonksiyonun nasil calisitigna dair nasil inanilmaz bir insight sagliyor oyle...

* Ayni konuyla iliskili, ayni kisinin ['Ace Python Interviews'](https://lerner.co.il/2019/12/23/ace-python-interviews-a-new-free-course-to-help-you-get-a-better-job/) adinda harika bir ucretsiz dersi bulunuyor; baslangic seviyesinden ileri seviyeye kadar 50 soru uzerinden video ile cozumleri gosteriyor. Bunlara ek bir de [Youtube'da Python'un standart kutuphanesini anlattigi bir listede](https://www.youtube.com/playlist?list=PLbFHh-ZjYFwErD9ICH42MPeT8PQuzIj56) ufak guzel videolar var.

* Python konusunda bugun izledigim bir **PyCon 2020** konusmasinda **Python Runtime**'i anlatiyordu. Program calisirken cesitli fonksiyon cagirilari yapildiginda arka planda olusuturulan stack frame'ler ve bunlarin yapisi, icinde saklanan bilgilere deginen guzel bir konusmaydi. Sonlara dogru epey bir detaya girse de en azindan ufak bir hatada dahi cikan "**stack trace"** mesajlarinin arka tarafta nasil olusturulduguna dair bana epey fikir verdi: [Elizaveta Shashkova - The Hidden Power of the Python Runtime](https://www.youtube.com/watch?v=yr6E7FwK_Hw&t=1095s)

* Twitter'da bugun denk geldigim bir yazi:, yazilimci **Elif Kus**'un ["4 Buyuk" teknoloji deviyle mulakatindan nasil "red yedigi"nin hikayesi](https://elifk.us/dort-buyukten-nasil-red-aldim/). Tum bu zorlu sureclere dair guzel noktalara deginmis; boylesi kisisel "negatif deneyimler" ne kadar da degerli...

* Bir de dun onemli bir is gorusmesi yapacagim demistim; epey guzel gecti ilk gorusme. Gorustugum kisinin isin tanimini dahi anlayamayan HR elemani degil de Istatistik PhD'li biri olmasi sebebiyle 45 dakika boyunca bol bol teknik konulari rahatca konusabildigim, kendimi ifade edebildigim bir gorusme oldu. Bir sonraki asama departman yoneticisi ile benzer bir teknik gorusme, sonrasinda somut bir proje odevi olacak. Umutluyum!

* Son olarak da, konu disi, gecen aksam ufak teleskop ve cep telefonu kombinasyonumla arka bahceden cektigim Ay fotografini suraya birakayim:
 
 ![Ay_Foto](/img/Ay.jpeg) 