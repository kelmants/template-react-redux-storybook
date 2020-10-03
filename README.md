## Create CRA

npx create-react-app

## install prettier, eslint, lint-staged and husky

https://prettier.io/docs/en/install.html

- yarn add --dev --exact prettier && echo {}> .prettierrc.json && echo serviceWorker.js> .prettierignore && yarn prettier --write . && prettier --check .
- yarn add eslint eslint-config-prettier eslint-plugin-jest --dev && yarn run eslint --init
- extends [ "prettier", "prettier/react" ]
- add plugin jest

```
{
  "plugins": ["jest"]
}
```

## Add rules to prettierrc.json file

```
{
  "singleQuote": true,
  "endOfLine": "lf",
  "semi": false,
  "trailingComma": "es5"
}
```

#### You can also tell ESLint about the environment variables provided by Jest by doing:

```
{
  "env": {
    "jest/globals": true
  }
}
```

- add scripts lint and prettier

```
    "format": "yarn prettier --write ."
    "lint": "eslint --ext .jsx,.js --fix ."
```

- yarn add husky --dev
- npx mrm lint-staged
- add into packages.json this configuration

```
{
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "**/*": "prettier --write --ignore-unknown"
  }
}
```
