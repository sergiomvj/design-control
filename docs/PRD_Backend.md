# PRD Backend - Design Control Pro

## Models Prisma
- Request: solicitante_nome, empresa, email, telefone, departamento, tipo_projeto enum, descricao_paragrafo, dimensoes, unidade enum, material enum, quantidade, cores, identidade_visual bool, manual_marca bool, acabamento text, logo_vetorial enum, arquivos Cloudinary[], links_ref text, gostou_refs text, nao_quer text, data_entrega date, urgente bool, motivo_urgente text, data_evento date, aprovador_nome, contato_aprovador, num_aprovadores enum, revisoes enum, ciente_custo bool, projeto_os text, responsavel_designer enum, prioridade_interna enum, status enum (recebido/em-analise/em-criacao/em-revisao/aprovado/producao/finalizado), obs_internas text, confirm1/2/3 bool.
  - Relations: attachments[], status_logs[], user (solicitante), designer AssignedTo.
- Attachment: requestId, url Cloudinary, tipo (ref/foto).
- StatusLog: requestId, status_old/new, designer_id, timestamp.

## APIs (App Router)
- POST /api/requests: Submit form → create Request + attachments → email confirm.
- GET /api/requests: List paginated, query filtros (status/prioridade/prazo/departamento).
- PATCH /api/requests/[id]: Update status/assign/designer (RBAC check).
- GET /api/requests/[id]: Detail.

## Auth
- NextAuth RBAC: roles solicitante/admin/designer.

## Infra
- Postgres 16 RLS (row level security por role).
- Redis 7 cache lists.
- Cloudinary upload refs/arquivos.
