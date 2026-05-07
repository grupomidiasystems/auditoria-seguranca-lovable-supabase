# Changelog

## v1.3.0 — Maio/2026

- Adicionada instrução operacional para o Lovable rodar a auditoria ao receber o `.md`.
- Reduzida a necessidade de o usuário escrever prompts adicionais após anexar o arquivo.
- Adicionada regra para evitar respostas genéricas como “qual opção você quer?”.
- Adicionada orientação para o Lovable escolher uma recomendação padrão segura conforme o tipo de projeto.
- Reforçado que o primeiro passo deve ser relatório de auditoria, sem alteração automática de código.
- Adicionada matriz de decisão automática para projetos pessoais, SaaS, apps com IA, apps com URLs externas e sistemas regulados.

## v1.2.1 — Maio/2026

- Correção do rodapé de versão.
- Atualização do Prompt Mestre para tratar SSRF de forma mais completa.
- Refinamento da frase sobre `search_path` no Módulo 15.

## v1.2 — Maio/2026

- Adicionado disclaimer público.
- Corrigido comportamento de JWT/logout no Supabase.
- Refinada recomendação de `search_path` em funções `SECURITY DEFINER`.
- Adicionada ressalva sobre a amostra independente dos 63%.
- Expandida seção de SSRF para apps que acessam URLs arbitrárias.

## v1.1 — Maio/2026

- Fontes corrigidas.
- Adicionados módulos 14 a 19:
  - Teste real de ataque
  - RPC / SECURITY DEFINER
  - Anti-regressão de RLS
  - IA / prompt injection
  - Backup / incidente
  - Mobile / Capacitor
- Adicionado aviso sobre scanners do Lovable.

## v1.0 — Maio/2026

- Primeira versão pública do checklist.
