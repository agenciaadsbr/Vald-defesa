# LP — Vald.Defesa (Advocacia Criminal · Goiás)

Landing page estática (HTML/CSS/JS puro) da Vald.Defesa, mantida pela ADS BR.

## Páginas
- `/` — landing page (`index.html`)
- `/redirect` — obrigado + redirecionamento ao WhatsApp em ~3 s (`redirect.html`)
- `/dashboard` — painel de leads com login (`dashboard.html`)
- `/privacidade` — política de privacidade (`privacidade.html`)

## Configuração
`config.js` → `WHATSAPP_NUMBER` (só dígitos, com 55 + DDD), mensagem e tempo do redirecionamento.

## Dados
Supabase **ADS BR CLIENTES** (`qxhnjzyhtllmtdrcyygi`), tabelas multi-tenant `lp_visits` e `lp_leads` com `site = 'vald-defesa'`.
- A LP grava 1 visita por carregamento e 1 lead por envio (nome, whatsapp, origem) com a anon key.
- O painel só lê com sessão autenticada; o RLS (`pode_ver_site`) libera apenas os sites vinculados ao usuário em `lp_acessos`.
- Login do painel: usuário `admin` → `admin@vald-defesa.adsbr.internal` (senha com a ADS BR).

## Deploy
Vercel (projeto conectado a este repositório). Cada push na `main` publica em produção.
