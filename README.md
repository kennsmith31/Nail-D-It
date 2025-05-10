// App entry file for Nail-D It! using Expo (React Native)
import React from 'react';
import { View, Text, Image, StyleSheet } from 'react-native';
import { NavigationContainer } from '@react-navigation/native';
import { createStackNavigator } from '@react-navigation/stack';

const Stack = createStackNavigator();

// Splash Screen
function SplashScreen() {
  return (
    <View style={styles.splashContainer}>
      <Image source={require('./assets/naild-it-logo.png')} style={styles.logo} />
      <Text style={styles.appName}>Nail-D It!</Text>
    </View>
  );
}

// Home Screen placeholder
function HomeScreen() {
  return (
    <View style={styles.screenContainer}>
      <Text style={styles.heading}>Welcome to Nail-D It!</Text>
      <Text style={styles.subheading}>Start designing your dream manicure</Text>
    </View>
  );
}

export default function App() {
  return (
    <NavigationContainer>
      <Stack.Navigator initialRouteName="Splash">
        <Stack.Screen name="Splash" component={SplashScreen} options={{ headerShown: false }} />
        <Stack.Screen name="Home" component={HomeScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

const styles = StyleSheet.create({
  splashContainer: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#fbe9f0', // soft pink tone
  },
  logo: {
    width: 200,
    height: 200,
    resizeMode: 'contain',
  },
  appName: {
    fontSize: 36,
    fontFamily: 'Cochin', // replace with custom cursive font later
    color: '#d291bc',
    marginTop: 20,
  },
  screenContainer: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#fff',
  },
  heading: {
    fontSize: 24,
    fontWeight: 'bold',
    color: '#b76e79',
  },
  subheading: {
    fontSize: 16,
    color: '#7a4e58',
  },
});
