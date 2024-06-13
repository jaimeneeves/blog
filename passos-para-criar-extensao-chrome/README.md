# Passos Para Criar Uma Extensão no Chrome

Para criar uma extensão para o Google Chrome, você precisa seguir alguns passos básicos. Vou te guiar através desses passos, começando com uma descrição do que você precisa fazer e um exemplo básico de código.

## Passos para Criar uma Extensão de Navegador:

1. **Estrutura do Projeto**: Organize seu projeto com os arquivos necessários.

2. **Manifest File**: Crie um arquivo `manifest.json` que descreve a extensão.

3. **Arquivos HTML/CSS/JavaScript**: Crie os arquivos que definem a funcionalidade da sua extensão.

4. **Teste e Empacotamento**: Teste sua extensão no navegador e, se tudo estiver correto, empacote para distribuição.

### 1. Estrutura do Projeto

Estruture seu projeto da seguinte forma:

```sh
my_extension/
├── manifest.json
├── background.js
├── popup.html
├── popup.js
└── styles.css
```

### 2. Criar o manifest.json

O `manifest.json` é o arquivo mais importante, pois descreve a extensão e suas configurações.

```json
{
  "manifest_version": 3,
  "name": "Minha Extensão",
  "version": "1.0",
  "description": "Uma extensão de exemplo",
  "permissions": [
    "activeTab",
    "storage"
  ],
  "action": {
    "default_popup": "popup.html",
    "default_icon": {
      "16": "icons/icon16.png",
      "48": "icons/icon48.png",
      "128": "icons/icon128.png"
    }
  },
  "background": {
    "service_worker": "background.js"
  },
  "icons": {
    "16": "icons/icon16.png",
    "48": "icons/icon48.png",
    "128": "icons/icon128.png"
  }
}
```

### 3. Criar os Arquivos HTML, CSS e JavaScript

**popup.html**

```html
<!-- popup.html -->

<!DOCTYPE html>
<html>
<head>
  <title>Popup</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1>Minha Extensão</h1>
  <button id="actionButton">Clique Aqui</button>
  <script src="popup.js"></script>
</body>
</html>
```

**styles.css**

```css
/* styles.css */

body {
  width: 200px;
  padding: 10px;
  font-family: Arial, sans-serif;
}

button {
  width: 100%;
  padding: 10px;
  margin-top: 10px;
}
```

**popup.js**

```js
// popup.js

document.getElementById('actionButton').addEventListener('click', () => {
  alert('Botão clicado!');
});
```

**background.js**

```js
// background.js

chrome.runtime.onInstalled.addListener(() => {
  console.log('Extensão instalada.');
});
```

### 4. Testar e Empacotar a Extensão

1. **Teste**: Para testar sua extensão, abra o Chrome e vá para `chrome://extensions/`. Ative o `Modo de desenvolvedor` e clique em `Carregar sem compactação`. Selecione a pasta do seu projeto.

2. **Empacotar**: Para empacotar sua extensão, clique no botão "Empacotar extensão" na página `chrome://extensions/`.


## Próximos Passos:

Se precisar de ajuda com qualquer parte específica ou tiver dúvidas sobre funcionalidades adicionais, sinta-se à vontade para perguntar!

