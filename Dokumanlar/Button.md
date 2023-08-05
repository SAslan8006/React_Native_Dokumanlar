# React Native Button Component

Kimya alanında maddenin en küçük yapı taşını atom olarak tanımlıyorsak (Atomu oluşturan parçacıkları göz ardı edersek) React Native için de bunu component olarak tanımlayabiliriz.

Button Component’i ne işe yarar?
Her component’in olduğu gibi button component’inin de bir işlevi vardır. Tıklanabilir bir component olan button, tıklandığı zaman içerisine atanmış sorumluluğu yerine getirmiş olur.

Button Component’ini React Native’de nasıl kullanabiliriz?
Aşağıdaki kod satırını kullanarak button component’i, react-native kütüphanesinden import edilmiş olur.

import {Button} from "react-native";
Button component’ini aşağıdaki kod satırındaki gibi kullanabiliriz.

<Button title="Birinci Button" onPress={pressFunction}/>
Yukarıda gözüktüğü gibi button component’i zorunlu olarak iki tane prop almalıdır. İlk prop; title, ikinci prop; onPress. Title prop’u button’un içinde yazılı kelimedir, title prop’u için genelde button’un yapacağı fonksiyonla ilgili kelimeler kullanılır, onPress prop’u ise button’un çalıştıracağı fonksiyonu parametre olarak alır. Button’a tıklandığında onPress içerisindeki fonksiyon çalışarak işlevini yerine getirmiş olur.

import { useState } from 'react';
// useState import edilir.
import { Button, Platform, StatusBar, Text, View } from 'react-native';
// Button, Platform, StatusBar, Text ve View componentleri import edilir.
const App = () => {
if (Platform.OS === "android") {
//Platform android ise
const notch = StatusBar.currentHeight > 24;
//StatusBar componentinin yüksekliği 24'ten büyük olur.
}
const [txt, setTxt] = useState("");
// useState kullanılarak ekranda güncelleme yapılacak değişken atanır.
const printHelloWorld = () => {
//Ekrana HelloWorld yazdıran fonksiyon

    setTxt("Hello World");
    //txt değişkenini güncelleyen useState içerisindeki fonksiyon.

}
return(
<View> //View component'i
<StatusBar/> //StatusBar component'i
<Button title="Hello World" onPress={printHelloWorld}/>
//İçerisinde Hello World yazan ve tıklandığında printHelloWorld fonksiyonunu çağıracak olan button.
<Text>{txt}</Text> //txt değişkenini içeren Text component'i

    </View>
    );

};
export default App; //App'in export edilmesi.
Yukarıda, button’a tıklandığında button’un altına “Hello World” yazdıran bir örnek kod.

Button’a basılmadan önce -> -> -> -> -> -> -> -> -> -> Button’a basıldıktan sonra
Button Component’inin kullandığı prop’lar
color: String bir değer alır, Android tarafında button’un arkaplan rengini değiştirir, IOS tarafında ise button’un adının rengini değiştirir.
disabled: Boolean bir değer alır, “true” değerini aldığında tıklanılmayan, gri bir button’a dönüşür. Default değeri olarak “false” alır.
touchSoundDisabled: Boolean bir değer alır, “true” değerini aldığında, button’a tıklanıldığında çıkan sistem sesi duyulmuyor. “false” değerini aldığında, button’a tıklanıldığında çıkan sistem sesinde herhangi bir sınırlama olmuyor. Default değeri olarak “false” alır.
Button işlevinde kullanılan Component’ler
TouchableOpacity: Button component’inde olduğu gibi tıklandığı zaman onPress prop’u içerisindeki fonksiyonu yerine getirir. Tıklandığı an arka plandaki rengin opacity miktarı azalır, bu da tıklama hissiyatı olarak daha iyi bir deneyim sunar.
TouchableWithoutFeedback: Button component’inde olduğu gibi tıklandığı zaman onPress prop’u içerisideki fonksiyonu yerine getirir. Tıklandığı an arka plandaki rengin opacity miktarı değişmez. TouchableOpacity arasındaki temel fark budur.

Not: https://medium.com/@mgunerengineer/react-native-button-component-a23254bd90c3
