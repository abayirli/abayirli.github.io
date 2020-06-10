---
title: Gunden Geri Kalanlar - 2
date: 2020-06-01
---

Aralikli olsa da gunden geri kalanlari paylasmaya devam edelim. Bugun, uzun zamandir ogrenmeye niyetli oldugum birkac seye egilme firsatim oldu...


* Bir suredir cesitli programlama problemleri cozerken gittikce daha da fazla ihtiyacini duymaya basladigim, uzun zamandir sadece `print` statement'lar ile 'gunu kurtardigim' gercegini asmak adina, sonunda en temelinden "debugger" kulllanmayi ogrenmeye karar verdim. Ilk olarak C++ iicn kullanilan `gdb`'ye biraz goz atip, Youtube'de Hintli bir arkadasin 12 dakikada onemli hemen herseyini uygulamali anlattigi [video](https://www.youtube.com/watch?v=J7L2x1ATOgk) epey isimi gordu. `breakpoint` olusturmadan, `stack frame` kavramina her seyi super ozetlemis videoda. Yillardir aklimda neredeymis diye kendime sorup durdum. Ardindan `gdb`'nin Python muadili `pdb`'ye gectim. Real Python'un her zamanki gibi harika hazirlanmis [tutorial'larindan birini](https://realpython.com/python-debugging-pdb/) takip edip yine yaklasik 20 dakikada bu debugger da cepteydi. Ustelik iki debugger arasindaki benzerlik isim benzerliginin isaret ettigi uzere, ust duzeyde. Bundan sonrasini zorlu 'bug'lar dusunsun!

* Haziran ayinin baslamasiyla, bir suredir problem cozme egzersizleri yaptigim [LeetCode'da June 2020 Challange](https://leetcode.com/explore/challenge/card/june-leetcoding-challenge/!) basladi bugun itibariyle. Sitede her gun yeni bir algoritma problem yayinlaniyor ve ucretsiz olarak bunu cozup sisteme gonderebiliyorsunuz. Cozumleri de yayinliyorlar ama onlar 'Premium' uyelere ozel. Bugunku problem, verilen bir `binary tree`'yi tersine cevirmek seklindeydi. Ufak bir `recursive` trick ile kolaylikla problemi cozdum. `Tree` yapilarini cok tanimiyor olsam da problem sayesinde ufak bir arastirma da yapmis oldum. Yarindan itibaren muhtemelen LeetCode'a Premum uyeligi de yapip hem cozumlere hem de ekstra kaynaklara da ulasmayi planliyorum. Problem ve cozumu surada:

```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def invertTree(self, root: TreeNode) -> TreeNode:
        if(root):
            if(root.right != None or root.left != None):
                temp = root.right
                root.right = root.left
                root.left = temp
            self.invertTree(root.right)
            self.invertTree(root.left) 
        return root
```        
        
* Coursera'da takip ettigim ["Accelerated Computer Scince"](https://www.coursera.org/specializations/cs-fundamentals) specialization'in ikinci dersinin bu haftaki projesi epey kallavi bir `Linked List` problemi uzerniyedi. Verilen siralanmis bir `linked list`'e sirayi bozmayacak sekilde yeni bir `node` eklemek ve verilen sirasiz bir listeye `merge sort` ile siralamak seklinde iki problemden ilkini cozdum, ikincisi ilerleyen gunlerde ellerimden oper...

* Bugun Real Python'un podcast yayininda, gecenlerde [PyCon 2020 konusmasina](https://www.youtube.com/channel/UCMjMBMGt0WJQLeluw6qNJuA) denk geldigim Anthony Shaw konuktu: [Episode 11: Advice on Getting Started on Testing with Python](https://realpython.com/podcasts/rpp/11/). Konu bu sefer `pytest` modu ve genel olarak test kavramiydi. "Production level kod" olayinin onemli bir parcasini olusturdugunu sezinledigim test kavramina dair epey guzel noktalara degindiler programda. "Test coverage", "continous integration" vs. gibi kavramlar da cabasi.

* Ogrendigim programlama becerilerini "pratige" dokmenin en guzel yolu muhtemelen acik kaynak bir projeye katki koymak diye dusunuyorum. Bunun icin sonunda kollari sivadim. Tabi bu kararimda, Columbia'dan derslerini takip ettigim Andreas Mueller'in gecen gunler yayinladigi [genel tanitim videosu](https://www.youtube.com/watch?v=5OL8XoMMOfA) ve bunlarin somut olarak uygulandigi `scikit-learn`'e ilk contribution nasil yapilir temali [video](https://www.youtube.com/watch?v=PU1WyDPGePI) epey bir etkili oldu. Ben de son zamanlarda en cok kullandigim ve ic isleyisini ogrenmeye can attigim `scikit-learn` ve `numpy` kutuphanelerine mutevazi de olsa katki koymak icin fork'larimi yaptim, kendime issue secmeye basladim. Ilk basta dokumantasyonla ilgili de olsa ufak bir katki ile baslamayi umuyorum, bakalim.

* Iki takip edilesi online ders:
	- [MIT Fundementals of Statistics](https://www.edx.org/course/fundamentals-of-statistics) - epey saglam duruyor; duzenli odevlerle takip etmeyi dusunuyorum.
	- [Practical Python Programming](https://dabeaz-course.github.io/practical-python/) - sifirdan gorunse de epey saglam bir alt yapi kuran, web tabanli, bol uygulamali, odevli bir ders. Ufak ufak ilerlemeyi planliyorum.

* Agustos ayinda Ingiltere'de (uzaktan) katilacagim bir egiitim programi var [Science to Data Science (S2DS)](http://www.s2ds.org/) adinda; bilim PhD'lilere sektorde olanaklar yaratmak konusunda danismanlik yapip, egitimler yapiyorlar. Bes haftalik programin ilk duyurulari bugun e-posta kutuma geldi. Slack kanalina uyeligimizi yaptik, Github hesaplarimizi verdik, bir sonraki asamayi bekliyoruz. Program kafamda bir suredir sekillendirdigim bilimden, veri bilimine gecisim konusunda epey etkili olacagini dusunuyorum, bakalim gorecegiz...

* Yarin, korona mevzulari nedeniyle bir suredir pek gerceklesmeyen is gorusmelerinden birini yapacagim Almanya Munih'ten epey buyuk bir sigorta sirketinin "Data Scientist" pozisyonu icin. Bu ilk gorusme olacak fakat ilk gorusmeyi direkt "Head of Data Science" bir istatistik PhD'li, universitelerde ders veren bir amca ile yapmak gozumu korkutmuyor degil. Fingers crossed!