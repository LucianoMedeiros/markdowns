# ESLINT + PRETTIER + EditorConfig
> Instalação
```bash 
pnpm add -D eslint eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks @typescript-eslint/eslint-plugin @typescript-eslint/parser prettier eslint-plugin-prettier eslint-config-prettier
```

> Configuração

Criar os seguintes arquivos na raiz do projeto:

**.editorconfig**
```javascript
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = false
insert_final_newline = true

```

**.prettierignore**
```javascript
node_modules
pnpm-lock.yaml
```

**.prettierrc**
```javascript
{
  "jsxSingleQuote": true,
  "singleQuote": true,
  "semi": false,
  "tabWidth": 2,
  "trailingComma": "all",
  "printWidth": 120,
  "bracketSameLine": false,
  "useTabs": false,
  "arrowParens": "always",
  "endOfLine": "auto"
}
```

**.eslintignore**
```javascript
node_modules
```

**.eslintrc**
```javascript
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:jsx-a11y/recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:import/typescript",
    "plugin:react/jsx-runtime",
    "plugin:prettier/recommended",
    "prettier"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["react", "@typescript-eslint", "import", "jsx-a11y", "react-hooks", "prettier"],
  "rules": {
    "@typescript-eslint/no-explicit-any": "off",
    "@typescript-eslint/no-non-null-assertion": "off",
    "@typescript-eslint/no-unused-vars": [
      "warn",
      {
        "argsIgnorePattern": "^_",
        "varsIgnorePattern": "^_",
        "caughtErrorsIgnorePattern": "^_"
      }
    ],

    "react-hooks/rules-of-hooks": "error",
    "react-hooks/exhaustive-deps": "off",

    "prettier/prettier": [
      "warn",
      {
        "semi": false,
        "endOfLine": "auto",
        "singleQuote": true
      }
    ]
  }
}
```

> Instalar extensões:
- Prettier - Code formatter
- ESLint
- EditorConfig for VS Code

> Configuração das extensões

Acessar com **CRTL+**, e clicar no botão no canto superioir direito 
**OpenSettings (JSON)** 

```js
  // FORMATTER
  "prettier.configPath": ".prettierrc",
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "typescript.updateImportsOnFileMove.enabled": "always",
  "javascript.updateImportsOnFileMove.enabled": "always",
```
