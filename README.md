# luxtory-e5-authorizer-sandbox

Repositório de teste **descartável** da etapa E5 da W13 (Luxtory Branded Second Home, spec `booking` §10.16).
Prova o workflow do autorizador independente num GitHub Environment de teste (`booking-authorizer`: revisor
obrigatório, só a branch `main`, secrets sintéticos só no Environment), contra um PostgreSQL descartável criado
dentro do próprio job. Sem dados reais, sem credenciais reais, sem conexão com Production.

Conteúdo: arquivos públicos copiados do repositório principal (branch `feat/w13-e5-autorizador`, base
`caa699c2f6d6d21b1f0fbca415f56da35c39f02f`), sem alteração, exceto o workflow: em `.github/workflows/booking-authorizer.yml`
está a variante `tests/fixtures/booking-authorizer-sandbox.yml` (o workflow real mais o overlay de sandbox).
Hash de blob do Git de cada arquivo de origem (`git hash-object`):

```
577a586521659e5d91dcc43efa091a48942adcf7  package.json
adf009ed9694508f8dbf2acb956c5b1e3397f8ef  package-lock.json
7a13826f299a2db863984790888b3718c00286e5  .npmrc
8defe5b71e9eaf01ac4e0267aa8748fc0698f1f9  scripts/booking-authorizer.mjs
e80bfbab16311393761f29967fdf98f0b17e718d  scripts/lib/pg.mjs
6354633f5b66efe59a1a8e054f625571688f5de9  scripts/lib/supabase-compat.sql
d5461ffb5257672b46dfdeb426ebec43f008885e  scripts/lib/dbmate.mjs
84ba1de39f459f7d57bc2938ad2382d9da0a7d85  src/features/platform/infrastructure/database/supabase-root-ca.ts
23a80944853060f7e61ae8584790ff00b2b435f4  tests/support/booking-authorizer-sandbox-db.mjs
cdc4e7dbdcf795e72b6a55f89ffc97c7bf140ad2  tests/fixtures/booking-authorizer-sandbox.yml
9569c5531164669db31b547bb4c94fb062170d49  .github/workflows/booking-authorizer.yml
6369fbf272f4baa9a7f9b1ebb66f5623cd132c8e  migrations/*.sql (concatenados, 60 arquivos)
```

Atualizado em 2026-11-18 com a correção T-1321 (entrada lida do arquivo do evento, não do `env:` do passo).

Pode ser apagado depois da auditoria da E5.
