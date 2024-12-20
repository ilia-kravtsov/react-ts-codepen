# React + TypeScript + Vite

pnpm init # инициализация pnpm:

pnpm create vite # установка Vite с шаблоном React + TypeScript:

pnpm install # 

Структура проекта:

react-js-ts-codepen/
├── public/
├── src/
│    ├── assets/
│    ├── components/
│    ├── hooks/
│    ├── pages/
│    ├── styles/
│    └── App.tsx
├── index.html
├── tsconfig.json
├── vite.config.ts
├── .gitignore
├── package.json
└── pnpm-lock.yaml

Обновите tsconfig.json: Это позволит использовать алиасы @components, @hooks, и т.д.

{
"compilerOptions": {
"target": "ESNext",
"module": "ESNext",
"moduleResolution": "Node",
"jsx": "react-jsx",
"strict": true,
"baseUrl": "./src",
"paths": {
"@components/*": ["components/*"],
"@hooks/*": ["hooks/*"],
"@pages/*": ["pages/*"],
"@styles/*": ["styles/*"]
}
},
"include": ["src"]
}

Добавьте скрипты для удобного запуска и сборки проекта:

"scripts": {
"dev": "vite",
"build": "vite build",
"preview": "vite preview",
"lint": "eslint . --ext .js,.ts,.jsx,.tsx",
"format": "prettier --write ."
}

Установка линтеров и форматтеров

pnpm add -D eslint prettier eslint-config-prettier eslint-plugin-react eslint-plugin-react-hooks

Создайте .eslintrc.js:

module.exports = {
env: {
browser: true,
es2021: true
},
extends: [
'eslint:recommended',
'plugin:react/recommended',
'plugin:react-hooks/recommended',
'prettier'
],
parserOptions: {
ecmaFeatures: {
jsx: true
},
ecmaVersion: 'latest',
sourceType: 'module'
},
plugins: ['react'],
settings: {
react: {
version: 'detect'
}
},
rules: {
'react/react-in-jsx-scope': 'off'
}
};
