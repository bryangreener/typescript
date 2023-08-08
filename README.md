# TypeScript

This repo contains test projects created while learning TypeScript.


## Requirements

- [nvm](https://github.com/nvm-sh/nvm)
- [yarn](https://classic.yarnpkg.com/)

## Environment Setup

1. Install NVM

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | zsh
```

1. Restart terminal

```bash
exec zsh
```

1. Install `NodeJS` and `NPM`

```bash
nvm install --lts
nvm use --lts
```

1. Install `Yarn`

```bash
npm install -g yarn
```

1. Initialize a new project directory.

```bash
mkdir ./my_project
cd ./my_project
yarn init
```

1. Install the Node Types and TypeScript compiler locally to the project.

```bash
yarn add @types/node
yarn add typescript --dev
```

Optionally, add `ts-node` to run code without compiling.

```bash
yarn add -D ts-node
```

1. Setup TypeScript for the project.

```bash
yarn tsc \
    --init \
    --rootDir src \
    --outDir ./bin \
    --esModuleInterop \
    --lib ES2019 \
    --module commonjs \
    --noImplicitAny true
mkdir src
echo "console.log('Hello World\!\!\!')" > src/app.ts
```

1. Add shortcut commands to your project's `package.json` file just before the `dependencies` section.

```json
"scripts": {
    "build": "tsc",
    "start": "node ./bin/app.js",
    "dev": "ts-node ./src/app.ts"
},
```

## Building Project

```bash
yarn build
```

Output is put in the `./bin` folder unless you specified a different location when initializing typescript.

## Running Project

Running compiled code:

```bash
yarn start
```

Alternatively, run the project using `ts-node` to speed up testing.

```bash
yarn dev
```
