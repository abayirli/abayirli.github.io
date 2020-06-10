---
title: Hesaplama/Analiz Günlüğü - 2
date: 2019-12-09
---

![Kapak-1](/img/kapak_2.png) 


Son dönemde, araştırma, okuma, öğrenme ve bunları pratiğe dökme şeklinde geçen haftalardan geriye kalanları, yıldızlayıp ileride mutlaka geri dönmek istediğim şeyleri bir araya getirmek için ufak çaplı bir derleme hazırlamaya karar verdim. Başarabildiğim takdirde hafta başlarında yayınlamayı planladığım bu derlemeler çoğunlukla (bilimsel) programlama-hesaplama-analiz, bir takım akademik motivasyon/üretkenlik temalı paylaşımlar ve kayda değer bağlantılardan oluşacak. Son zamanlarda CERN'deki işimde yoğun olarak uğraştığım **'İstatistiksel Veri Analizi'** ve **'Python'** özelinde yüksek performanslı hesaplama/yazılım mühendisliği temaları muhtemelen geniş yer kaplayacak, bunların yaninda benzer konularda kitap-video ders önerileri de olacak.

Bu serinin ilk yazısını [blog arşividen](https://arifb.gitlab.io/blog/post/2019-12-01-hesaplama-analiz-gunlugu-1/) okuyabilirsiniz. Bu hafta içeriği biraz daha sadeleştirip, çok dağılmadan birkaç konu etrafında toplamaya, görsellerle biraz daha renkli hale getirmeye çalıştım. Bu haftaki bağlantıların çoğu **'yapay öğrenme (machine learning)'** ve **'derin öğrenme (deep learning)'** üzerine, ileriki haftalarda biraz daha farklı alanlara da dokunmayı umuyorum.
 
---------------------------------

## İstatistiksel Öğrenme - Veri Analizi - Yapay Öğrenme

Bu bölümde, bu hafta iki makaleye bağlantı vermeyi istiyorum. İkisi de epey pratik makaleler: biri temel bilimlerden biri de endüstride büyük ölçekli uygulamalardan.

![ML-1](/img/ml_physics.jpeg) 

Bunlardan ilki fizikle ilişkili bilimlerde yapay öğrenme yöntemlerinin nasıl kullanıldığına dair epey kapsamlı ve çok iyi yazılmış bir makale. Parçacık fiziğinde derin öğrenme çalışmalarına büyük katkı veren ve çalışmalarını yakından takip ettiğim Kyle Cranmer'in da yazarları arasında olduğu ve **parçacık fiziğinden, kozmolojiye, kuantum-çok parçacıklı sistemlerden materyal bilimine** kadar birçok alandaki uygulamalara değinen makale konuyla ilgili fizikçiler ya da fiziğe meraklı herkes için güzel bir tarama niteliği taşıyor: [Machine learning and the physical sciences](https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.91.045002) - [arXiv link](https://arxiv.org/abs/1903.10563)

![ML-2](/img/booking.png) 

İkincisi, Türkiye'den maalesef kullanamıyor olsak da dünya genelinde seyahat planlama konusunda çok popüler olan **Booking.com**'un, arka planda ekibin geliştirip üretimde kullandığı 150 modeli geliştirirken öğrendiği dersler şeklinde epey pratik noktalara değinen bir makale: [150 successful Machine Learning models: [6 lessons learned at Booking.com](https://www.kdd.org/kdd2019/accepted-papers/view/150-successful-machine-learning-models-6-lessons-learned-at-booking.com) Bir yapay öğrenme modelinin, araştırmanın ötesinde endüstriyel bir ortamda üretime konulması sürecinde yaşanılan birçok problem ve bunlara yönelik geliştirilen çözümleri birinci elden okumak epey aydınlatıcı oldu benim için. Endüstri ortamında olmasa bile, uygulamaya konulacak herhangi bir model geliştiren herkesin az çok göz önünde bulundurması gereken prensipler konusunda epey ilham verici noktalara değiniyorlar, mutlaka bir göz atın. Eğer okumaya zamanım yok derseniz de, yine bu konularda harika içerikler üreten **'Linear Digressions'** podcasti geçen hafta makaleyi kapsamlıca inceledi, oradan da dinleyebilirsiniz: [Linear Digressions - Lessons learned from doing data science, at scale, in industry](http://lineardigressions.com/episodes/2019/10/24/lessons-learned-from-doing-data-science-at-scale-in-industry)

Son olarak, geçtiğimiz haftalarda yayınlanan birkaç analize göre derin öğrenme odaklı birçok [akademik araştırma makalesinde](https://thegradient.pub/state-of-ml-frameworks-2019-pytorch-dominates-research-tensorflow-dominates-industry/), aynı zamanda [endustride veri bilimi temelli iş ilanlarında](https://towardsdatascience.com/the-most-in-demand-tech-skills-for-data-scientists-d716d10c191d) öne çıkmaya başlayan **PyTorch** kütüphanesinin geliştiricileri tarafından hazırlanan tasarım prensipleri ve birçok performans analizinin yer aldığı bir makale yayınlandı: [PyTorch: An Imperative Style, High-Performance Deep Learning Library](https://arxiv.org/abs/1912.01703) Tensorflow ve diğer birkaç alternatifine karşıt olarak 'pythonic' yaklaşımı vurgulanan bu kütüphanenin önümüzdeki günlerde daha da yuseklişini izleyeceğiz gibi duruyor. Bekleyelim ve görelim.

----------------------

## Hesaplama - Programlama
Bilimsel alanlarda uğraşılan problemlerin, veri setlerinin yazılım gereksinimleri ve ölçeklerinin hızlanarak büyümesi, buna ayak uydurmak konusunda epey hazırlıksız ve bana kalırsa bilinçsiz komunitenin yakın zamanda büyük problemler yaşayabileceği sinyallerini veriyor. Açık veri setleri, paylaşılan code-base'ler ile bir taraftan önemli ilerlemeler kaydediliyor olsa da, bu ölçekte etkili, tekrarlanabilir bilimsel araştırma ve hesaplama yapabilmek için bakış açısı değişikliği öneren, hayli kafa açıcı bir makale: [The industrialization of scientific research](https://blog.khinsen.net/posts/2019/10/29/the-industrialization-of-scientific-research/)

![ML-2](/img/best_practices.jpeg) 

Biraz geçmişe gidersek, üzerine kısa bir blog yazısı yazdığım ve bilimsel hesaplama konusunda **'iyi alışkanlıklara'** değinen güzel bir makaleyi eklemek istedim bu haftaki günlüğe. Makalede, bilimsel araştırmalar sırasında geliştirilen yazılımların herkesine faydasına olacak şekilde çok pratik öneriler yer alıyor: [Best Practices for Scientific Computing](https://www.google.com/search?client=ubuntu&channel=fs&q=best+practices+for+software+development&ie=utf-8&oe=utf-8) Makalenin yanında blog yazısını okumak için: [Aslinda Fizik - Haftanin Makalesi](https://aslindafizik.blogspot.com/2018/01/haftann-makalesi-i-best-practices-for.html)

Son olarak, Aralık ayı, malum yeni yıl yaklaşıyor. Batıda Christmas'ın yaklaşmasıyla geleneksel olarak yapılan bazı etkinliklerden internete yansıyanlardan biri 'Advent Calendar' etkinlikleri. Çeşitli temalar etrafında düzenlenen bu etkinliklerde 25 Aralık'a kadar her gün yeni bir içerik yayınlanıyor/paylaşılıyor. Bizim ilgi alanımıza giren ise birkaç yıldır devam eden ve gelenekselleşme yolunda ilerleyen **'Advent of Code'** etkinliği. Her gün birbirinden ilginç konseptlerde kimi zaman kolay, kimi zaman epey zorlayıcı programlama problemleri yayınlanıyor ve internet üzerinde birçok kişi bu 'challange'a ortak olup problemleri çözmeye çalışıyor. Problemlerin yer aldığı site: [Advent of Code 2019](https://adventofcode.com/) (Problemlere başka insanların yaklaşımlarını incelemek için Twitter/Youtube'da yayınlanan bir çok 'live-coding' videoları var, kendisi de bir veri bilimci olan [Joel Grus'un düzenli olarak yayınladığı videolarını](https://www.youtube.com/playlist?list=PLeDtc0GP5IClipbtVLCKWy2JlKTkp90e4) tavsiye ederim.)

-----------------------

## Motivasyonel
Bu haftaki motivasyonel videomuzun **Oxford Üniversitesi**'nden bir astrofizikcinin araştırma ve diğer birçok şeyle dolu 'tipik' bir gününün video-log'u. Kendisi aynı zamanda Youtube kanalında düzenli olarak popüler astronomi içerikleri de üreten **Dr. Becky** harika anlatım tarzı ile aktif bir bilim insanının çalışma hayatını ortaya koymuş. Gunlerinizin bu kadar verimli ve keyifli geçmesini dilerim :)

--------------------------

## Haftanin Podcast'i

İlk bakışta doğrudan bültenin konsepti ile ilişkili görünmüyor olsa da dinlerken her adımda, gittikçe karmaşıklaşan bir kod yaz yazma sureciyla fazlasıyla ilişki kurduğum, tüm çalışmalarını yakından takip ettiğim ekonomi-yazarı/BBC podcast-sunucusu **Tim Harford**'un yeni podcast yayını **Cautionary Tales**'ın üçüncü bölümü bu hafta için seçtiğim podcast yayını. Başlığı **'LaLa Land: Galileo’s Warning'** olan programda, bozulmaması için çeşitli önlemler alınan sistemlerin sırf bu yüzden dönüp dolaşıp bozulmaları konusu epey yaratıcı ve eğlenceli bir şekilde anlatılmış. Kendi yaptığım işlere dair epey güzel çıkarımlar elde ettim ben; bu amaçla olmasa da en baştaki Oscar Ödülleri galasindaki olayın hikayesi için dahi dinlemeye değer:  [Cautionary Tales Ep 3 – LaLa Land: Galileo’s Warning](http://timharford.com/2019/11/cautionary-tales-ep-3-lala-land-galileos-warning/)

--------------------------

## Kitap Önerisi

![Kitap-2](/img/smart_machines.jpg)

[How Smart Machines Think -Sean Gerrish, 2019](https://mitpress.mit.edu/books/how-smart-machines-think) : Bu hafta elime geçen ve hemen okumaya başladığım, Google'da yazılım mühendisliği yöneticisi Sean Gerrish'in yapay/derin öğrenme konusunda büyük bir açığı dolduran **'popüler-bilim'** seviyesinde kitabı. İçerisinde konuyu öğrenmek isteyenlere temel bilgilerin yanında, pratik olarak uğraşan kişilere, bu tip sistemlerin nasıl çalıştığına dair de epey önemli konulara değiniyor.
 

------------------------

## Video Ders Önerisi

**Yapay öğrenme** konusunda tipik online-eğitimlerin tersine teoriyi derslerin sonunda, pratik uygulamayı ise en başında yapan, PyTorch temelli kendi geliştirdikleri çok güçlü **fast.ai** kütüphanesi veri analizine kelimenin tam anlamıyla 'no-nonsense' bir giriş için ideal bir ders: [Practical Deep Learning for Coders](course.fast.ai) - fast.ai'in bu dersin bir sonraki aşaması olan derin öğrenme odaklı dersini bitirdikten sonra daha detaylı tanıtmayı planlıyorum.

-------------------------

## Eğlencelik
![Eglencelik-2](/img/eglencelik_2.png) 


