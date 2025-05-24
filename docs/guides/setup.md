# Setup

## Pré-requisitos

Antes de começar, certifique-se de ter:

- Node.js instalado
- npm ou yarn
- Docsify CLI

## Instalação

### 1. Instalar Docsify CLI

```bash
npm install -g docsify-cli
```

### 2. Inicializar projeto

```bash
docsify init ./docs
```

### 3. Servir localmente

```bash
docsify serve docs
# ou
npm run docs
```

A documentação estará disponível em `http://localhost:8080`

## Configuração

### Personalizar index.html

Edite o arquivo `docs/index.html` para personalizar:

- Nome do projeto
- Tema
- Plugins
- Configurações gerais

### Exemplo de configuração

```javascript
window.$docsify = {
  name: "Minha Documentação",
  repo: "https://github.com/usuario/repo",
  loadSidebar: true,
  autoHeader: true,
  subMaxLevel: 2,
  coverpage: true,
  search: "auto",
};
```

## Estrutura de arquivos

```
docs/
├── README.md        # Página inicial
├── index.html       # Configuração principal
├── _sidebar.md      # Menu lateral
├── _coverpage.md    # Página de capa
└── guides/          # Pasta de guias
    └── setup.md     # Este arquivo
```

## Próximos passos

- Customize o tema
- Adicione mais páginas
- Configure plugins adicionais
- Configure deploy (GitHub Pages, Netlify, etc.)
