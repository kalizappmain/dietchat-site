# ChatDiet — Site Oficial

Site estático pronto para deploy no Vercel, atendendo todos os requisitos do **Meta (Facebook) Developers**.

## Estrutura

```
chatdiet-site/
├── vercel.json          ← Configuração do Vercel com headers de segurança
├── public/
│   ├── index.html       ← Landing page principal
│   ├── privacy.html     ← Política de Privacidade (LGPD + GDPR + Meta)
│   ├── deletion.html    ← Página de Exclusão de Dados (Data Deletion Instructions URL)
│   └── terms.html       ← Termos de Serviço
```

## Deploy no Vercel (gratuito)

### Opção 1 — Via GitHub (recomendado)

1. Crie um repositório no GitHub e suba os arquivos
2. Acesse [vercel.com](https://vercel.com) e faça login com GitHub
3. Clique em **"Add New Project"** → importe o repositório
4. Clique em **Deploy** — pronto!

### Opção 2 — Via Vercel CLI

```bash
npm i -g vercel
cd chatdiet-site
vercel --prod
```

### Opção 3 — Drag & Drop

1. Acesse [vercel.com/new](https://vercel.com/new)
2. Arraste a pasta `chatdiet-site` para a área de upload
3. Aguarde o deploy

---

## Configuração no Facebook Developers

Após o deploy, acesse o [Facebook Developers](https://developers.facebook.com/apps/) e configure:

| Campo | URL |
|-------|-----|
| **Privacy Policy URL** | `https://seu-app.vercel.app/privacy.html` |
| **Terms of Service URL** | `https://seu-app.vercel.app/terms.html` |
| **Data Deletion Instructions URL** | `https://seu-app.vercel.app/deletion.html` |
| **App Domains** | `seu-app.vercel.app` |

### Checklist de conformidade Meta ✅

- [x] Política de privacidade publicamente acessível (não geo-bloqueada)
- [x] URL de exclusão de dados (LGPD/GDPR/Meta Policy)
- [x] Política explica quais dados são coletados via Facebook Login
- [x] Política explica como o usuário pode solicitar exclusão
- [x] Página de exclusão com instruções claras (Data Deletion Instructions URL)
- [x] Site com HTTPS (garantido pelo Vercel)
- [x] Headers de segurança (X-Frame-Options, CSP, etc.)
- [x] Metadados Open Graph para Facebook

---

## Personalização

Substitua nos arquivos HTML:
- `chatdiet.vercel.app` → sua URL real do Vercel
- `privacidade@chatdiet.app` → seu e-mail real
- `contato@chatdiet.app` → seu e-mail de contato
- `ChatDiet Ltda` → nome da sua empresa (se aplicável)
- `© 2025 ChatDiet` → atualize conforme necessário

---

## Segurança

O `vercel.json` já inclui headers de segurança:
- `X-Content-Type-Options: nosniff`
- `X-Frame-Options: SAMEORIGIN`
- `X-XSS-Protection: 1; mode=block`
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Content-Security-Policy` configurada
- HTTPS automático pelo Vercel
