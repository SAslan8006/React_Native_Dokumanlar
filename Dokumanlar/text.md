## Text Kullanımı

Metni görüntülemek için kullanılan React bileşenidir.  
Text yerleştirme, stil verme ve dokunmatik işlemeyi desteklemektedir.  
Aşağıdaki örnekte, iç içe geçmiş başlık ve gövde metni, öğesinden miras alınır fontFamily, styles.baseTextancak başlık kendi ek stillerini sağlar. Başlık ve gövde, gerçek yeni satırlar nedeniyle birbirinin üzerine yığılır:

```JS
import React, {useState} from 'react';
import {Text, StyleSheet} from 'react-native';

const TextInANest = () => {
  const [titleText, setTitleText] = useState("Bird's Nest");
  const bodyText = 'This is not really a bird nest.';

  const onPressTitle = () => {
    setTitleText("Bird's Nest [pressed]");
  };

  return (
    <Text style={styles.baseText}>
      <Text style={styles.titleText} onPress={onPressTitle}>
        {titleText}
        {'\n'}
        {'\n'}
      </Text>
      <Text numberOfLines={5}>{bodyText}</Text>
    </Text>
  );
};

const styles = StyleSheet.create({
  baseText: {
    fontFamily: 'Cochin',
  },
  titleText: {
    fontSize: 20,
    fontWeight: 'bold',
  },
});

export default TextInANest;
```

Nested text
NSAttributedStringHem Android hem de iOS, kalın veya renkli metin ( iOS'ta, SpannableStringAndroid'de) gibi belirli biçimlendirmeyle bir dizenin aralıklarına açıklama ekleyerek biçimlendirilmiş metni görüntülemenize olanak tanır . Uygulamada, bu çok sıkıcı. React Native için, aynı etkiyi elde etmek için metni iç içe yerleştirebileceğiniz web paradigmasını kullanmaya karar verdik.
