# ESLinter boilerplate

### 1. Para iniciar el proyecto es necesario crear un ``package.json`` base. Se puede hacer con:
```
npm init
```
### 2. Luego iniciar la instalación de ESLint:
```
npx eslint --init
```
### 3. Agregar configuración en VSCode para la validación al guardar (añadir estos valores en el ``setting.json``):
```
"editor.formatOnSave": false,
"editor.codeActionOnSave": {
  "source.fixAll.eslint": true
}
```
### 4. Podemos arreglar los errors corriendo el comando:
```
npx eslint ./src/**.jsx --fix
```
### 5. Instalar plugin para ``Prettier``:
```
npm install --save-dev eslint-plugin-prettier eslint-config-prettier prettier
```
### 6. Agregar estos valores al archivo ``.eslintrc.json``:
```
"extends": [
  "plugin:prettier/recommended"
],
"plugins": [
  "prettier"
],
"rules": [
  "prettier/prettier": "error"
]
```
### 7. Añadir plugin para ordenar los imports con ```eslint-plugin-import```:
```
npm install eslint-plugin-import --save-dev
```
```
"plugins": [
  "order"
]
```
```
"rules": [
  "import/order": ["warn", {
    "pathGroups": [{
      "pattern": "~/**",
      "group": "external",
      "position": "after"
    }],
    "newlines-between": "always"
  }]
]
```