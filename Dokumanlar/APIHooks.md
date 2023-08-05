React Native API’s Hooks

React Native Api’s yapısının içerisinde hooks kısmı ikiye ayrılmaktadır. Bunları;

• useColorScheme

import { useColorScheme } from 'react-native';
• useWindowDimensions

import { useWindowDimensions } from 'react-native';
şeklinde ifade edebilir, projelerimize bu kodlar ile import edebiliriz.

useColorScheme:
İlk olarak useColorScheme ’den başlayacak olursak,

“useColorScheme” telefonda mevcut kullanıcının tercih ettiği renk şemasını bizlere ifade eder. Kullanıcı telefonunda gündüz temasını kullanıyorsa “light” şeklinde, gece temasını kullanıyorsa “dark” şeklinde bir sonuç alacaktır. Sonuç “null” döndüğünde ise kullanıcının renk teması belirtmediğini anlamış oluruz. Şimdi aşağıdaki kod bloklarından adım adım işlevlerini inceleyelim;

import React from 'react';
import { Text, StyleSheet, useColorScheme, View } from 'react-native';  
// İlk olarak yukarıda react native kütüphanesinden useColorScheme import ettik
const App = () => {
// Daha sonra import ettiğimiz useColorScheme() fonksiyon şeklinde colorScheme değişkenine tanımladık.
const colorScheme = useColorScheme();
return (
<View style={styles.container}>
<Text>useColorScheme()</Text><br/>
<Text><b>{colorScheme}</b></Text>
// Üstteki text kısmında ise süslü parantez içerisinde tanımladığımız colorScheme değişkenini ekrana yazdırdık.
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

EKRAN ÇIKTISI
Ve kodlarımızın gündüz teması kullanılan bir cihazda çıktısını aldığımızda yukarıdaki gibi light sonucunu gözlemleriz.

useWindowDimensions:
useWindowDimensions hooku ise bize 4 adet özellik sunar. Bunları;

• Height (yükseklik)

• Width (genişlik)

• Scale (büyüklük)

• FontScale (yazı büyüklüğü)

olarak listeleyebiliriz.

Bu değerleri bize güncel olarak useWindowDimensions hooku sunmaktadır. Kod üzerinde örneklendirecek olursak;

import React from "react";
import { View, StyleSheet, Text, useWindowDimensions } from "react-native";
// İlk olarak react-native kütüphanesinden useWindowDimensions hookunu import ettik.
const App = () => {
const window = useWindowDimensions();
// UseWindowDimensions fonksiyonunu window değişkenine atadık.
return (
<View style={styles.container}>
<Text>Window Dimensions</Text>
<Text>{`Height: ${window.height}`}</Text>
<Text>{`Width: ${window.width}`}</Text>
<Text>{`Scale: ${window.scale}`}</Text>
<Text>{`FontScale: ${window.fontScale}`}</Text>
// Sırasıyla güncel height, width, scale, fontScale değerlerini ekrana yazdırdık.
</View>
);
}
const styles = StyleSheet.create({
container: {
flex: 1,
justifyContent: "center",
alignItems: "center"
}
});
export default App;

EKRAN ÇIKTISI
Yukarıdaki gibi cihazınızın piksel cinsinden ekran uzunluğunu, oranını ve yazı tipi büyüklük ölçeğini gözlemleyebiliriz.

Cihazı yatay çevirdiğinizde “height” ve “width” ölçüleri güncel olarak değişecektir. Height dikeydeki uzunluğu, width ise yataydaki genişliği ifade eder.

“fontScale” değeri telefonunuzdaki yazı boyutlarını ifade eder ve işletim sistemine göre farklılık gösterebilir.

“Scale” değeri ise cihazın piksel oranını ifade eder. 2 değeri Retina ve yüksek DPI ekranlarda oluşur.
