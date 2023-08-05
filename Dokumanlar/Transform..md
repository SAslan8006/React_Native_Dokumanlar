React Native Transform Kullanımı

React kullanmaya başlamadan önce bir web geliştirme geçmişine sahipseniz CSS transform özelliğinin son derece yararlı ve kullanışlı olduğunu bilirsiniz. Bu transform özelliğinin bize sağladığı dönüşümleri kullanarak animasyonlar ve görsel olarak çekici UI öğeleri oluşturabiliriz. Aslında birçok modern web tasarımı bu dönüşümlerden ilham alarak gerçekleştirilir.

React Native, bize bu transform özelliğini varsayılan olarak sunar. Bu özelliği tıpkı web geliştirme yaparken kullandığımız gibi benzer senaryolarda ve çeşitli uygulamalarda kullanabiliriz. Bu yazımda bu dönüştürme özelliklerini açıklamaya çalışacağım.

Transform Özelliği Tanımı ve Kullanımı
Transform özelliği, ekrandaki bir nesneyi döndürmek, ölçeklemek ve çevirmek için kullanılabilecek bir özellikler listesi için genel bir terimdir. Başka bir deyişle, bir nesnenin yönünü ve konumunu değiştirmek için kullanabileceğiniz bazı stil özelliklerinin birleşimidir. Ancak, dönüştürmeleri uyguladığınızda, dönüştürülmüş bileşenin etrafındaki düzenler aynı kalır, dolayısıyla yakındaki bileşenlerle çakışabilir. Bu tür çakışmaları önlemek için dönüştürülen bileşene, yakındaki bileşenlere veya kapsayıcıya dolgu uygulayabiliriz.

Bir örnek üzerinden ilerlemek için aşağıdaki linke tıklayarak kullanımına göz atabilirsiniz:

Transforms - Snack
Example usage
snack.expo.dev

Transform özelliği, bir dizi nesne bekleyen bir anahtardır. Her nesne, verilen öğeye uygulamak istediğimiz bir dönüştürme özelliğini ve dönüşümde kullanılacak değeri belirtir. Nesneler birleştirilmemelidir ve her nesne tek bir anahtar ve değer çifti içermelidir. En çok kullanılan üç dönüştürme özelliği; translate, scale ve rotate özellikleridir.

Translate Özelliği:
Bir öğeyi bir yerden başka bir yere taşımak için kullanılır. Öğeyi yatay ya da dikey eksende hareket ettirebiliriz. Aşağıda gösterildiği gibi transform dizinize translateX özelliğini belirterek öğenizi x ekseni boyunca, translateY özelliğini belirterek y ekseni boyunca hareket ettirebilirsiniz. Aşağıdaki kod nesnemizi mevcut konumunda (orijin) 50 birim x ekseninde ve 50 birim y ekseninde kaydırmalıdır.

transform([{ translateX:50 },{ translateY:50 }]);

Rotate Özelliği:
Döndürme özelliği, nesnenizi farklı döndürme eksenleri boyunca yönlendirmenize olanak tanır. Onu x ekseni, y ekseni veya z ekseni boyunca döndürebilirsiniz. Bu özellik, belirtilen açının birimiyle birlikte dönüş açısı için bir dize değeri bekler. Radyan için rad veya derece için deg olabilir. Gelin nesnemizi hem x ekseninde hem de y ekseninde döndürelim. Bunu yaparken de hem derece hem radyan cinsinden değerler vererek örnekleyelim:

transform([{ rotateX: '60deg' }]);

transform([{ rotateY: '1.047197rad' }]);

Scale Özelliği:
Scale özelliği, nesnenin orijinal boyutuna göre ne kadar büyük olması gerektiğini belirtir. Başlangıçta, tüm öğelere 1 ölçeği verilir. Nesneyi, aşağıda gösterildiği gibi 2'lik bir ölçek vererek kendi boyutunun iki katı olacak şekilde ölçeklendirebilirsiniz:

transform([{ scale: 2 }]);

Alternatif olarak nesnemizi x ekseni ya da y ekseni boyunca da ölçeklendirebiliriz. Bu sayede nesnemizi x ekseni boyunca ölçeklendirerek genişletebilirken y ekseninde ise boyunu uzatabiliriz.

Transform özelliğinin nasıl çalıştığından bahsettiğimize göre kullanım alanlarından da bahsederek yazımızı sonlandıralım. Başta da belirttiğimiz gibi animasyonlarda oldukça sık kullanılmaktadırlar. Bunun dışında yaygın olarak kullanıldıkları bir diğer alan da e-ticaret uygulamaları veya eğitim uygulamalarıdır. Bir çok e-ticaret uygulaması, bir ürünü farklı açılardan görmenize ve ürün görselini yakınlaştırmanıza, uzaklaştırmanıza ve döndürmenize olanak tanır. Transform özelliği sayesinde bu işlemleri kolayca gerçekleştirebiliriz.

Buraya kadar geldiyseniz tebrikler. Bu ilk medium yazımdı. Umarım faydası olmuştur :)

Kaynaklar:
https://reactnative.dev/docs/transforms
https://www.waldo.com/blog/react-native-transforms

Not: https://medium.com/@fatihgultekin/react-native-transform-kullan%C4%B1m%C4%B1-d241dd4952fb sayfasından alınmıştır.
