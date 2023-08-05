# useColorScheme — React Native

Bu yazı içerisinde useColorScheme’in ne olduğundan ve React Native içerisinde ne ifade ettiğinden bahsedeceğiz.

useColorScheme Apperance modülü içerisindeki renk şemasını React Hook’u olarak yakalamamızı sağlar. Kısacası işletim sisteminin teması değiştiğinde bunu direkt olarak uygulamamızın içerisinde bilgi olarak yakalayıp ona göre tema değişikliğine uygun hale getirir. Geriye döndürülen değer kullanıcının tercih temayı belirtir. Değer daha sonra güncellenebilir. Direkt kullanıcının eylemi doğrultusunda değiştirilebilir ya da zamanlı olarak değiştirilebilir.

Örnek: Ayarlar -> Görünüm kısmından tema değişikliği yapabilirsiniz ya da gece ve gündüz zamanı ile değişen karanlık ve aydınlık tema özelliğini telefonlarınızdan aktif hale getirebilirsiniz.

Desteklenen tema şemaları:

Kullanıcı “light” (aydınlık) tema seçebilir.
Kullanıcı “dark” (karanlık) tema seçebilir.
Kullanıcı tercih edilen tema şablonlarından herhangi bir temayı belirlemeyebilir. Bu değer “null” cinsindedir.
Bunu kullanabilmek için öncelikle kullanacağımız dosya içerisine ekleme işlemi yapmamız gerekiyor. Ekleme işlemini dosyanızın en üst kısmına alttaki kodu kopyalarak yapabilirsiniz.

import { useColorScheme } from 'react-native';
Ekledikten sonra alttaki kod kısmında birlikte inceleme yapabiliriz.

Teker teker bu dosya içerisindeki kodu inceleyelim.

import React from 'react';
React kütüphanesini dosya içerisine ekledik.
import { Text, StyleSheet, useColorScheme, View } from 'react-native'; 2. React native kütüphanesi içerisinde olan Text, StyleSheet, useColorScheme ve View kısmını aşağıda kullanabilmek için aldık.

const App = () => {
const colorScheme = useColorScheme();
return (
<View style={styles.container}>
<Text>useColorScheme(): {colorScheme}</Text>
</View>
);
}; 3. Sabit bir şekilde App değişkeni oluşturduk. Şimdi App içerisini teker teker inceleyelim.

const colorScheme = useColorScheme();
App içerisine kullanıcından gelecek olan değeri ismi colorScheme sabit değişkeni olarak atama yaptık.

return (
<View style={styles.container}>
<Text>useColorScheme(): {colorScheme}</Text>
</View>
);
Return içerisine girecek olursak eğer yazacağımız yazının görünmesi için öncelikle View oluşturduk ve style içerisine StyleSheet içerisinde tanımladığımız container’ı ekledik.

<View style={styles.container}>
    Boş kısım
</View>
View içerisine girdikten sonra (Yukarıdaki boş kısım yazan yer.) Text ekledik ve içeriye “useColorScheme() : ” yazdıktan sonra return dışarısında tanımladığımız ColorScheme değişkenini ekledik. (JavaScript ile tanımladığımız değerleri süslü parantez içerisinde oluşturmaya özen gösteriniz yoksa hata alırsınız.)

<Text>useColorScheme(): {colorScheme}</Text>
App kısmını geçtiğimize göre App altında stil tanımlamalarımızı yapabiliriz.

const styles = StyleSheet.create({
container: {
flex: 1,
alignItems: "center",
justifyContent: "center"
},
});
En alt kısımda da oluşturduğumuz App adlı component’i dışarı aktarıyoruz.

export default App;
Aşağıdaki gibi tema karanlık ise dark, aydınlık ise light yazarak gözükmektedir.

Tema bilgisi ekranda gözükmektedir
import React from 'react';
import { Text, StyleSheet, useColorScheme, View } from 'react-native';
const App = () => {
const colorScheme = useColorScheme();
return (
<View style={styles.container}>
<Text>useColorScheme(): {colorScheme}</Text>
</View>
);
};
const styles = StyleSheet.create({
container: {
flex: 1,
alignItems: "center",
justifyContent: "center"
},
});
export default App;
Kaynaklar : React Native useColorScheme https://reactnative.dev/docs/usecolorscheme
