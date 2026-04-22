# 🚚 Agilog — Sistema de Ranking de Motoristas

Sistema completo de avaliação e gestão de performance de motoristas para a **Agilog Logística**.

---

## 📁 Estrutura do projeto

```
agilog-ranking/
├── public/
│   └── index.html          ← Todo o sistema (HTML + CSS + JS em um arquivo)
├── server.js               ← Servidor Node.js/Express (opcional)
├── package.json
├── netlify.toml            ← Deploy automático no Netlify
├── vercel.json             ← Deploy automático no Vercel
├── .gitignore
└── README.md
```

---

## 🚀 Como rodar

### Opção A — Direto no navegador (mais simples)
Abra o arquivo `public/index.html` diretamente no Chrome ou Edge. Funciona sem servidor.

### Opção B — VS Code com Live Server
1. Abra a pasta no VS Code: `Arquivo → Abrir Pasta`
2. Instale a extensão **Live Server** (recomendada no workspace)
3. Clique com botão direito em `public/index.html` → **"Open with Live Server"**
4. Acesse: `http://localhost:3000`

### Opção C — Node.js (produção local)
```bash
# Instalar dependências
npm install

# Rodar o servidor
npm start

# Acesse: http://localhost:3000
```

### Opção D — Claude Code
```bash
# Na pasta do projeto
claude

# Peça ao Claude para rodar:
# "sobe o servidor na porta 3000"
```

---

## ☁️ Como colocar no ar (online)

### Netlify (gratuito, recomendado)
1. Crie conta em [netlify.com](https://netlify.com)
2. Clique em **"Add new site" → "Import an existing project"**
3. Conecte ao GitHub ou arraste a pasta `public/` direto
4. O arquivo `netlify.toml` já configura tudo automaticamente
5. Pronto! Você recebe uma URL como `https://seu-site.netlify.app`

### Vercel (gratuito)
1. Crie conta em [vercel.com](https://vercel.com)
2. Instale o CLI: `npm i -g vercel`
3. Na pasta do projeto: `vercel`
4. Siga as instruções no terminal

### GitHub Pages (gratuito)
1. Crie um repositório no GitHub
2. Faça upload dos arquivos
3. Vá em **Settings → Pages → Source → main branch → /public**
4. Acesse: `https://seuusuario.github.io/nome-do-repo`

---

## 🔥 Configurar Firebase (sincronização entre dispositivos)

O sistema já tem Firebase integrado. Para ativar:

1. Acesse [console.firebase.google.com](https://console.firebase.google.com)
2. Crie um projeto (gratuito)
3. Vá em **Realtime Database → Criar banco de dados**
4. Em **Regras**, substitua por:
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }
   ```
5. Copie a URL do banco (ex: `https://meu-projeto-default-rtdb.firebaseio.com`)
6. No sistema: clique em **"Sincronização"** no cabeçalho
7. Cole a URL e clique **Salvar**

Com Firebase ativo, **todos os dados ficam na nuvem** — motoristas, avaliações, metas, planos e configurações sincronizam automaticamente entre qualquer dispositivo.

---

## 💾 Backup manual de dados

Sem Firebase, use a exportação manual:

1. Faça login como **Admin**
2. Vá em **Admin → Backup**
3. Clique em **"Baixar backup completo (JSON)"**
4. Salve o arquivo em local seguro
5. Para restaurar em outro computador: **Admin → Backup → Selecionar arquivo de backup**

---

## 🔐 Credenciais padrão

| Usuário | Senha | Perfil |
|---------|-------|--------|
| `adminperte` | `Perte@2026` | Administrador |
| `funcionarioperte` | `Func@2026` | Visualizador |
| `ARLEI` | `ARLEI@perte` | Motorista |
| `MOISES` | `MOISES@perte` | Motorista |
| *(demais motoristas)* | `NOME@perte` | Motorista |

> ⚠️ **Troque as senhas** após o primeiro acesso em **Admin → Usuários**.

---

## ✨ Funcionalidades

- 📊 **Ranking** por semana, dia ou período customizado
- 📈 **Dashboard** com KPIs, gráficos de evolução e análise por critério
- 🎯 **Metas & KPIs** configuráveis por motorista e por equipe
- 🚀 **Ranking de Evolução** com índice de regressão linear
- 📋 **Plano de Desenvolvimento** individual por motorista
- 📱 **Motoristas** veem seu próprio plano (somente leitura)
- 💾 **Backup** exportar/importar JSON + sincronização Firebase
- 🌙 Modo escuro / claro
- 📄 Exportação PDF e Excel

---

## 🛠️ Tecnologias

- HTML5 + CSS3 + JavaScript puro (sem frameworks)
- Chart.js 4.4 (gráficos)
- jsPDF + AutoTable (exportação PDF)
- SheetJS / XLSX (exportação Excel)
- Firebase Realtime Database (sincronização em nuvem, opcional)

---

*Desenvolvido para Agilog Logística*
