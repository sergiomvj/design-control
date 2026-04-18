# PRD Frontend - Design Control Pro

## Páginas/Rotas
- /new-request: Form multi-step 9 seções exatas Marco spec (ID solicitante, tipo solicitação, descrição projeto, specs técnicas, refs/arquivos, prazo/prioridade, aprovação, controle interno, confirmação).
  - Zod validation (required, enums, dates).
  - Progress steps visual (1-9).
  - File upload Cloudinary (PDF/AI/PNG/JPG).
  - FBR design tokens (dark bg #0b0f16, accent #d91f26, grid-2 mobile 1fr).
- /admin: Dashboard admin list cards requests, filtros (status/prioridade/prazo/departamento), search nome/empresa, assign designer dropdown, update status badges (recebido/em-criacao/aprovado/finalizado).
  - Stats cards total/pendentes/urgentes.
  - Pagination/export CSV.
- /dashboard: Designer view my tasks, mark done.

## Componentes
- FormStep: Multi-step wrapper.
- StatusBadge, PriorityBadge.
- RequestCard: Card list dashboard.
- FilterBar: Selects/multi-choice filtros.

## UX
- Mobile-first, animações fade-in.
- Validação real-time, errors inline.
- Loading spinners submit/upload.
