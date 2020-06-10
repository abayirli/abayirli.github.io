---
title: Hesaplama/Analiz Günlüğü - 3
date: 2019-12-16
---

![Kapak-1](/img/kapak_3.png) 


Son dönemde, araştırma, okuma, öğrenme ve bunları pratiğe dökme şeklinde geçen haftalardan geriye kalanları, yıldızlayıp ileride mutlaka geri dönmek istediğim şeyleri bir araya getirmek için ufak çaplı bir derleme hazırlamaya karar verdim. Başarabildiğim takdirde hafta başlarında yayınlamayı planladığım bu derlemeler çoğunlukla (bilimsel) programlama-hesaplama-analiz, bir takım akademik motivasyon/üretkenlik temalı paylaşımlar ve kayda değer bağlantılardan oluşacak. Son zamanlarda CERN'deki işimde yoğun olarak uğraştığım **'İstatistiksel Veri Analizi'** ve **'Python'** özelinde yüksek performanslı hesaplama/yazılım mühendisliği temaları muhtemelen geniş yer kaplayacak, bunların yanında benzer konularda kitap-video ders önerileri de olacak.

Bu serinin [ilk](https://arifb.gitlab.io/blog/post/2019-12-01-hesaplama-analiz-gunlugu-1/) ve [ikinci yazısını](https://arifb.gitlab.io/blog/post/2019-12-01-hesaplama-analiz-gunlugu-2/) blog arşividen okuyabilirsiniz. Bu hafta biraz daha kompakt bir bülten oldu; temel temamız yapay öğrenme temelli modellerin uygulamaya geçirilmesi, yani **'deployment'**. Bilimsel hesaplama tarafında epey güzel, pratik kaynaklara da yer vermeye çalıştım. Bültenden yararlanıyorsanız görüşlerinizi, önerilerinizi arif.bayirli@cern.ch adresinden bana ulaştırabilirsiniz. İyi okumalar!
 
---------------------------------

## İstatistiksel/Yapay Öğrenme - Veri Analizi

![ML-1](/img/technical_dept3.png) 
Bu bölümde, bu hafta da biri endüstriden birisi de temel bilimlerde **istatistiksel öğrenme** yöntemlerinin kullanıldığı iki makale yer alıyor. Bir de elbette gecen haftaki **NeurIPS** konferansına kısaca değinmeden geçmiyoruz.

Birinci makale, yapay öğrenme temelli bir projenin gelişim sürecinde, verinin elde edilmesinden modelin ortaya konulup sonunda uygulamaya geçirilip, performans testlerine kadar tüm süreçleri ele alıyor. Bu sureçlerdeki kritik risk faktörlerinin yazılım geliştirme ortamlarında çokça kullanılan **'technical dept'**, yani sonradan ödemeniz gereken (ağır) bedele benzer şekilde bir yük getirdiği üzerine **Google mühendis/araştırmacılarından** epey kapsamlı bir makale sunmuşlar: [Hidden Technical Dept in Machine Learning Systems](https://papers.nips.cc/paper/5656-hidden-technical-debt-in-machine-learning-systems.pdf)


İkinci olarak; bilişsel bilimler alanında araştırmacıların özellikle hayvan davranışlarını daha iyi anlamak için denekleri takip etmek ve davranışlarını modellemek amacıyla, geleneksel yöntemlerle büyük ölçekte gerçekleştirilmesi zor işleri **yapay öğrenme** yöntemleri ile başarabiliyorlar. Bilim haberciliğinde çok kaliteli işler çıkartan **Quanta Magazine**'de geçen hafta yayınlanan yazıda, kullanılan bazı yöntemlere ve çalışmaların detaylarına harika görseller ve videolar eşliğinde yer veriliyor. Bazılarını ağzım açık kalarak izledim: [To Decode the Brain, Scientists Automate the Study of Behavior](https://www.quantamagazine.org/to-decode-the-brain-scientists-automate-the-study-of-behavior-20191210/)

![ML-2](/img/swarm.png) 

Son olarak, geçtiğimiz hafta Kanada'da düzenlenen ve yapay öğrenme konusunda en etkili ve en çok katılımcı çeken **NeurIPS 2019** konferansı tamamlandı. Tüm dünyadan konuyla ilgili 'cutting-edge' çalışmaların sunulduğu konferansta geçen yıl olduğu gibi bu yıl da fizik ve fizikle ilişkili temel bilimler temalı ayrı bir oturum yapıldı: [Machine Learning and Physical Sciences](https://ml4physicalsciences.github.io/) Henüz konuşmaların üzerinden geçme fırsatım olmadı, muhtemelen önümüzdeki haftadan itibaren gözüme çarpan birkaç tanesini detaylıca paylaşırım. Fırsatı olanlar, bu oturumu ve konferanstaki tüm oturumları yayınlanan videolardan inceleyebilirler:[NeurIPS videos](https://slideslive.com/neurips#!feed=latest)

----------------------

## Hesaplama - Programlama
Bilimsel hesaplama alanında C++ gibi derlenen diller, Python gibi 'interpret' edilen dillere göre performans açısında daha çok tercih ediliyor. Fakat bu demek değil ki Python kodunuzu ibr takım değişikliklerle hayli hızlı ve yüksek performanslı calistiramazsiniz. Özellikle Numpy, Dask ve benzeri kütüphanelerin yardımı ve bir takım kullanışlı yöntemlerle çok pratik örnekler eşliğinde önerilere yer veren bir konuşma: [Performance Python: Seven Strategies for Optimizing Your Numerical Code](https://www.youtube.com/watch?v=zQeYx87mfyw)

Biraz eskilere gidip, 'yıllanmış' makalelerden birine değinmek gerekirse; özellikle günümüz bilgisarlarının **çok çekirdekli**, **karmaşık ön-bellek (cache)** hiyerarşili, paralel hesaplama temelli yapıları göz önüne alındığında iyi bir programcının, özellikle yüksek performanslı işler yapanların, elinin altindakinin tüm imkânlarından yararlanabilmek için işlemci, hafıza vb. konularda hayli bilgili olması gerekiyor. Bu haftaki makale özellikle işlemci (CPU) ön-bellek ve RAM organizasyonu üzerinden çok değerli bilgiler veriyor: [What Every Programmer Should Know About Memory](https://people.freebsd.org/~lstewart/articles/cpumemory.pdf) 

![Hesaplama-1](/img/memory.png) 

Yazdığımız kodu optimize etme demişken, geçen günlerde Twitter'da rastladığım bir yazıyı da paylaşmadan edemedim: [How to Make Your Code Run Faster](https://brohrer.github.io/code_optimization.html) Çok temel yöntemleri kısa-kısa sıralayıp güzel bağlantılar veriyor; bunlardan bir tanesi dahi kodunuzun çalışma süresini dramatik bir şekilde hızlandırmaya yetebilir.


-----------------------

## Haftanin Gorseli

Her hafta, o haftanın içeriğinden öne çıkan, vurucu bir görsel ya da içeriği bu bölümde paylaşmaya karar verdim. Bu haftaki görsel, üstte yapay öğrenme kısmında değindiğim Google makalesindeki süreçleri özetleyen ve yapay öğrenme kod geliştirme sürecinin tüm sistemin ne kadar küçük bir kısmını kapladığını dramatik olarak gösteren bir görsel.

![Gorsel](/img/gorsel_3.png) 

-----------------------

## Motivasyonel
Bu hafta, biraz sistem eleştirisi şeklinde, her argümanıyla 'evet ya, kesinlikle' demekten kendimi alamadığım güzel bir makale paylaşmak istiyorum. **'İyi' bir eğitimin kazandırdığı 'toksik' becerilerden biri olan 'test/sınavları hack edebilmek' ve bunun trajik sonuçları üzerine** Paul Graham'in son yazısı: [The Lesson to Unlearn](http://paulgraham.com/lesson.html)

--------------------------

## Haftanin Podcast'i

Bu haftaki tema paralelinde podcast önerim, yapay öğrenme temelli istatistiksel modellerin uygulamaya konma ve sonrası, yani **operasyon** aşamasında devreye giren süreçleri güzel bir şekilde özetleyen her bölümünü keyifle ve yepyeni şeyler öğrenerek dinlediğim **Data Skeptic**'in güzel bir bölümü: [ML Ops](https://podbay.fm/podcast/890348705/e/1574842694) Yazılım geliştirme süreçlerini günümüzde şekillendiren **DevOps** uygulamalarının, gereklilikler ve uygulama ortamları konusunda farklılıklar gösteren yapay öğrenme süreçlerine nasıl entegre edildiğini epey pratik örneklerle özetliyor, meraklısına önerilir.

--------------------------

## Kitap Önerisi

![Kitap-2](/img/kitap_3.jpg)

[Effective Computation in Physics - A. Skopatz, K. D. Huff, 2015](http://physics.codes/) : Bilimsel araştırma sürecinde Python ile "oyuncak kod" yazmayı bırakıp "yazılım geliştirme" boyutunda tekrar edilebilir, version control'lü, testing/debugging/documenting temelli kod yazmaya. Hem de sıfırdan adım adım...

------------------------

## Video Ders Önerisi

![Python-1](/img/python_oop.png)

Python'u öğrenmek istediğinizde internette tonla kaynak var artık. Fakat tipik olarak bunların hemen hemen hepsi giriş seviyesinde ve işler tam karmasiklasmaya başladığında, işin içine 'exception'lar, 'object-oriented concept'ler girmeye başladığında bitiveriyorlar. Python ile başlangıç seviyesinde bir adım ileriye gitme konusunda zamanında takip edip epey yararlandığım Udemy'de güzel bir dersi tavsiye edeceğim bu hafta: [Python Beyond the Basics - Object Oriented Programming](https://www.udemy.com/course/python-beyond-the-basics-object-oriented-programming/) - her ne kadar ders biraz geçmiş tarihli olması nedeniyle Python 2 temelli olsa da, içerik ve anlatım tarzı olarak epey etkili olduğunu düşünüyorum.

-------------------------

## Eğlencelik
![Eglencelik-3](/img/eglencelik_3_2.jpeg)


**Verimli haftalar!**
