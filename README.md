# auditoria-seguranca-lovable-supabase
Checklist público para auditoria de segurança em projetos Lovable + Supabase antes da publicação.
# Auditoria de Segurança para Projetos Lovable + Supabase

Checklist público para builders, desenvolvedores, freelancers, agências e empresas que usam **Lovable + Supabase** e querem reduzir riscos antes de publicar um projeto.

Este material foi criado para ser usado antes de cada publish, ajudando a revisar pontos críticos como banco de dados, RLS, autenticação, permissões, Edge Functions, Storage, webhooks, Stripe, SSRF, IA, mobile e LGPD.

> ⚠️ Este checklist reduz riscos comuns, mas não substitui auditoria profissional, pentest, revisão jurídica/LGPD ou validação de compliance para sistemas regulados.

---

## O que este checklist cobre

- Row Level Security (RLS)
- Secrets e API keys
- Supabase Auth
- Authorization e IDOR
- Edge Functions
- Supabase Storage
- Validação de inputs
- XSS, SQL Injection e SSRF
- Rate limiting
- Webhooks, especialmente Stripe
- Headers de segurança e CORS
- Logs e dados sensíveis
- Dependências
- Configurações do Supabase
- Teste real com visitante anônimo, usuário A e usuário B
- RPC, SQL Functions e SECURITY DEFINER
- Anti-regressão de RLS em migrations
- IA, prompt injection e vazamento de dados para LLM
- Backup, rollback e plano de incidente
- Mobile, Capacitor e App Store

---

## Como usar

1. Abra o arquivo:

   `AUDITORIA-SEGURANCA-LOVABLE-v1.2.1.md`

2. Copie o **Prompt Mestre** e cole no Lovable.

3. Leia o relatório antes de aceitar correções automáticas.

4. Rode os módulos específicos conforme o tipo de projeto.

5. Faça o checklist manual no Supabase, Stripe, hosting e GitHub.

6. Depois de publicar, rode um scanner externo no app deployado.

---

## Para quem serve

Este material é útil para:

- Quem cria apps no Lovable
- Quem usa Supabase como backend
- Quem publica MVPs rapidamente
- Quem cria SaaS, dashboards, sites com login ou apps com IA
- Agências e freelancers que entregam projetos para clientes
- Pequenas empresas que querem reduzir riscos antes de colocar um sistema no ar

---

## Versão atual

**v1.2.1 — Maio/2026**

---

## Licença

Este material está disponível sob licença **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

Você pode usar, adaptar e distribuir, inclusive comercialmente, desde que mantenha a atribuição ao autor original.

Autor original: **Monaco — GrupoMidiaSystems**

---

## Aviso

Segurança não é destino, é processo.  
Este checklist é uma camada prática de revisão, não uma garantia de segurança absoluta.
