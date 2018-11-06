# React Native: react-native-intent-player

[![github home](http://img.shields.io/npm/v/react-native-intent-player.svg?style=flat)](https://www.npmjs.com/package/react-native-intent-player)
![platforms](https://img.shields.io/badge/platforms-Android-brightgreen.svg?style=flat&colorB=191A17)
[![github home](https://img.shields.io/badge/gaetanozappi-react--native--intent--player-blue.svg?style=flat)](https://github.com/gaetanozappi/react-native-intent-player)
[![npm](https://img.shields.io/npm/dm/react-native-intent-player.svg?style=flat&colorB=007ec6)](https://www.npmjs.com/package/react-native-intent-player)

[![github issues](https://img.shields.io/github/issues/gaetanozappi/react-native-intent-player.svg?style=flat)](https://github.com/gaetanozappi/react-native-intent-player/issues)
[![github closed issues](https://img.shields.io/github/issues-closed/gaetanozappi/react-native-intent-player.svg?style=flat&colorB=44cc11)](https://github.com/gaetanozappi/react-native-intent-player/issues?q=is%3Aissue+is%3Aclosed)
[![Issue Stats](https://img.shields.io/issuestats/i/github/gaetanozappi/react-native-intent-player.svg?style=flat&colorB=44cc11)](http://github.com/gaetanozappi/react-native-intent-player/issues)
[![github license](https://img.shields.io/github/license/gaetanozappi/react-native-intent-player.svg)]()

![PNG](screenshot/react-native-intent-player.jpeg)

-   [Usage](#-usage)
-   [License](#-license)

## 📖 Getting started

`$ npm install react-native-intent-player --save`

`$ react-native link react-native-intent-player`

#### Android

Add `react-native-intent-player` to your `./android/settings.gradle` file as follows:

```diff
...
include ':app'
+ include ':react-native-intent-player'
+ project(':react-native-intent-player').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-intent-player/android/app')
```

Include it as dependency in `./android/app/build.gradle` file:

```diff
dependencies {
    ...
    compile "com.facebook.react:react-native:+"  // From node_modules
+   compile project(':react-native-intent-player')
}
```

Finally, you need to add the package within the `ReactInstanceManager` of your
MainActivity (`./android/app/src/main/java/your/bundle/MainActivity.java`):

```java
import com.reactlibrary.PlayerPackage;  // <---- import this one
...
@Override
protected List<ReactPackage> getPackages() {
    return Arrays.<ReactPackage>asList(
        new MainReactPackage(),
        new PlayerPackage()  // <---- add this line
    );
}
```

After that, you will need to recompile
your project with `react-native run-android`.

## 💻 Usage

```javascript
import React, { Component } from 'react';
import Player from 'react-native-intent-player';

type Props = {};
export default class App extends Component<Props> {
  
  constructor(props) {
    super(props);
    this.state = {
      url: 'https://www.w3schools.com/html/mov_bbb.mp4',
    };
  }

  componentDidMount() {
    Player.play(this.state.url)
      .then(a => {
        console.log(a);
      })
      .catch(e => console.log(e));
  }

  render() {
    return null;
  }
}
```

## 📜 License
This library is provided under the Apache License.
