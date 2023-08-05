# React Native’de Stillendirme Nasıl Yapılır: StyleSheet

Frontend frameworkleri ile çalışmayı sevmemde büyük rol oynayan stillendirme işlemini React Native’de nasıl gerçekleştireceğimizden bahsetmek istiyorum.

React Native, stillendirme işlemi için StyleSheet yapısını kullanmamızı bekler. Style Sheet, Türkçesiyle stil şablonları, sözlük anlamıyla bir web sayfası içerisindeki kodların ekrana nasıl yansıtılmasını gerektiğini web tarayıcısına söyleyen en önemli öge. Hadi şimdi bu yapıyı uygulamalı olarak tanıyalım. 🎨

Öncelikle buradaki adımları takip ederek yeni bir proje oluşturalım ve başlangıç olarak App.js dosyasını aşağıdaki gibi yazalım.

Projemizi ayağa kaldırınca ekrandaki görüntü aşağıdaki gibi olacaktır.

Şimdi StyleSheet yapısını kullanarak stil verme işlemine başlayalım. Bu işlemi App.js dosyasının içerisinde yapmak mümkün, fakat çalışma ve kod okuma kolaylığı açısından ayrı bir stil dosyası içerisinde çalışmak daha konforlu olacaktır. Ayrıca StyleSheet ile çalışırken aynı zamanda metotları ve özellikleri tanıyalım.

Metotlar
create()
App.js ile aynı dizinde App.style.js adını verdiğimiz dosyayı StyleSheet’in create metodunu kullanarak aşağıdaki şekilde oluşturalım.

Oluşturduğumuz bu stil dosyasını App.js içerisinde import edelim ve gerekli gördüğümüz etiketlerde style prop’unu aşağıdaki gibi kullanarak uygun isimler verelim. Burada style prop’unu HTML’deki class yapısı gibi düşünebiliriz.

App.js dosyasını bu şekilde güncelledikten sonra App.style.js dosyasında çalışmaya başlayabiliriz. Bu dosyada birçok yönüyle CSS’e benzeyen StyleSheet’i kullanmış olacağız. Temel olarak StyleSheet özellikleri camelCase tekniğiyle, özellik değeri ise tırnak içinde yazılır ve bu özellikler burada noktalı virgülle değil, virgülle ayrılmak zorundadır.

Örneğin arka plan rengini belirlerken kullandığımız özellik

CSS’te background-color: black; iken

StyleSheet içerisinde backgroundColor: “black”, olmaktadır.

App.js dosyasında container olarak isimlendirdiğim prop’un içerisinde flex yapısını ve arka plan rengini tanımlayalım. Sonrasında header ve subheader stilleri içerisinde başlığımızın görünümünü dilediğimiz şekilde ayarlayalım. Ben yazı rengi olarak React logo rengini (#61DBFB) kullandım. 🤩

App.js dosyasında subheader’a ait olan Text etiketini header’a ait olan Text etiketinin içine yazmıştık. App.style.js dosyasında başlığımıza bazı özellikler verdik ve subtitle stili içerisinde farklı olmasını istediğimiz özellikleri kolayca değiştirmiş olduk. Ben yazı boyutunu ve rengini değiştirerek bu özelliği ön plana çıkarmak istedim.

Kısaca create metodunu tanımış olduk. Şimdi diğer metodlara göz gezdirelim.

compose()
compose metodunu tanımak için yukarıdaki başlık stillendirmesinden devam etmek istiyorum. Farkları ve değişiklikleri daha kolay anlayabilmek için başlığımızı View etiketi ile saralım. Ardından dosyalarımızı aşağıdaki gibi düzenleyelim.

Burada create metodunda gerçekleştirdiğimiz işlemden farklı bir işlem gerçekleştirmeyip iki farklı başlık stili ortaya koymuş olduk ve ekran görüntümüz şekildeki gibi oldu.

Şimdi compose metodunu anlayabilmek için App.style.js dosyamıza aşağıdaki gibi compose metodu ile farklı stiller oluşturalım. Burada özellikleri oluştururken yazım hataları yaptım, çünkü compose yazım hatası yaptığımız özelliği görmezden gelerek yoluna devam ediyor. 🙈

Şimdi oluşturduğumuz bu stilleri App.js dosyamıza uygulayalım.

compose metodunu kullanarak yaptığımız stillendirme işleminde aşağıdaki ekran görüntüsünü elde etmiş olduk. styles.header stilinde textAlign özelliğinde yazım hatası yaptığımız için, textAlign özelliği okunmadı ve ilk kutuda metin ortalanmadı. Aynı şekilde compose.header stilinde color özelliği okunmadığından ikinci kutudaki yazı rengi varsayılan olarak ekranda görüntülenmiş oldu.

Burada compose metodu kullanmasaydık, uygulamamız mutlaka hata verirdi.

Üçüncü ve dördüncü kutulara baktığımıza ise App.style.js dosyasında compose metodu ile oluşturduğumuz header, header2, subheader ve subheader2 stillerinin ekrana nasıl yansıdığını görüyoruz. Aynı zamanda compose metoduna yazdığımız ikinci nesnenin özelliklerinin baskın olduğunu da görüyoruz.

Karışık gibi görünen, fakat aslında basit bir mantığa sahip olan bu compose metodunu, çeşitli şekillerde deneyerek kavramanızı öneriyorum. Ben yukarıdaki örneği hazırlarken eğlendiğimi itiraf edebilirim. 🥳

flatten()
Bu metot, diğer metotlar ile oluşturulmuş stil nesnelerini tek bir nesne altında toplamak için kullanılmaktadır. Ben yine oluşturduğumuz App.js dosyası üzerinden ilerlemek istiyorum. Bunun için öncelikle App.style.js dosyasını aşağıdaki şekilde düzenleyelim.

Burada flatten ve flattenSub adında iki stil nesnesi oluşturmuş olduk. App.js dosyasına bir kutu daha ekleyelim ve style prop’larına sırayla flatten ve flattenSub nesnelerini aşağıdaki gibi verelim.

flatten metodunu kullanarak oluşturduğumuz beşinci kutumuzu ekranda yukarıdaki gibi görüntülemekteyiz.

Kullanımı ve mantığı çok basit olan bu flatten metodu, işimizi kolaylaştırıyor olsa da style prop’una doğrudan stil nesnesi göndermek optimizasyon açısından çok da sağlıklı olmayacaktır.

Özellikler
absoluteFill veya absoluteFillObject
Bu iki özellik aşağıda vermiş olduğum özellikleri barındırmaktadır.

App.js dosyasının içerisinde, absoluteFill veya absoluteFillObject özelliklerini içeren stilleri, hangi sırayla kullanılırsak kullanalım position özelliği absolute ve diğer özellikleri aşağıdaki gibi 0 olduğundan sıfır noktasında, yani ekranın sol üst köşesinde, görüntülenecektir. Şimdi bu iki özelliği denemek için App.js doyasını aşağıdaki gibi düzenleyelim.

Burada üç ayrı kutu oluşturmuş olduk. Karışıklık olmaması adına da kutuları numaralandırdık. Şimdi App.style.js dosyasını düzenleyelim.

Burada birinci kutumuzu absoluteFill veya absoluteFillObject özelliğini kullanmadan stillendirerek sıfır noktasından 100 birim solda ve 50 birim aşağıda yer almasını sağladık. İkinci kutumuzda absoluteFillObject özelliğini kullandık ve sıfır noktasından 125 birim sola taşıdık. Üçüncü kutumuzda ise sadece absoluteFill özelliğini kullanarak sıfır noktasında bıraktık. Bu sayede ekran görüntüsü aşağıdaki gibi oldu.

Unutmadan belirtmemde fayda var: absoluteFill ve absoluteFillObject özellikleri arasında bir fark yok. 🙅‍♀️

hairlineWidth
Son olarak hairlineWidth özelliğine bakalım. Ekranda ince bir çizgi oluşturmak istiyorsak bunu kullanabiliriz. Bu özellik için App.style.js dosyasında aşağıdaki gibi düzenleme yapalım.

Bu düzenlemeyle ilk kutumuzda border kalınlığını hairlineWidth özelliğiyle ikinci kutumuzdaysa 1 değeriyle belirlemiş olduk. Şimdi ekran görüntüsüne bakalım.

İlk kutuda gördüğümüz gibi ince hatta saç telim kadar ince bir çizgi elde etmiş olduk. 🤭 Fakat yine de bu benim tercih edeceğim bir özellik değil, çizginin kalınlık değerini manuel olarak girmeyi tercih ettiğimi söyleyebilirim. 🙄

Evet, StyleSheet bu şekildeydi. Ben yazarken çok eğlendim umarım siz de okurken eğlenirsiniz. 😛

Ayrıca bu yazıyı yazmam için beni teşvik eden ve bana muhteşem bir bootcamp eğitim programı fırsatı sunan
kodluyoruz
’a teşekkürler.

Not: https://medium.com/@zehratok/react-nativede-stillendirme-nas%C4%B1l-yap%C4%B1l%C4%B1r-stylesheet-95db2f97044d
