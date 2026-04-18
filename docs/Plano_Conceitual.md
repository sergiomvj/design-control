# Plano Conceitual - Design Control Pro FBR

## Definição Básica
Sistema web interno FBR para controle solicitações design. Solicitante preenche form detalhado (48 campos 9 seções Marco spec), admin dashboard assign designer, track status (recebido/em-criacao/aprovado/finalizado), filtros prioridade/prazo, notificações SMTP.

**Esboço Sistema:**
- Frontend: Next.js 15 App Router, Tailwind FBR dark tokens, form multi-step Zod val, dashboard React list/grid cards.
- Backend: Prisma/PostgreSQL 16 model Request + attachments/statuslogs, APIs REST (POST submit, GET list/filter, PATCH update), NextAuth RBAC (solicitante/admin/designer).
- Infra: Redis 7 cache, Cloudinary upload, Docker EasyPanel deploy, SMTP emails.
- Security: Zod client/server, RLS Postgres, rate limiting, no SQLi/XSS/CSRF.

**User Flows:**
1. Solicitante → /new-request → multi-step form → submit → email confirmação.
2. Admin → /admin → list/filtros → assign designer → update status.
3. Designer → /dashboard → my tasks → mark done → notify admin.

**ROI Estimado:** 30% menos retrabalho, aprovação 2x mais rápida, histórico specs completos.

**Requisitos Non-Funcionais:** Mobile-first, FBR design standards, Postgres RLS, deploy 1-click EasyPanel.
