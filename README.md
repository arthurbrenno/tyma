# Landing Page — Do Carbono à Educação (Leads IES)

Uma landing page mobile-first, minimalista e rápida para captar emails de gestores de IES interessados em transformar créditos de carbono em permanência estudantil.

## 1) Como funciona
- Single file: `index.html` com Tailwind via CDN e JS vanilla.
- Persistência de leads sem backend próprio usando Netlify Forms.
- Micro-interações discretas (fade-in, ícone de validação, spinner).

## 2) Persistência mais simples: Netlify Forms

Você não precisa configurar planilha nem backend. Ao publicar no Netlify, os envios ficam visíveis no painel (Forms → Submissions) e você pode exportar CSV, receber notificações por email ou integrar com Zapier.

O que já está pronto no `index.html`:
- `<form name="lead" method="POST" data-netlify="true" netlify-honeypot="bot-field">`
- Campo oculto `form-name`, honeypot, e submissão manual via `fetch('/')` com `application/x-www-form-urlencoded`.

Passos:
1. Crie um site no Netlify e faça o deploy desta pasta.
2. Acesse Netlify → Forms. Você verá o formulário `lead` detectado automaticamente após o primeiro envio.
3. Opcional: ative notificações por email, webhooks, ou exporte CSV.

## 3) Rodar localmente
Basta abrir `index.html` no navegador (duplo clique ou via servidor estático). Em macOS, no Terminal:

```zsh
# opcional: um servidor simples com Python
python3 -m http.server 5173
# abra http://localhost:5173
```

## 4) Deploy
- Netlify (recomendado para Forms): arraste a pasta (ou conecte ao repositório). O formulário funciona automaticamente.
- Vercel/Outros: funcionará visualmente, mas o Netlify Forms não processa fora do Netlify.

## 5) Personalização rápida
- Logo: substitua `logo.png`. O layout aplica leve "glow" para melhorar contraste.
- Headline/CTA: edite direto no HTML.
- Cores: altere o objeto `tailwind.config` inline no `index.html`.

## 6) Acessibilidade e boas práticas
- Labels e mensagens de erro claras.
- Focus states visíveis.
- Contraste AA em fundo escuro.
- Inputs com `type="email"` e `inputmode="email"` para mobile.

## 7) Checklist antes de apresentar
- [ ] Deploy no Netlify concluído.
- [ ] Teste de envio: verifique a submissão em Netlify → Forms.
- [ ] Mobile: layout e tipografia confortáveis (iOS/Android).
- [ ] Animações suaves (transform/opacity apenas).
- [ ] Link de produção pronto para o pitch.

---
Se quiser evoluir para a "Calculadora Visual" (contagem animada de tCO₂e → R$ → alunos) ou social proof, eu adiciono sem comprometer o minimalismo.