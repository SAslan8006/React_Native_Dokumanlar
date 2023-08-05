# React Native - Alert Component

Alert React Native'de kullanılan bir uyarı komponentidir. Belirlenen başlık ve mesajla bir uyarı penceresi oluşturulur. Açılan uyarı penceresinde herhangi bir seçeneğe tıklandığında onPress callback fonksiyonu tetiklenir ve uyarı penceresi kapanır.

Öncelikle projeye Alert komponentini import etmek gerekiyor.

```
    import { Alert } from "react-native";
```

Alert komponentinin kullanımı:

- Mesaj başlığı,
- Mesaj içeriği,
- Alert butonu
  şeklindedir.

Aşağıda Alert komponentinin örnek kullanımı bulunmaktadır.

```
import {React} from "react";
import { View, StyleSheet, Button, Alert } from "react-native";

const App = () => {

  const createAlert = () => {
    Alert.alert(
      "Title",
      "Alert Message",
      [
        {
          text: "Cancel",
          onPress: () => Alert.alert("Cancel Pressed")
        },
        {
          text: "OK",
          onPress: () => Alert.alert("OK Pressed")
        }
      ]
    )
  }

  return (
    <View style={styles.container}>
      <Button title={"Alert Button"} onPress={createAlert} />
    </View>
  )
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "space-around",
    alignItems: "center"
  }
});

export default App;
```

![alert-1](./images/alert-1.png)
![alert-2](./images/alert-2.png)
![alert-3](./images/alert-3.png)
![alert-4](./images/alert-4.png)

Görüldüğü üzere butona tıklandığında bir uyarı penceresi açıldı. Açılan pencerede "Cancel" ya da "OK" seçeneklerinden herhangi birine tıklandığında ona ait olan onPress fonksiyonu tetiklendi.
