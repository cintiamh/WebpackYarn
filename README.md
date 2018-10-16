# WebpackYarn

1. [Yarn](#yarn)
2. [Webpack](#webpack)

## Basics

```
$ touch .gitignore
$ mkdir src
$ touch src/index.js
$ mkdir styles
$ touch styles/index.css
```

[.gitignore](.gitignore)

## Yarn

Yarn is a package manager.

### Installation

Using Homebrew
```
$ brew install yarn
```

If you use nvm, intall without node.
```
$ brew install yarn --without-node
```

#### Upgrade

```
$ brew upgrade yarn
```

### Usage

Starting a new project:
```
$ yarn init
```

Adding a dependency:
```
$ yarn add [package]
$ yarn add [package]@[version]
$ yarn add [package]@[tag]
$ yarn add --dev [package]
```

Removing dependency:
```
$ yarn remove [package]
```

Installing all the dependencies of project:
```
$ yarn
$ yarn install
```

## Webpack

### Install

```
$ yarn add --dev webpack webpack-cli
$ touch webpack.config.js
```

[webpack.config.js](webpack.config.js)

Include in `package.json`:
```json
"scripts": {
  "start": "webpack --config webpack.config.js"
}
```

#### Loading CSS

```
$ yarn add --dev style-loader css-loader
```

From your js file, you can just import:
```javascript
import './style.css';
```

#### Loading Images

```
$ yarn add --dev file-loader
```

Now you can import in your JavaScript file:
```javascript
import Icon from './icon.png';
...
var myIcon = new Image();
myIcon.src = Icon;

element.appendChild(myIcon);
```

And use the image in CSS:
```css
.hello {
  background: url('./icon.png');
}
```

#### Loading fonts

```css
@font-face {
  font-family: 'MyFont';
  src: url('./my-font.woff2') format('woff2'),
    url('./my-font.woff') format('woff');
  font-weight: 600;
  font-style: normal;
}
.hello {
  font-family: 'MyFont';
}
```

### Output Management

```
$ yarn add --dev html-webpack-plugin
```

#### Cleaning up the `/dist` folder

```
$ yarn add --dev clean-webpack-plugin
```

### Development

#### Using source maps

Include into webpack.config.js:
```
devtool: 'inline-source-map',
```

#### Using webpack-dev-server

```
$ yarn add --dev webpack-dev-server
```

Include into webpack.config.js
```
devServer: {
  contentBase: './dist'
},
```

Include into scripts in `package.json`:
```
"start": "webpack-dev-server --open"
```
