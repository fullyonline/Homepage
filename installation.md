#was ich alles machen musste

## corepack enablen (Node.js version >= 16.10)

```shell
corepack enable
```

## yarn init

```shell
yarn init -2
```

## typescript

```shell
yarn -D add typescript
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
## vscode sdk installieren

```shell
yarn dlx @yarnpkg/sdks vscode
```
