---
title: Merhaba Dünya!
date: 2019-06-02
---

Bilimsel hesaplama ve veri analizi konusunda biraz derinlere dalıp, bilgisayarın en alt seviyede nasıl çalıştığını anlama serüvenimde karşılaştıklarımı, klavyemin döndüğünce anlatmaya alışacağım blogun ilk yazısını 'Hello World!' diyerek açalım istedim. Programlama ile ilgili tüm derslerde, öğrenilen dilin temel syntax (sözdizimi)'ni ve temel programların yapısını göstermek amacıyla ekrana 'Hello World!' yazıp çalışmayı tamamlayan 'basit' bir programla başlanır, malum. Tabii, 'basit' kelimesi birçok konuda kullanılırken epey temkinli olunması gereken bir kelime, özellikle konu bilgisayar olunca... Bryant ve O'Hallaron'ın efsane **'Computer Systems: A Programmer's Perspective'** kitabında yaklaşık 40 sayfa boyunca anlatılan, C++ ile yazılmış bu basit programın arkadaki işleyişine dair birkaç şeyden bahsederek blogu açalım.

```
#include <iostream>
using namespace std;

int main(int argc, char** argv) {
	cout << "Hello World!" << endl; 
	return 0;
}
```
Üstteki kodda, temel input/output işlemleri için ```iostream``` kütüphanesini ekleyip, ```cout``` ile ekrana 'Hello World!' mesajını yazıyoruz. Kodu kaydettiğimiz hello.cpp dosyasını önce derleyip (compilation), ardından 'link' ediyoruz.

```bash
$ c++ -c hello.cpp -o hello.o
$ c++ hello.o -o hello
```
İlk satır, üstte bizim okuyabildiğimiz C++ kodunu, bilgisayarın anlayabileceği object code'a çevirirken, ikinci satırda ise çeşitli kaynaklardan gelen object code'lar çalıştırılabilir (executable) bir dosya oluşturmak üzere bir araya getiriliyor. Her ne kadar bizim durumumuzda link edilecek sadece bir dosya (hello.cpp) varmış gibi görünse de, bu aşamada linker'ın kodumuza eklediği tüm object code'ları listelemek için **ldd** komutunu kullanabiliriz:
```bash
$ ldd hello
	linux-vdso.so.1 (0x00007ffc7f7d7000)
	libstdc++.so.6 => /usr/lib/x86_64-linux-gnu/libstdc++.so.6 (0x00007fe30792a000)
	libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007fe307539000)
	libm.so.6 => /lib/x86_64-linux-gnu/libm.so.6 (0x00007fe30719b000)
	/lib64/ld-linux-x86-64.so.2 (0x00007fe307eb5000)
	libgcc_s.so.1 => /lib/x86_64-linux-gnu/libgcc_s.so.1 (0x00007fe306f83000)
```
Komutun çıktısı olarak elde ettiğimiz listede, yazdığımız kodun object kodu ile bir araya getirilen çeşitli **shared library (ortak kütüphane)**'leri, parantez içinde hafızadaki adresleri ile görüyoruz. Bunlar, arasında C standard library **libc.so.6** ve C standard math library **libm.so.6**'nın de yer aldığı, programın çalışması için gerekli birçok **shared library** bulunuyor. Bu kütüphaneler daha önceden derlenip oluşturulmuş birçok object code'un bir araya getirilip bir 'paket' halinde sunulduğu ve ihtiyaç halinde programlara eklenebilen kod parçaları gibi düşünülebilir. Ortak kütüphanelerin, bir diğer kütüphane türü olan **static kütüphanelerden** farkı, linking aşamasında çalışacak koda doğrudan kopyalanıp eklenmek yerine, kodun hafızada yer aldığı adrese bir pointer olarak eklenip, program çalışırken pointer'ın gösterdiği adres çözümlenerek ilgili kodun çalıştırılmasını sağlaması. Bu tip shared/static libary'leri oluşturmaya ilerleyen yazılarda muhtemelen daha detaylı değiniriz.

Bryant ve O'Hallaron kadar detaylı olmasa da, 'Hello World!' programının altta yatan 'karmaşıklığa' ufak çaplı bir bakış atmış olduk. Programın derlenip, link edildikten sonra CPU ve RAM'deki tüm işleyişine kadar tüm detaylar için meraklılara, bahsettiğim kitabın ilgili bölümünü okumalarını kesinlikle tavsiye ederim.

Bu ve ilerleyen yazılarda temel referans ve başucu kaynağı olarak  Boudreau & Swanson'ın **'Appplied Computational Physics'** kitabını kullanıyor olacağım.
