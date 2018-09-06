# rn-recaptcha
this is the React native component for Google Recaptch V2

## How to install
```js
 yarn add rn-recaptcha
 npm install rn-recaptcha
```
## How to use 
you can clone this project and check the App.js for see How to use it. 
or just like this.

```js
import React, {Component} from 'react';
import {StyleSheet, View} from 'react-native';
import RNRecaptcha from 'RNRecaptcha';

export default class App extends Component<Props> {
  render() {
    return (
      <View style={styles.container}>
        <RNRecaptcha siteKey={siteKey} onMessage={onMessage} url={testUrl}/>
      </View>
    );
  }
}

const siteKey='6LcWuG4UAAAAAAn1v2RHkpyaE6yaXAc-uyRDSgMG';
const testUrl = 'https://rnrecaptcha.org';

onMessage = event => {
  if ( event && event.nativeEvent.data) {
    console.log(event.nativeEvent.data)
  } else if(event.nativeEvent.data === 'expired'){
    console.log('this is when you expired')
  }else if(event.nativeEvent.data === 'error') {
    console.log('this is when error')
  } else {
    console.log('other')
  }
};


const styles = StyleSheet.create({
  container: {
    flex: 1,
    paddingTop: 20
  },
});
```

siteKey is the siteKey of the Google Recaptcha

testUrl is the url Domain defined on your google Recaptcha

onMessage is the callback function which will be called after the google verification.

## Demo
there is RN Project Demo you can check:
[Demo](https://github.com/aaronisme/RNRecaptchaDemo)

Any Suggestion or Questions, please contact me.