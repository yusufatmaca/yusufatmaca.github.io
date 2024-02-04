---
layout: post
title: "Markdown'a Ufak Bir Giriş"
---

Markdown bir işaretleme dilidir (ing: markup language). İşaretleme dillerinin amacı bir dizi tanımlanmış kodlar sayesinde metni manipüle etmek, biçimlendirmek ve bağlantılar kurmaktır. [[1]](https://en.wikipedia.org/wiki/Markup_language?useskin=vector)

Yaygın kullanılan işaretleme dillerinden bazıları; TeX, LaTeX, Markdown ve HTML’dir. Bu dil ailesinin üyelerine işaretleme dili denmesinin sebebi; eskiden, el yazmalarına, zamanının editörlerinin kalemle düzeltme talimatlarını işaretlemesinden (marking up) kaynaklanmaktadır. [[2]](https://en.wikipedia.org/wiki/Markup_language?useskin=vector)

İşaretleme dilleri hakkında temel bilgileri öğrendikten sonra, Markdown’ı kullanmaya başlayalım.

Bir rapor hazırladığımızı varsayalım. Boş bir sayfamız var ve genelde işe raporumuzun başlığını yazarak başlarız. Öyleyse ilk etiketimizi tanıtalım:

`#` etiketi ile başlıklar oluşturabiliyoruz. Büyükten küçüğe doğru 6 farklı başlık tipimiz var. Markdown’da başlık büyüklüğünü, #etiketinden kaç tane kullandığımız belirliyor. Etiket sayısı ne kadar fazlaysa, başlık o kadar küçük demektir. Yani etiket sayısı ile büyüklük arasında bir ters orantı var.

```
# Başlık 1
## Başlık 2
### Başlık 3
#### Başlık 4
##### Başlık 5
###### Başlık 6
```
<script src="https://gist.github.com/yusufatmaca/b1d559f70df88c26a9a853894b870d0c.js"></script>

Bir metinde ana başlık bir tane olacağı için, 1 numara büyüklükteki başlıklardan metinlerde yalnızca bir tane olması tavsiye ediliyor. Bizim örneğimizde, rapor başlığımızın 1 numara büyüklük ile yazılması, alt başlıkların ise belirli bir hiyerarşiyi takip etmesi doğru olacaktır.

---

Başlığımızı oluşturduk ve metni yazmaya koyulduk. Vurgulamak istediğimiz bazı kelimeler muhakkak olacaktır. Kalın (bold) ve/veya eğik (italic) vurgulamalar kullanabiliriz.

Metni iki adet yıldız `(**)` etiketi ile boşluksuz sararak kalın, bir tane alt çizgi `(_)` etiketi ile sararak eğik, hem iki tane yıldız hem de bir tane alt çizgi ile aynı anda sararak hem kalın hem eğik yapabiliriz.

```
**kalın yazı**
_eğik yazı_
**_hem kalın hem eğik yazı_**
```
<script src="https://gist.github.com/yusufatmaca/0abc58e5f983899beaa04d1ebd6b4b78.js"></script>

---

İşaretleme dillerinde işler etiketler yoluyla yürür. İç içe geçmiş şekilde birden çok etiket kullanınca okunurluğu (readability) artırmak için girintiler, boşluklar ve çoklu satırlar oluşturabiliriz. Bu okunabilirliği artırıyor fakat bir dezavantaja sahip: alt satıra geçmek. Bir örnek üzerinde anlatayım.

```
Lorem ipsum
**dolor _sit amet_, consectetur
adipiscing** elit.

Lorem ipsum  
**dolor _sit amet_, consectetur  
adipiscing** elit.
```

<script src="https://gist.github.com/yusufatmaca/125bf21a007ac0127dca531f486fc4bf.js"></script>

İki örnek de aynı şekilde yazılmış gibi gözükmesine rağmen çıktıları (output) farklı. Sebebini öğrenelim.

İkinci örnekte, “Lorem ipsum” ve “dolor sit amet, consectetur” cümleciklerinden sonra minimum iki boşluk bıraktıktan sonra alt satıra geçiyoruz. Markdown’da, bu boşluğun okunabilirliği artırmak amacıyla değil, yeni bir satıra geçmek için olduğunu böyle belirtiyoruz.

---

Metnimize başlıklar ekledik, yazılarımızı kalınlaştırdık, eğdik, yeni satıra sıçradık. Şimdi sıra geldi belgemize bağlantılar eklemeye.

Bağlantı ekleyebilmek için köşeli parentezler arasına yönlendirme ekleyeceğimiz metni, sonrasında ise normal parantezler arasına gitmek istediğimiz bağlantıyı yazıyoruz.

```Markdown
[Benim kişisel web sayfam](https://yusufatmaca.github.io)
```

<script src="https://gist.github.com/yusufatmaca/ddabe6471092b3970b3a8939575f9e3a.js"></script>

---

Resimleri de aynı şekilde tanıtıyoruz fakat bir farkla, en başa, yani köşeli parentezlerin önüne bir ünlem işareti (!) ekleyerek. Burada şunu sorabilirsiniz: resim eklerken köşeli parentezler arasına neden resim ile ilgili açıklama yazıyoruz, gözükmeyecek ki! Şöyle açıklayabilirim:

1. Google motorları resmin içeriğini daha iyi anlayabilecek
2. Görme engelliler için oluşturulmuş seslendirme uygulamaları, resme eklediğimiz açıklamayı seslendirebilecek
3. Bant genişliği düşük olan ve bu nedenle de resmi düzgün görüntüleyemeyen kullanıcılar, resme eklediğimiz açıklama sayesinde resmi kısmen de olsa anlayabilecek/yorumlayabileceklerdir.

```Markdown
![Sarman cinsi bir kedi fotoğrafı](https://www.alleycat.org/wp-content/uploads/2019/03/FELV-cat.jpg)
```

<script src="https://gist.github.com/yusufatmaca/1038818240e2561112402f75c250230b.js"></script>

---

Peki aynı bağlantıyı veya resmi, belgede birden çok defa kullanacaksak, her defasında böyle tanıtmamız mı gerek? Yani bir defa tanıtıp, istediğimiz yerde çağırabilmemizin bir yolu yok mu?

Cevap: Var. Anlatayım.

Öncelikle bağlantılarımızı kendimizin isimlendireceği referansa kaydediyoruz. Ben “kedi” ve “websayfam” adını verdiğim referanslara kaydettim. Sonrasında bağlantı ve resimleri öğrendiğimiz şekilde tanımlıyoruz fakat tek bir farkla: Daha önce normal parantezler arasına bağlantıyı koyarken, şuan sadece referansı çağırmamız yeterli. Referans oluşturma ve çağırma işlemi köşeli parantezlerle yapıldığı için de bu kurala riayet ediyoruz.


```Markdown
[kedi]: https://www.alleycat.org/wp-content/uploads/2019/03/FELV-cat.jpg
[websayfam]: https://www.yusufatmaca.github.io

[Benim kişisel web sayfam][websayfam]  

![Sarman cinsi bir kedi fotoğrafı][kedi]
```

<script src="https://gist.github.com/yusufatmaca/4f88d25474a70ba29b6daee043937b90.js"></script>

---

Giriş seviyesi için burada bitireyim. Bir sonraki yazımda görüşmek üzere, hoşçakalın!