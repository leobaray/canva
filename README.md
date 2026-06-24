# canva

Editor visual node-based para mapear a arquitetura de sistemas — organização visual de como os sistemas de um ambiente se conectam, sem precisar de planilha ou draw.io.

## Visão geral

Ferramenta visual para criar diagramas de arquitetura de forma interativa. Cada node representa um sistema (API, banco de dados, fila, serviço) com categoria e status, e as conexões mostram as relações entre eles. Tudo é salvo no `localStorage` — não perde nada ao recarregar.

## Funcionalidades

- **Canvas interativo** com zoom e pan (botão do scroll para arrastar, scroll para zoom)
- **Nodes** representando sistemas com categoria (API, Banco de Dados, Fila, Serviço, Outro) e status (Ativo, Inativo, Desconhecido)
- **Conexões** entre nodes arrastando de um handle para outro
- **Menu de contexto** (botão direito) no canvas para adicionar sistema ou nota adesiva
- **Menu de contexto** (botão direito) no node para editar ou deletar
- **Notas adesivas** colapsáveis diretamente no canvas
- **Seleção de área** com botão esquerdo
- **Snap-to-grid** (16px) para alinhamento automático
- **Persistência local** via `localStorage`

## Stack

- React 19 + Vite
- React Flow (`@xyflow/react`) — engine do canvas
- Tailwind CSS v4
- Zustand — state management
- Lucide React — ícones

## Rodando

```bash
npm install
npm run dev
```

Abre em `http://localhost:5173`

## Estrutura

```
src/
├── App.jsx                    # Provider raiz (ReactFlowProvider)
├── main.jsx                   # Entry point
├── components/
│   ├── Canvas.jsx             # Canvas principal + context menu
│   ├── SystemNode.jsx         # Node de sistema (categoria + status)
│   ├── SystemEdge.jsx         # Edge estilizada
│   ├── NodeModal.jsx          # Modal de edição de node
│   ├── StickyNote.jsx         # Nota adesiva colapsável
│   ├── TextCard.jsx           # Card de texto
│   ├── ContextMenu.jsx        # Menu de contexto (botão direito)
│   └── GuideLines.jsx         # Linhas guia de alinhamento
├── store/
│   └── useCanvasStore.js      # Store Zustand (nodes, edges, localStorage)
└── utils/
    └── smartPath.js           # Cálculo de caminhos de edges
```

## Licença

[MIT](LICENSE)