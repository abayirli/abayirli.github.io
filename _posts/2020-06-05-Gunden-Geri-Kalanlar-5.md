---
title: Gunden Geri Kalanlar - 5
date: 2020-06-05
---

Tum bu notlari yazarken fark ettim ki, calistigim, okudugum, dinledigim bir seyin hemen ardindan 3-5 dakika ayirip, kendi cumlelerimle anladigimi/hissettiklerimi kaleme almak bircok seyin kafamda oturmasini ve kalicilasmasini sagliyor. Bundan sonra yorumlardan ziyade, biraz daha ogrendigim seylerin onemli noktalarini tekrar eder sekilde maddeler yazacagim: bunlar bazen kod parcalari, bazen bir denklem bazen kazik bir kavramin aciklamasi olacak. Blog yazisi gibi uzatmadan, kisa kisa, aklimda kaldigi kadariyla...

* Gunlerden en sevdigim gun: Udacity'deki Peter Norvig'in [Design of Computer Programs](https://classroom.udacity.com/courses/cs212) dersi gunu! Google Research direktoru, muthis karakter Peter Norvig'den programlama dersi alabilmek nasil bir ayricaliktir (hem de ucretsiz!). Neyse dersi ve Norvig'i ne kadar ovsem az; bugun ogrendigim birkac Python trick'ine gecelim.

* Python'da butun her seyin birer `object` olmasi fikrini acayip seviyorum. Boylece fonksiyonlar dahil butun herseyi bir yerden bir yere gonderebiliyorsunuz. Ornegin bir fonksiyonun ne kadar surede calistiginin istatistigini tutan bir fonksiyon yazacak olsak:

```
import time

def my_timeit(fn, *args):
	"""Calculates the result and runtime for a given function with arguments"""

	tick = time.time()
	result = fn(*args)
	tock = time.time()

	return result, round(tock - tick, 2)


def functime(n, fn, *args):
	"""Runs the given function for n times with a given arguments
	   and returns min, average and maximum run times
	"""
	times = [my_timeit(fn, *args)[0] for _ in range(n)]

	return min(times), average(times), max(times)
```

Kodun belirli bir kisminin ne kadar surede calistigini Python'daki **"Context Manager"** gibi biraz daha karmasik yapilarla da takip etmek mumkunmus. [Python in High Performance Computing](https://www.futurelearn.com/courses/python-in-hpc) dersinde gordugum ornekten:

```
from math import exp, sin
import time

class Timer:
    def __enter__(self):
        self.start = time.process_time()
        return self

    def __exit__(self, *args):
        self.end = time.process_time()
        self.interval = self.end - self.start

def calculate(a):
    result = 0
    for val in a:
        result += exp(val) * sin(val)
    return result

x = [0.1 * i for i in range(1000)]
with Timer() as t:
    for r in range(1000):
        calculate(x)
print("Time spent", t.interval)
```

Tabi bu isin en guzel yapilma sekli standart kutuphanedeki `timeit` [modulunu](https://docs.python.org/3/library/timeit.html) kullanmak. Ozellikle Jupyter Notebooktaki `%%timeit` magic'i epey kullanisli bir output veriyor:

```
In [1]: %timeit cos(0.2)
71.1 ns ± 1.57 ns per loop (mean ± std. dev. of 7 runs, 10000000 loops each)
```

* Python'un bir diger guclu ozelliklerinden biri **generators** kavrami. `for` dongulerinden ve gereksiz iteration'lardan etkili bir sekilde kurtulmanin en guzel yolu `generator` kullanmak. "List comprehension"'larin icinde kullandigimiz ifadeler de birer `generator` aslinda; ama bunlarin disinda ayrica da bir object olarak da tanimlayabiliyoruz ve istedigimiz zaman calistirabiliyoruz:

```
>>> gen = (item for item in [1,2,3,4,5,6] if item % 2 == 1)
>>> next(gen)
1
```

Generators kavramini anladiktan sonra ancak Python'daki for dongusunun nasil calistigini acikca anlayabiliyoruz:

```
my_list = [1, 2, 3]
for item in my_list:
	print(item)

#ustteki for dongusunun dengi asagidaki ifadeye karsilik geliyor

gen = iter(my_list)
try:
	while True:
		item = next(gen)
		print(item)
except StopIteration:
	pass
```

* Bir kodun icinde is yapan, bir takim "efficiency" ve "debugging" log'lari tutan farkli kisimlari birbirinde ayirmak olarak kabaca tanimlanabilecek **"Aspect Oriented Programming"** kavramiyla ilk defa karsilastim. Ornegin bir generator'de donguye kac defa girildigini, kac tane item donduruldugunun hesabini tutmak icin aralara sayicilar eklemek yerine soyle yeni bir `generator` tanimlanabilir; boylece isi yapan kod ile istatistikleri tutan kisim olabildigince ayrilmis oluyor (ekstra birkac ekleme disinda):

```
def c(sequence):
	c.start += 1
	for item in sequence:
		c.item += 1
		yield item

#usage:
for i c(sequence1):
	...
	for j in c(sequence2):
		...
```

* [Bugunku LeedCode Challange](https://leetcode.com/explore/challenge/card/june-leetcoding-challenge/539/week-1-june-1st-june-7th/3351/) biraz kazikti; daha dogrusu soruyu bence dogru duzgun formule etmemislerdi ya da benim anlayisimda bir sorun var. [Cozumunu internetten](https://www.youtube.com/watch?v=skkJtFzePwQ) baksam da hala kafamda soru isaretleri var; stokastik bir yontem nasil oluyor da fixed bir sonuc donduruyor, kafam basmadi bu ise, biraz daha dusunmek gerek sanirim. Bu arada cozumu izledigim elemanin Youtube kanalini epey sevdim, cok da guzel anlatiyor cozumleri; guzel bir referans kaynagi oldu elimde Leetcode soru cozumlerine dair. Problem asagida:

```
Given an array w of positive integers, where w[i] describes the weight of index i, write a function pickIndex which randomly picks an index in proportion to its weight.

Note:

    1 <= w.length <= 10000
    1 <= w[i] <= 10^5
    pickIndex will be called at most 10000 times.

class Solution:

    def __init__(self, w: List[int]):
        

    def pickIndex(self) -> int:
        


# Your Solution object will be instantiated and called as such:
# obj = Solution(w)
# param_1 = obj.pickIndex()
```

* Istatistik dersinin bu haftaki kisminin sonlarina dogru isin rengi baya bir degismeye basladi! Central Limit Theorem, Normal Distribution, z tablolari falan derken olay bir anda rastgele degiskenlerin dizilerinin yakinsama problemine donustu; gecmiste matematik bolumunden dinledigim olasilik/istatistik derslerinden kulak asinaligina (fakat pratigine kesinlikle degil) sahip oldugum bu kavramlar belli ki onemli bir yer kaplayacak ders boyunca. 

      <center><img src="/img/2020_06_05_Convergence.png" ></center>
      <center>Kaynak: MITx Fundementals of Statistics </center>

	- Bunun sebebi de donup dolasip aslinda istatistigin temel probleminin, bir populasyonun herhangi parametresini belirli bir hata ile hesaplayabilir miyim olmasi sanirim. Bunu da formule ederken rastgele degisken (ve fonksiyonlari) ile iliskili olasiliklarin N sonsuza giderken neye (ya da hangi dagilima) yakinsadiginin onemli olmasi. Asagidaki yakinsama turleri de bunlari gosteriyor: **almost surely**, **converges in probability** ve **converges in distribution**.

	- Matematik Bolumun'de yuksek lisansta bir sure takip ettigim Umit Islak hocanin Graduate Probability dersi gunlerim aklima geldi bu kadar matematige dalinca. Bu arada Umit Hoca yakin zamanda uzaktan verdigi dersleri ve ortaya karisik daha bircok konuda anlattigi dersleri kisa kisa [Youtube'a koymaya basladi](https://www.youtube.com/channel/UCUvzlb2B1TMQ1hz49BwE4PQ/videos). Matematiksel Istatistik'e giris serisini bi tekrar izlemek gerek...


