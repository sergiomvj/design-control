# PRD Backend - Design Control Pro

**Model Prisma Request:**
- Campos spec (solicitante, tipo, descricao, specs, refs, prazo, aprovacao, controle).
- Relations User/Attachments/StatusLog.

**APIs:**
- POST /api/requests: Submit form.
- GET /api/requests: List/filtros.
- PATCH /api/requests/[id]: Status/assign.

**Stack:** Prisma/PostgreSQL 16, Redis 7 cache, NextAuth RBAC, Zod server val, Cloudinary upload.
