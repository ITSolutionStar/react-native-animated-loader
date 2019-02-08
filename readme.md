# React Native Animated Loader

A React Native Loader Component which uses Airbnb's [Lottie](https://github.com/react-native-community/lottie-react-native) for beautiful loader animations.

## Prerequisites
This library uses [lottie-react-native](https://github.com/react-native-community/lottie-react-native) to render loader animations. Therefor this library need to be installed and linked to your project before installing this package.

Follow the official instruction and linking guide [here](https://github.com/react-native-community/lottie-react-native/blob/master/README.md#getting-started).

## Install

```
yarn add react-native-animated-loader
```
or
```
npm i --save react-native-animated-loader
```

## Usage

```jsx
import React from 'react';
import AnimatedLoader from "react-native-animated-loader";

export default class Loader extends React.Component {
  constructor(props) {
    super(props);
    this.state = { visible: true };
  }

  componentDidMount() {
    setInterval(() => {
      this.setState({
        spinner: !this.state.visible
      });
    }, 3000);
  }

  render() {
    const { visible } = this.state;
    return (
      <AnimatedLoader
        visible={visible}
        overlayColor="rgba(255,255,255,0.75)"
        source={require("./loader.json")}
        animationStyle={styles.lottie}
        speed={1}
      />
    );
  }
}
```

## API

| Prop | Description | Default |
|---|---|---|
|**`source`**| The source of animation. Can be referenced as a local asset by a string, or remotely with an object with a `uri` property, or it can be an actual JS object of an animation, obtained (for example) with something like `require('../path/to/animation.json')`. | [Lottie Object](https://lottiefiles.com/1531-loader) |
|**`visible`**| Controls the visibility of the loader. | `false` |
|**`overlayColor`**| Changes the color of the overlay. | `rgba(255,255,255,0.75)` |
|**`animationStyle`**| The style to be applied to the Lottie. | - |
|**`animationType`**| Changes animation on show and hide loader's view. | `none` |

## TODOs
- [ ] Add expo example
- [ ] Add ability to render text with animations

## License
Licensed under the [MIT](https://github.com/vikrantnegi/react-native-animated-loader/blob/master/LICENSE).