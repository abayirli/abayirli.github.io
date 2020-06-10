---
title: Hesaplama/Analiz Günlüğü - 1
date: 2019-12-02
---

![Kapak-1](/img/kapak_1.png) 


Son dönemde, araştırma, okuma, öğrenme ve bunları pratiğe dökme şeklinde geçen haftalardan geriye kalanları, yıldızlayıp ileride mutlaka geri dönmek istediğim şeyleri bir araya getirmek için ufak çaplı bir derleme hazırlamaya karar verdim. Başabildiğim takdirde hafta başlarında yayınlamayı planladığım bu derlemeler çoğunlukla **(bilimsel) programlama-hesaplama-analiz**, bir takım akademik motivasyon/üretkenlik temalı paylaşımlar ve kayda değer bağlantılardan oluşacak. Son zamanlarda CERN'deki işimde yoğun olarak uğraştığım **'İstatistiksel Veri Analizi'** ve **'Python'** özelinde yüksek performanslı hesaplama/yazılım mühendisliği temaları muhtemelen geniş yer kaplayacak, bunlarin yaninda benzer konularda kitap-video ders onerileri de olacak. Lâfı uzatmadan bu haftaki bağlantılara geçelim...
 
---------------------------------
## İstatistiksel Öğrenme - Veri Analizi ('Machine Learning')
 * Özellikle **yapay ogreme (machine learning)** işleriyle uğraşırken ilk etapta hızlı prototipleme için birçok noktasından feragat edilen fakat sonrasında işler **'deployment'** safhasına yaklaşırken gelen 'teknik borç' ile fazlasıyla başa bela olan kötü alışkanlıklara işaret edip, epey somut önerilerde bulunan harika bir yazı: [Coding habits for data scientists](https://www.thoughtworks.com/insights/blog/coding-habits-data-scientists)
 
 * Malum yeni moda "derin öğrenme" olduğundan, yapay zeka konusunda bugüne nazaran, geçmişte ilk zikredilen konulardan olan **'evrimsel yöntemler - genetik algoritmalar'** yöntemlerini yapay sinir ağları ile öğrenme problemine uygulayıp, üç temel örnekle süper anlaşılır anlatan bir yazı: [Evolving Neural Networks](https://towardsdatascience.com/evolving-neural-networks-b24517bb3701)
 
 * En popüler yapay öğrenme kütüphanelerinden biri olan **scikit-learn**'un core-geliştiricilerinden Andreas Müller ile güzel bir röportaj: [Want to Truly Master Scikit-Learn? 2 Essential Tips from Core Developer Himself](https://towardsdatascience.com/want-to-truly-master-scikit-learn-2-essential-tips-from-the-official-developer-himself-dada6ff56b99)
 
 * Yapay öğrenme yöntemlerinin **'kapalı-kutu'** olmaları sebepli tekrarlanabilirlik, yorumlanabilirlik gibi problemleri beraberinde getirmesi', fakat 'bilim camiasının' sihirli değnek bulmuscasina üzerine atlamasıyla tonla problemin gün yüzüne çıkışını etraflıca ele alan bir yazı: [Machine Learning Crisis in Scientific Research](https://towardsdatascience.com/the-machine-learning-crisis-in-scientific-research-91e61691ae76)
 * Derin öğrenmeden konu açılmışken,, son zamanlarda bu yöntemlerin fizik dahil olmak üzere birçok alanda 'devrimsel' sonuçları, kendi kendine evrenin sırlarını çözen yöntemler şeklinde lanse edilmelerine karşı kelimenin tam anlamıyla bir şövalye ruhuyla savaşan **Gary Marcus** (ve ortağı Ernest Davis)'in Nautulis'teki haklı tepkisel yazısı: ['Are Neural Networks about to Reinvent Physics](http://nautil.us/issue/78/atmospheres/are-neural-networks-about-to-reinvent-physics) [Aynı kişinin 'AI Hype' temasını etraflıca ele aldığı bir başka güncel yazısı 'The Batch'de: [An Epidemic of AI Misinformation](https://thegradient.pub/an-epidemic-of-ai-misinformation/)]
 
 * Hype demişken, 2019'da özellikle medya üzerinden büyük sansasyon şeklinde duyurulan birçok **machine learning/deep learning** gelişmesini, bir fizikçi sağduyusu ve kendine has yorumuyla ele alan güzel bir yazı: [AI update, late 2019 - wizards of Oz](https://blog.piekniewski.info/2019/11/18/late2019-the-wizards-of-oz/)
----------------------
## Hesaplama - Programlama
 * Birçok bilimsel hesaplama probleminin kalbinde yer alan **'optimizasyon'** konusuna etraflıca bir giriş niteliğinde, temel yöntemleri uygulamalarıyla sunup birçok kaynak paylaşan CERN'de geçen haftalarda "İstatistik-Veri Bilimi" seminer serisinden güzel bir konuşma (sunum PDF'si ve konuşması mevcut): [PHYSTAT Seminar: A general ıntroduction to continuous optimization](https://indico.cern.ch/event/839925/)
 
 * Yakın zamanda emekli olduğunu açıklayan, **Python'un 'mucidi' Guido van Rossum** ile Python dilinin güçlü yanları ve temel felsefesine dair bir röportaj: [The Mind at Work: Guido van Rossum on how Python makes thinking in code easier ](https://blog.dropbox.com/topics/work-culture/-the-mind-at-work--guido-van-rossum-on-how-python-makes-thinking)
 
 * Biraz daha **'yazılımcı' becerilerine** odaklanan, yazılıma ucundan bir şekilde dokunan kişilerin gelişimi için epey pratik önerilerin yer aldığı, **PyCon Africa 2019**'dan keyifli bir konuşma: [Standing out in a world of 20 million developers - Anthony (Youtube) Shaw](https://www.youtube.com/watch?v=I5rL9LrIp0c)
 
 * Yazılım becerileri demişken, eli-yüzü-düzgün yazılımlar geliştirirken göz önünde bulundurulması gereken birçok prensibi her zamanki gibi epey keyifli ve eğitici bir şekilde işleyen **Prisync** ekibinin yeni videosu: [SOLID Prensipleri](https://www.youtube.com/watch?v=URjGeK4xPzI) [Bu arada geçen haftaki bilgisayar mimarisi üzerine olan konuşma da tadından yenmiyor: [Bilgisayar Mimarisi](https://www.youtube.com/watch?v=AUmMqlwav5c)]
 
 * Programlama becerilerini geliştirip 'bir üst seviyeye' geçmek için, birçok yerde  genelde **açık kaynaklı bir projeye** katkı vermek önerilir. Fakat genelde epey olgunlaşmış, bir çok kişinin üzerinde paralel olarak çalıştığı, büyük bir 'codebase'e sahip bir projeye 'katkıda bulunmak' pek de 'çaylak dostu' bir şey değil. Tam da bu konuya kişisel hikayesi aracılığıyla değinen harika bir yazı: [My first contribution to open source: Impostor Syndrome](https://opensource.com/article/19/11/my-first-open-source-contribution-impostor-syndrome)
 * Son olarak Türkiye'deki Python ekosisteminin günden güne gelişiminin en somut göstergelerinden biri olan, **2020 baharında Boğaziçi Üniversitesi**'nde düzenlenecek [PyCon Turkey](https://tr.pycon.org/) konferans konuşma önerileri açılmış durumda. Paylasacaklariniz varsa 15 Ocak'i beklemeden konuşma önerinizi su adresten gönderebilirsiniz: [PyCon Turkey - Call for Proposals](https://www.papercall.io/pycon-turkey-2020) 
-----------------------
## Veri Bilimi - Akademi vs Gerçek Dünya
 
 * Bu bölümde istatistiksel veri analizinin akademik ortamın dışında **dışarıdaki dünyada (endüstri)** nasıl uygulandığı, ne gibi fark-benzerlikler olduğuna dair pratik yazılar olacak. Örneğin 'yüzyılın en seksi mesleği veri bilimi' yaklaşımını daha gerçekçi bir düzleme oturtan ve endüstride veri temelli bir projenin gelişiminda karşılaşılan (çoğu zaman sıkıcı) süreçleri çok güzel özetleyen bir yazı gibi: [Data Science iş Boring - Part I](https://towardsdatascience.com/data-science-is-boring-1d43473e353e) ve [Part - II](https://towardsdatascience.com/data-science-is-boring-part-2-d7c702422004)
 * Temel bilimler altyapısı endüstride birçok şirket için özellikle veri temelli projelerde büyük bir avantaj haline gelmiş durumda: 'büyük veri' daha büyük veri olmadan devasa veri ile her gün uğraşan parçacık fizikçileri için ise bu geçiş çok daha sürtünmesiz olabiliyor. Bu tip bir karar verdiyseniz tabii ki şirketler kucağını açmış sizi bekliyor olmayacak, birçok önhazırlık yapmak gerekiyor. Tüm bu sürecin bir parçacik fizikçisinin kendi deneyimlerinden yola çıkıp güzel bir şekilde özetlenmiş hali için: [How to Get a Job in Data Science](https://indico.in2p3.fr/event/19363/?fbclid=IwAR3_FZgQOpxanzIlCe_XsWXB38IW6ftwGhj3qPvJbACbN12Ea13hFP-AD14)
 -----------------------
## Motivasyonel
 * Akademik/teknik işler yapan herkesin başına bela bir problem: **"Imposter Syndrome"**. Becerilerinizi küçümseyip, aslında hiçbir şey bilmediğiniz ve birilerinin bir gün sizin 'sahtekarlığınizı' yakalayacağı üzerine patolojik fikirler silsilesi... Tüm bu düşüncelerin 'başarılı' kişiler tarafından dahi hissedildiğini ve üstesinden gelmek için olmasa da onunla huzurlu yaşayabilmek için yapılabilecekleri kendi hikayesi üzerinden anlatan harika bir TED konuşması: [How you can use imposter syndrome to your benefit](https://www.ted.com/talks/mike_cannon_brookes_how_you_can_use_impostor_syndrome_to_your_benefit)
 -------------------------
 ## Açık Veri Seti - Veri Analiz Yarışması
 
 * Önümüzdeki aylarda gerçekleştirilecek **'ML4Jets'** konferansı öncesinde, katılımcı ve konuyla ilgilenen herkese açık yeni bir veri seti ve yarışma duyuruldu. LHC deneyi ortamında temelde yeni parçacık sinyallerini, arka plandan ayırmaya yönelik önerilen bu 'challange'a dair detaylı bilgi için: [LHC Olympics](https://indico.cern.ch/event/809820/page/19002-lhcolympics2020)
--------------------------
## Kitap Önerisi
 * [The Hitchiker's Guide to Python - Best practices for development](http://shop.oreilly.com/product/0636920042921.do) (Kenneth Reitz and Tanya Schlusser, 2016): Python'un detaylarıyla birçok yönden 'olması gerektiği' gibi öğreten', geliştirme ortamını olusuturup birçok 'best practice' kullanarak doğru/düzgün kod yazmak için epey kompakt güzel bir kitap.
 ------------------------
## Video Ders Önerisi
 * Yapay öğrenme yöntemlerini hazır kütüphaneler kullanmadan temel Python ve numpy fonksiyonları ile sıfırdan inşa eden bir video serisi: [Machine Learning from Scratch (Youtube)](https://www.youtube.com/playlist?list=PLqnslRFeH2Upcrywf-u2etjdxxkL8nl7E)
-------------------------
## Eğlencelik
* Bültenin kapak resmini oluşturan ve çeşitli derin öğrenme problemlerinin parametre-loss uzaylarının 'sanatsal' gösterimlerinin yer aldığı harika bir site: [Loss Landscape](https://losslandscape.com)

