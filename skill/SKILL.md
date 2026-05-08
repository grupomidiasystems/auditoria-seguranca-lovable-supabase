---
name: lovable-security-audit
description: Use this skill whenever the user wants to audit, review, or harden the security of a project built with Lovable + Supabase (or similar vibe-coded / AI-generated stacks) BEFORE publishing it. Triggers include any mention of "Lovable", "Supabase", "vibe coding", "auditoria de segurança", "security audit", "antes de publicar", "review security", "RLS", "Row Level Security", "secrets exposed", "IDOR", "SSRF", "webhook Stripe", "edge function security", or when the user uploads a Lovable/Supabase project and asks for a security pass. Also use when the user explicitly asks to "rodar o checklist", "verificar segurança", or pastes the AUDITORIA-SEGURANCA-LOVABLE document.
license: CC-BY-4.0
---

# Lovable Security Audit Skill

Comprehensive, opinionated security audit checklist for projects built with **Lovable + Supabase**, optimized for solo founders, indie hackers, and software houses shipping vibe-coded apps.

Authored by Monaco ([GrupoMidiaSystems](https://grupomidiasystems.com.br)) and licensed under CC BY 4.0.

## When to use this skill

Activate when the user is about to publish a Lovable project, has just published one and wants to harden it, or is reviewing a vibe-coded SaaS for security gaps. Most useful **before** the first paying customer touches the app.

## How to use this skill

The full reference document is `../AUDITORIA-SEGURANCA-LOVABLE-v1.3.0.md` (in the repository root). **Read that file before performing the audit** — it contains the master prompt, 19 modular prompts, manual checklists, SQL diagnostics, curl commands, and prêt-à-coller prompts in Portuguese for the Lovable chat.

### Recommended flow

1. **Read** the reference `.md` in full.
2. **Identify the project context**: standalone web app, multi-tenant SaaS, mobile/Capacitor, AI-heavy, payment-enabled, etc. The reference document has a "tipos de projeto" matrix mapping which modules to prioritize per project type.
3. **Run the master prompt** (the big code block under "PROMPT MESTRE") against the user's project. This generates a structured audit report covering 13 critical areas: RLS, secrets, auth, IDOR, edge functions, storage, input validation, rate limiting, webhooks, CORS/headers, logs, dependencies, Supabase config.
4. **Run extended modules 14–19** as needed: real-attack testing (anonymous / user A / user B), RPC + SECURITY DEFINER, anti-regression of RLS via migrations, AI/prompt injection, incident response, mobile/Capacitor.
5. **Walk the manual checklist** "CHECKLIST PRÉ-PUBLICAÇÃO (Manual)" — checks the user must do in the Supabase dashboard, Stripe dashboard, hosting, and Git that cannot be done from code alone.
6. **Recommend an external scan** post-deploy (Vibe App Scanner, Rafter, Aikido, OWASP ZAP).

### Output format per finding

- **Status**: ✅ OK / ⚠️ Atenção / 🔴 Crítico
- **Findings**: file/line where applicable
- **Risk**: what an attacker can do
- **Fix**: ready-to-paste code or SQL
- **Manual verification**: what the user must check outside the codebase

End with an **executive summary**: total issues by severity, top 3 urgent actions, and an explicit "Safe to publish? YES / NO / WITH CAVEATS" verdict.

## Language

The reference document is written in **Brazilian Portuguese** because the primary audience is Brazilian solo founders and software houses. The skill works in any language — translate findings naturally when the user writes in English; preserve original phrasing when they write in Portuguese.

## Important notes

- **Disclaimer**: this skill reduces common risks but does not replace professional pentest, legal/LGPD review, or compliance validation for regulated systems (health, financial, legal). Pass this caveat to the user.
- **Do not modify code automatically on the first pass**: the reference document is explicit that the first audit is a *report*, not a refactor.
- **Lovable native scanners**: 3 of 4 native scanners (RLS analysis, Database security check, Dependency audit) run automatically before publish; the 4th (Code security review) requires manual click on "Update" in the Security view.
- **JWT in Supabase**: access tokens are stateless and remain valid until `exp` even after logout. Do not falsely claim that logout revokes JWTs.
- **SSRF for arbitrary URLs**: when the audited app accepts arbitrary URLs from users (e.g., site auditing tools), allowlist alone is insufficient. Apply the layered defense described in Module 8.
