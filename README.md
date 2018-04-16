# react-native-svg-from-uri

> This is a fork of the unmaintained [react-native-svg-uri](https://github.com/vault-development/react-native-svg-uri) library, originally written by Matias Cortes.

Render SVG images in React Native from an URL or a static file

This was tested with RN 0.52.0 and [react-native-svg](https://github.com/react-native-community/react-native-svg) 6.3.1, which this library depends on.

## Installation

Install library from `npm`

```bash
npm install react-native-svg-from-uri --save
```

Link the **react-native-svg** library

```bash
react-native link react-native-svg # not react-native-svg-from-uri !
```

## Props

| Prop         | Type          | Default | Note                                                      |
| ------------ | ------------- | ------- | --------------------------------------------------------- |
| `source`     | `ImageSource` |         | Same kind of `source` prop that `<Image />` component has |
| `svgXmlData` | `String`      |         | You can pass the SVG as String directly                   |
| `fill`       | `Color`       |         | Overrides all fill attributes of the svg file             |

## Known Bugs

* [ANDROID] There is a problem with static SVG file on Android,
  Works OK in debug mode but fails to load the file in release mode.
  At the moment the only workaround is to pass the svg content in the svgXmlData prop.
* Not all the svgs can be rendered, if you find problems fill an issue or a PR in
  order to contemplate all the cases

## Usage

Here's a simple example:

```javascript
import SvgUri from "react-native-svg-from-uri";

const TestSvgUri = () => (
  <View style={styles.container}>
    <SvgUri
      width="200"
      height="200"
      source={{
        uri: "http://thenewcode.com/assets/images/thumbnails/homer-simpson.svg"
      }}
    />
  </View>
);
```

or a static file

```javascript
<SvgUri width="200" height="200" source={require("./img/homer.svg")} />
```

This will render:

![Component example](./screenshots/sample.png)

## Testing

1.  Make sure you have installed dependencies with `yarn`
2.  Run tests with `yarn test`
