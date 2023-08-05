# FlatList

React Native ile listeleme yada ekranda alt alta sıralama işlemleri yapmak istiyorsanız en iyi tercih FlatList companenti olacaktır. Bunun alternatifleri var (ListView) ancak en çok kullanılanı ve geliştiriciler tarafından da performans olarak da en çok tercih edileni FlatList’dir.

Peki nedir bu FlatList ?
FlatList component’i, benzer şekilde yapılandırılmış verileri kaydırılabilir bir listede görüntüler. Yalnızca ekranda görünen öğeleri işler ve listedeki öğe sayısı çok fazla olduğunda uygulama performansının daha da kötüleşmesini önlemek için yalnızca değişen öğeleri günceller.

İşte FlatList’in desteklediği kullanışlı özellikler:

Tamamen cross-platform
İsteğe bağlı yatay mod
Header desteği
Footer desteği
Separator desteği
Scroll yükleme
ScrollToIndex desteği
Çoklu sütun desteği
FlatList Kullanımı
Proplar :

renderItem (type: function) (zorunlu) : data’dan bir öğe alır ve listeye işler.
data (type: array) (zorunlu) : Listeyi oluşturmak için kaynak olarak kullanılan bir veri dizisi.
Basit bir örnek için aşağıdaki linke tıklayınız :

flatlist-simple - Snack
Example usage
snack.expo.dev

Örnekteki propları açıklayalım:

keyExtractor (type: function) : Her component alanı için özel key ataması
Üzerine tıklanan item’ın rengini değiştiren bir örnek daha:

flatlist-selectable - Snack
Example usage
snack.expo.dev

extraData (type: any) : Data içerisinde belirlediğimiz diziye çalışma esnasında yeni bir değer eklenirse FlatList’de gösterilmesi yani yeniden render edilmesi için bir değişken var. render’la demek için kullanılır. Buraya state verilir .
Kaynaklar:
https://reactnative.dev/docs/flatlist
https://www.kindacode.com/article/react-native-flatlist-tutorial-and-examples/
https://www.brkdgn.com/react-native-flatlist/
