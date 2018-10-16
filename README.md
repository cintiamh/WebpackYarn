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
