# Agilog Ranking — Claude Code Context

## O que é este projeto
Sistema de ranking e gestão de performance de motoristas da Agilog Logística.
É uma **Single Page Application** — todo o código está em `public/index.html`.

## Arquivo principal
`public/index.html` — contém HTML, CSS e JavaScript em um único arquivo (~4500 linhas).

## Como rodar para desenvolvimento
```bash
npm install
npm start
# Acessa em http://localhost:3000
```

## Arquitetura
- **Frontend**: HTML/CSS/JS puro, sem frameworks
- **Dados**: localStorage + Firebase Realtime Database (opcional)
- **Gráficos**: Chart.js 4.4
- **PDFs**: jsPDF + AutoTable
- **Excel**: SheetJS

## Dados principais
```js
DATA = {
  drivers: [],   // motoristas
  trucks: [],    // caminhões/placas
  evals: [],     // avaliações de canhotos
  criteriaConfig: []
}
```

## localStorage keys
- `cr-drivers`, `cr-trucks`, `cr-evals` — dados principais
- `cr-goals` — metas e limiares (global + por motorista)
- `cr-planos` — planos de desenvolvimento
- `cr-users` — usuários do sistema
- `cr-theme` — dark/light
- `cr-fb-url` — URL do Firebase

## Critérios de avaliação
```js
CRITERIA = [
  {key:'boaQualidade', label:'Foto com qualidade', pts:1.6, type:'pos'},
  {key:'naPrancheta',  label:'Está na prancheta',  pts:0.4, type:'pos'},
  {key:'naoTirou',     label:'Não tirou foto',      pts:-2,  type:'neg'},
  {key:'naoPrancheta', label:'Qualidade ruim',      pts:-1.5,type:'neg'},
  {key:'vertical',     label:'Foto vertical/virada',pts:-0.2,type:'neg'},
]
```

## Funções principais para editar
- `renderRanking()` — renderiza o ranking principal
- `renderDashboard()` — renderiza o dashboard
- `renderPlanoDriver()` — plano de desenvolvimento
- `renderAcompanhamento()` — cards de acompanhamento
- `saveData()` / `loadData()` — persistência
- `getAllAppData()` / `restoreAllAppData()` — backup completo

## Usuários e roles
- `admin` — acesso total
- `viewer` — visualização (sem avaliações)
- `driver` — vê apenas seus próprios dados + plano

## Credenciais padrão
- Admin: `adminperte` / `Perte@2026`
- Viewer: `funcionarioperte` / `Func@2026`
- Motoristas: `NOME` / `NOME@perte`
