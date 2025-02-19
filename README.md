npx react-native init KadesApp
cd KadesApp
npm install react-native-call
import React from 'react';
import { View, Text, Button, Alert, StyleSheet } from 'react-native';
import call from 'react-native-call';

const App = () => {
  // İstenilen numara
  const emergencyNumber = '+90XXXXXXXXX'; // Bu numarayı değiştirin (örneğin 112)

  // Acil durum butonuna basıldığında çağrı yapmak
  const handleEmergencyCall = () => {
    try {
      // React Native Call ile arama yapma
      call.callPhone(emergencyNumber, true).then(() => {
        Alert.alert('Acil Durum', 'Acil numaraya çağrı başlatıldı!');
      }).catch((error) => {
        console.log('Arama hatası:', error);
        Alert.alert('Hata', 'Arama başlatılamadı. Lütfen tekrar deneyin.');
      });
    } catch (error) {
      console.error(error);
      Alert.alert('Hata', 'Bir hata oluştu. Lütfen tekrar deneyin.');
    }
  };

  return (
    <View style={styles.container}>
      <Text style={styles.header}>Acil Durum Uygulaması</Text>
      <Button title="Acil Durum Araması Yap" onPress={handleEmergencyCall} />
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#f0f0f0',
  },
  header: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 20,
  },
});

export default App;
<uses-permission android:name="android.permission.CALL_PHONE" />
