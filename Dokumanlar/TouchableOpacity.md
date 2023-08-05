### TouchableOpacity Nedir?

_TouchableOpacity_' react-native'de buton oluşturmak için kullanılan bir bileşen(component)dir. '_Button_' bileşeni(component) gibi kullanıcı arayüzünde buton oluşturur. '_Button_' bileşeninden farkı ise şu şekildedir. '_Button_' bileşeni(component) ile oluşturduğunuz buton ios yada android için varsayılan olarak stillendirilmiş olarak gelir. Örneğin şu kodu çalıştırırsanız,

```javascript
import React from "react";
import { View, Text, StyleSheet, Button } from "react-native";
const basicComponent = () => {
  return (
    <View>
      <Button>Press me!</Button>
    </View>
  );
};
const styles = StyleSheet.create({});
export default basicComponent;
```

bu şekilde bir çıktı alırız.

![alt text](./images/button.jpeg "button output for ios and android")

Yukarıdaki örnekte görüldüğü üzere '_button_' bileşeni(component) farklı platformlar için varsayılan olarak farklı stiller ile çıktı veriyor. Fakat '_TouchableOpacity_' bileşeni varsayılan olarak stilsiz olarak çıktı vermektedir. Bu nedenle StyleSheet bileşeni gibi bir stil bileşenine ihtiyaç duyarız.

Aşağıdaki örnekte görüleceği üzere '_TouchableOpacity_' bileşeni ile oluşturulan butona kullanıcı her bastığında ekrandaki bir sayaç butona basma sayısını ekrana basmaktadır.

```javascript
import React, { useState } from "react";
import { StyleSheet, Text, TouchableOpacity, View } from "react-native";

const App = () => {
  const [count, setCount] = useState(0);
  const onPress = () => setCount((prevCount) => prevCount + 1);

  return (
    <View style={styles.container}>
      <View style={styles.countContainer}>
        <Text>Count: {count}</Text>
      </View>
      <TouchableOpacity style={styles.button} onPress={onPress}>
        <Text>Press Here</Text>
      </TouchableOpacity>
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    paddingHorizontal: 10,
  },
  button: {
    alignItems: "center",
    backgroundColor: "#DDDDDD",
    padding: 10,
  },
  countContainer: {
    alignItems: "center",
    padding: 10,
  },
});

export default App;
```

---

![](./images/toucahbleOpacity_1.png)

---

![](./images/toucahbleOpacity_2.png)

---

![](./images/toucahbleOpacity_3.png)

---

Yukarıdaki örnekten anlaşılacağı üzere '_TouchableOpacity_' bileşenini kullanabilmemiz için ilk olarak import etmemiz gerekmetir.

```javascript
import { TouchableOpacity } from "react-native";
```

Syntax:

```javascript
  ...
    <TouchableOpacity />
  ...
```

### TouchableOpacity Props'ları

#### 1-TouchableWithoutFeedback

Geçerli bir nedeniniz olmadan kullanmayın. Bu özellik ile TouchableOpacity ile oluşturduğumuz buton dokunma sonrası geribildirimi kapatır. Fakat arkaplanda butona basılmış olur.

TouchableWithoutFeedback sadece bir alt öğe (child) destekler. Birden fazla alt öğeye sahip olmak için 'View' bileşenine ekleyebilirsiniz. TouchableWithoutFeedback, alt öğesini klonlayarak ve ona yanıtlayıcı sahne öğeleri uygulayarak çalışır. Bu nedenle, herhangi bir aracı bileşenin bu aksesuarlardan temeldeki React Native bileşenine geçmesi gerekir.

Örnek kullanım:

```javascript
function MyComponent(props) {
  return (
    <View {...props} style={{ flex: 1, backgroundColor: "#fff" }}>
      <Text>My Component</Text>
    </View>
  );
}

<TouchableWithoutFeedback onPress={() => alert("Pressed!")}>
  <MyComponent />
</TouchableWithoutFeedback>;
```

#### 2- Style

View bileşeninin(component) aldığı bir style özelliğini(props) alır.

Örnek kullanım:

```javascript
  <TouchableOpacity style={styles.button}>
```

#### 3-activeOpacity

Dokunma etkinken sarılmış görünümün opaklığının ne olması gerektiğini belirler. Varsayılan değer 0.2'dir. Tip olarak sayı alır.

Örnek kullanım:

```javascript
  <TouchableOpacity activeOpacity={0.8}>
```

#### 4-tvParallaxProperties (ios)

(Yalnızca Apple TV) Apple TV paralaks efektlerini denetleme özelliklerine sahip nesne. Obje tipinde değerler alır. Bu değerler şunlardır.

- **enabled:** Varsayılan olarak 'true' gelir. Parallax efekti aktif eder.

- **shiftDistanceX:** Varsayılan değeri 2.0.

- **shiftDistanceY:** Varsayılan değeri 2.0.

- **tiltAngle:** Varsayılan değeri 0.05.

- **magnification:** Varsayılan değeri 1.0.

- **pressMagnification:** Varsayılan değeri 1.0.

- **pressDuration:** Varsayılan değeri 0.3.

- **pressDelay:** Varsayılan değeri 0.0.

#### 5-hasTVPreferredFocus (ios)

(Yalnızca Apple TV) TV tercih edilen odak. Boolean tipinde değer alır.

#### 6-nextFocusDown (Android)

TV'nin sonraki odağını aşağı alır. Sayı tipinde değer alır.

#### 7-nextFocusForward (Android)

TV sonraki odağını ileri alır. Sayı tipinde değer alır.

#### 8-nextFocusLeft (Android)

TV sonraki odağını sola alır. Sayı tipinde değer alır.

#### 9-nextFocusRight (Android)

TV sonraki odağını sağa alır. Sayı tipinde değer alır.

#### 10-nextFocusUp (Android)

TV sonraki odağını yukarı alır. Sayı tipinde değer alır.
