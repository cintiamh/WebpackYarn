# WebpackYarn

1. [Basics](#basics)
2. [Yarn](#yarn)
3. [Webpack](#webpack)
4. [Babel](#babel)
5. [ESLint](#eslint)

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
$ yarn add --dev webpack webpack-cli webpack-merge
$ touch webpack.common.config.js
$ touch webpack.dev.config.js
$ touch webpack.prod.config.js
```

* [webpack.common.config.js](webpack.common.config.js)
* [webpack.dev.config.js](webpack.dev.config.js)
* [webpack.prod.config.js](webpack.prod.config.js)

Include in `package.json`:
```json
"scripts": {
  "build": "webpack --config webpack.prod.config.js",
  "start": "webpack-dev-server --config webpack.dev.config.js --hot --inline"
}
```

#### Loading CSS

```
$ yarn add --dev style-loader css-loader mini-css-extract-plugin
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
$ yarn add --dev html-webpack-plugin html-loader
$ touch src/index.html
```

#### Cleaning up the `/dist` folder

```
$ yarn add --dev clean-webpack-plugin
```

### Development

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

#### Using webpack-dev-middleware

```
$ yarn add --dev express webpack-dev-middleware
$ touch server.js
```

In webpack.config.js, add publicPath into output:
```javascript
output: {
  filename: '[name].bundle.js',
  path: path.resolve(__dirname, 'dist'),
  publicPath: '/'
}
```

## Babel

```
$ yarn add --dev @babel/core babel-loader @babel/preset-env @babel/preset-react
$ touch .babelrc
```

[.babelrc](.babelrc)

Add loader to webpack.config.js
```
{
  test: /\.js$/,
  exclude: /node_modules/,
  use: ['babel-loader']
},
```

## ESLint

```
$ yarn add --dev eslint eslint-loader
$ touch .eslintignore
$ ./node_modules/.bin/eslint --init
```
[.eslintignore](.eslintignore)

package.json
```javascript
"scripts": {
  "lint": "eslint . --ext .js",
}
```

## React

```
$ yarn add react react-dom
```
