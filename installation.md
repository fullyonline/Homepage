# Installation

## corepack enablen (Node.js version >= 16.10)

```shell
corepack enable
```

## creat react app

```shell
yarn create react-app client --template typescript
```

## react app auf yarn berry upgraden

### node_modules löschen

```shell
cd client
rm -rf node_modules
```

## yarn auf version berry upgraden

```shell
yarn set version berry
```

## anpassungen am .yarnrc.yml

Der nodeLinker: "node_modules" muss raus. Zusätzlich muss noch folgendes rein:

```shell
packageExtensions:
  babel-preset-react-app@*:
    dependencies:
      "@babel/plugin-proposal-private-property-in-object": "*"
```

[Das ist ein workaround für ein Problem mit den dependencies von create react-app.](https://github.com/facebook/create-react-app/issues/11793)

## .gitignore

.gitignore auf der Höhe der React-App löschen. Alles wird über den parent folder gehandelt

## dependencies installieren

```shell
yarn install
```

## oberste Ebene

```shell
cd ..
```

## yarn berry installieren

```shell
yarn init -2
```

## typescript installieren

```shell
yarn add -D typescript
```

## eslint / prettier

### installieren

```shell
yarn add -D eslint prettier eslint-plugin-prettier eslint-config-prettier
```

### wegen typescript

```shell
yarn add -D @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

## wegen React

```shell
yarn add -D eslint-plugin-react eslint-plugin-react-hooks
```

### config erstellen

```shell
yarn create @eslint/config
```

hier alles konfigurieren

### husky / lint-staged

```shell
yarn add -D lint-staged husky
```

### scripts

```shell
"scripts": {
    "lint": "eslint --cache \"src/**/*.{js,jsx,ts,tsx}\"",
    "lint:fix": "eslint --cache --fix \"src/**/*.{js,jsx,ts,tsx}\""
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "*.{js,jsx,ts,tsx}": "yarn run lint:fix"
  },
```

### .prettierrc file:

```shell
{
  "useTabs": false,
  "tabWidth": 4,
  "singleQuote": true,
  "printWidth": 120,
  "trailingComma": "es5"
}
```

### .gitignore file:

```shell
**/.pnp.*
**/.yarn/*
**/node_modules/*
!**/.yarn/patches
!**/.yarn/plugins
!**/.yarn/releases
!**/.yarn/sdks
!**/.yarn/versions
```

## vscode sdk installieren

```shell
yarn dlx @yarnpkg/sdks vscode
```
