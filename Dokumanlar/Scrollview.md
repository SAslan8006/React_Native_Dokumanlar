# React-Native-Scrollview

Scrollview kaydırabilir içerikler üretmemizi sağlayan react-native bileşenidir.İçerikleri isteğimize göre yatay ve dikey olarak kaydırabiliriz.Varsayılan değer dikeydir.Kaydırmayı yatay olarak ayarlamak için default olarak verilen (horizontal={false}) değerini (horizontal={true}) olarak değiştirmemiz gerekir.
Scrollview tüm yapıyı tek seferde render ettiği için ,çok fazla component içeren uzun yapılı projeler için dezavantaj olabilir.Düşünün belki cihaz ekranında sadece birkaç bileşen görebiliyoruz.Ancak Scrollview ekranda görmediğimiz kısımları da render ediyor.Bu büyük çaplı projeler için ciddi performans düşüklüğüne sebep olabilir.Büyük çaplı projelerde scrollview yerine FlatList bileşeni önerilir.FlatList öğeleri görünmek üzereyken tembel bir şekilde işler ve bellekten ve işlem süresinden tasarruf etmek için ekranın dışına kayan öğeleri kaldırır.Bu şekilde sadece ekranda görüntülediğimiz bileşenler render edilir.Ancak küçük çaplı projeler için Scrollview kullanmak ideal.

### Scrollview için kullanılan proplar

 <br>
<img src="https://github.com/demircisena/React-Native-Scrollview/blob/main/scrollview%20props.png" width="800px" heigth="400">

```javascript
import React from "react";
import {
  StyleSheet,
  Text,
  SafeAreaView,
  ScrollView,
  StatusBar,
  Button,
} from "react-native";

const App = () => {
  const onPressButton = () => {
    alert("You clicked the button!");
  };
  return (
    <SafeAreaView style={styles.container}>
      <ScrollView style={styles.scrollView}>
        <ScrollView>
          <Text style={{ fontSize: 20 }}>Scroll me plz</Text>
          <Button title={"Button 1"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>React Native ScrollView</Text>
          <Button title={"Button 2"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>React Native ScrollView </Text>
          <Button title={"Button 3"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>If you like</Text>
          <Button title={"Button 4"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>Scrolling down</Text>
          <Button title={"Button 5"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>Scrolling down</Text>
          <Button title={"Button 6"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>SENA DEMİRCİ</Text>
          <Button title={"Button 7"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>SENA DEMİRCİ</Text>
          <Button title={"Button 8"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>SENA DEMİRCİ</Text>
          <Button title={"Button 9"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>SENA DEMİRCİ</Text>
          <Button title={"Button 10"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>React Native</Text>
          <Button title={"Button 11"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>Scroll me plz</Text>
          <Button title={"Button 12"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>Scroll me plz</Text>
          <Button title={"Button 13"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>If you like</Text>
          <Button title={"Button 14"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>If you like</Text>
          <Button title={"Button 15"} onPress={onPressButton} />
          <Text style={{ fontSize: 20 }}>Scrolling down</Text>
          <Button title={"Button 16"} onPress={onPressButton} />
        </ScrollView>
      </ScrollView>
    </SafeAreaView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: StatusBar.currentHeight,
  },
  scrollView: {
    backgroundColor: "pink",
    marginHorizontal: 20,
  },
  text: {
    fontSize: 42,
  },
});

export default App;
```

### Çıktısı:

<table class="image-table">
<tbody>
<tr>
<td>
<img src="https://github.com/demircisena/React-Native-Scrollview/blob/main/Screenshot_20221104-095813_AwesomeProject.jpg" width="200" heigth="100" >
</td>
<td>
<img src="https://github.com/demircisena/React-Native-Scrollview/blob/main/Screenshot_20221104-095821_AwesomeProject.jpg" width="200" heigth="100">
</td>
<td>
<img src="https://github.com/demircisena/React-Native-Scrollview/blob/main/Screenshot_20221104-101516_AwesomeProject.jpg" width="200" heigth="100">
</td>
</tr>
</tbody>
</table>  

### Not : Bu Döküman SENA DEMİRCİnin githubından alınmıştır. 
