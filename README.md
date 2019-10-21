# react-native-rtl-toggle
<p align="left">
  <a href="https://npmjs.org/package/react-native-rtl-toggle"><img alt="npm version" src="http://img.shields.io/npm/v/react-native-rtl-toggle.svg?style=flat-square"></a>
  <a href="https://npmjs.org/package/react-native-rtl-toggle"><img alt="npm version" src="http://img.shields.io/npm/dm/react-native-rtl-toggle.svg?style=flat-square"></a>
</p>
Simple switch toggle component for react-native. This component supports horizontal switch toggle with animation with several options like start/end background colors, start/end circle colors, and duration for animation.
<img src="https://firebasestorage.googleapis.com/v0/b/bookoo-89f6c.appspot.com/o/switch-toggle.gif?alt=media&token=a9dc36e0-3c25-45dc-bbb7-8b095a716dc8"/>

## Changelogs
- **[1.0.6]**
  + Support rtl use I18nManager.
- **[1.0.5]**
  + Support changing state not only from contructor.
- **[1.0.4]**
  + Initial state support.
- **[1.0.3]**
  + Support types.
- **[1.0.1]**
  + Fixed prop-types.
- **[1.0.0]**
  + First time publish.

## Npm repo
https://www.npmjs.com/package/react-native-rtl-toggle

## Git repo
https://github.com/dooboolab/react-native-rtl-toggle

## Props
|    | necessary | types | default
|----|-----|-----|---------|
|switchOn| ✓ | boolean | false |
|onPress| ✓ | func | () => {} |
|containerStyle|  | styles | { width: 72, height: 36, borderRadius: 18 ... } |
|circleStyle|  | styles | { width: 30, height: 30, borderRadius: 15 ... } |
|backgroundColorOn|  | string | 'rgb(227,227,227)' |
|backgroundColorOff|  | string | 'rgb(215,215,215)' |
|circleColorOn|  | string | 'white' |
|circleColorOff|  | string | 'rgb(102,134,205)' |
|duration|  | number | 300

## Getting started
`$ npm install react-native-rtl-toggle --save`

```javascript
import React, { Component } from 'react';
import {
  Platform,
  StyleSheet,
  Text,
  View
} from 'react-native';

import SwitchToggle from 'react-native-rtl-toggle';

export default class App extends Component<{}> {
  constructor(props) {
    super(props);
    this.state = {
      switchOn1: false,
      switchOn2: false,
    };
  }

  render() {
    return (
      <View style={styles.container}>
        <SwitchToggle
          switchOn={this.state.switchOn1}
          onPress={this.onPress1}
        />
        <SwitchToggle
          containerStyle={{
            marginTop: 16,
            width: 108,
            height: 48,
            borderRadius: 25,
            backgroundColor: '#ccc',
            padding: 5,
          }}
          circleStyle={{
            width: 38,
            height: 38,
            borderRadius: 19,
            backgroundColor: 'white', // rgb(102,134,205)
          }}
          switchOn={this.state.switchOn2}
          onPress={this.onPress2}
          circleColorOff='white'
          circleColorOn='red'
          duration={500}
        />
        <SwitchToggle
          containerStyle={{
            marginTop: 16,
            width: 160,
            height: 65,
            borderRadius: 30,
            padding: 5,
          }}
          backgroundColorOn='#a0e1e5'
          backgroundColorOff='#e5e1e0'
          circleStyle={{
            width: 55,
            height: 55,
            borderRadius: 27.5,
            backgroundColor: 'blue', // rgb(102,134,205)
          }}
          switchOn={this.state.switchOn3}
          onPress={this.onPress3}
          circleColorOff='#ff11ff'
          circleColorOn='green'
          duration={500}
        />
      </View>
    );
  }
  onPress1 = () => {
    this.setState({ switchOn1: !this.state.switchOn1 });
  }
  onPress2 = () => {
    this.setState({ switchOn2: !this.state.switchOn2 });
  }
  onPress3 = () => {
    this.setState({ switchOn3: !this.state.switchOn3 });
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#F5FCFF',
  },
});
```
