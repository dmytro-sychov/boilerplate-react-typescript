# Boilerplate react with typescript app

## How it is created

### 1. Create react app using create-react-app

```
npx create-react-app boilerplate-react-typescript --template typescript
```

[GitHub](https://github.com/facebook/create-react-app)

### 2. Clean up your project with react-app-cleaner

```
npx react-app-cleaner
```

[GitHub](https://github.com/vinc86/react-app-cleaner)

### 3. Setup ESLint and Prettier

#### 3.1 Install dependencies

Install ESLint

```
npm install eslint --save-dev
```

Initialize the config file

```
npx eslint --init
```

_Note: In the end of the configuration process you will be asked to install dependencies. Choose "Yes"._

Install Prettier

```
npm install -D prettier eslint-config-prettier eslint-plugin-prettier eslint-plugin-react-hooks
```

#### 3.2 Add ESLint and Prettier configurations

Create `.prettierrc` file and add config:

```
{
  "semi": true,
  "tabWidth": 2,
  "printWidth": 100,
  "singleQuote": true,
  "trailingComma": "all",
  "jsxSingleQuote": true,
  "bracketSameLine": true,
  "bracketSpacing": true
}
```

Replace `.eslintrc.json` content with the following config:

```
{
  "env": {
    "browser": true,
    "es2021": true,
    "jest": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:react/recommended",
    "prettier"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["react", "react-hooks", "@typescript-eslint", "prettier"],
  "rules": {
    "react/react-in-jsx-scope": "off",
    "camelcase": "error",
    "spaced-comment": "error",
    "quotes": ["error", "single"],
    "no-duplicate-imports": "error"
  },
  "settings": {
    "react": {
      "version": "detect"
    },
    "import/resolver": {
      "typescript": {}
    }
  }
}
```

#### 3.3 Add scripts to `package.json`

```
{
  ...
  "scripts": {
    ...
    "lint": "eslint src/**/*.{js,jsx,ts,tsx,json}",
    "lint:fix": "eslint --fix 'src/**/*.{js,jsx,ts,tsx,json}'",
    "format": "prettier --write 'src/**/*.{js,jsx,ts,tsx,css,md,json}' --config ./.prettierrc"
  },
  ...
}
```

[Link](https://blog.devgenius.io/eslint-prettier-typescript-and-react-in-2022-e5021ebca2b1)
