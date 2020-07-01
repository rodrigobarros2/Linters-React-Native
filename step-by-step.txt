0. Deletar prettier e eslint já existente.

1. Instalar extenção editor config
2. Clicar com botão direito generetion .editorconfig
3. Colar dentro do arquivo


root = true

[*]

indent_style = tab
indent_size = 4
charset = utf-8
end_of_line = lf
trim_trailing_whitespace = true
insert_final_newline = true


5. npm install eslint -D
6. npx eslint --init
7. Segue o passo a passo para a instalação do eslint Airbnb (com js)
8. npm install prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D
9. Colocar esse código dentro do .eslintrc

module.exports = {
  env: {
    es6: true,
  },
  extends: [
    'plugin:react/recommended',
    'airbnb',
    'prettier',
    'prettier/react'
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
    __DEV__: 'readonly',
  },
  parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: [
    'react',
    'prettier',
    'react-hooks'
  ],
  rules: {
    'prettier/prettier': 'error',
    'react/jsx-filename-extension': [
        'warn',
        { extensions: ['.jsx', '.js']}
    ],
    'import/prefer-default-export': 'off',
    "no-unused-vars": ["error", { argsIgnorePattern: "^_" }],
    "react/jsx-one-expression-per-line": "off",
    "global-require": "off",
    "react-native/no-raw-text": "off",
    'no-param-reassign': 'off',
    "no-underscore-dangle": "off",
    camelcase: "off",
    'no-console': ['error', { allow: ['tron'] }],
    'react-hooks/rules-of-hooks': 'error',
    'react-hooks/exhaustive-deps': 'warn'
  },
  settings: {
      'import/resolver': {
          'babel-plugin-root-import': {
              rootPathSuffix: 'src'
          }
      }
  },
};

10. criar um arquivo chamado .prettierrc
11. colocar o código abaixo dentro do prettier

{
    "singleQuote": true,
    "trailingComma": "es5"
}

12. npm install babel-plugin-root-import eslint-import-resolver-babel-plugin-root-import -D
(organiza e simplifica os imports)

13. colocar no babel.config.js

module.exports = {
    presets: ['module:metro-react-native-babel-preset'],
    plugins: [
        [
            'babel-plugin-root-import',
            {
                rootPathSuffix: 'src',
            },
        ],
    ],
};

14. colocar no jsconfig.json (Criar)

{
    "compilerOptions": {
        "baseUrl": "src",
        "paths": {
            "~/*": ["*"]
        }
    }
}


12. Fim
