# Landing Page — Do Carbono à Educação (Leads IES)

Uma landing page mobile-first, minimalista e rápida para captar emails de gestores de IES interessados em transformar créditos de carbono em permanência estudantil.

## 1) Como funciona
- Single file: `index.html` com Tailwind via CDN e JS vanilla.
- Persistência de leads sem backend: recomendado para GitHub Pages é FormSubmit (sem servidor, sem contas complexas).
- Alternativa: Netlify Forms (se publicar no Netlify).
- Micro-interações discretas (fade-in, ícone de validação, spinner).

## 2) GitHub Pages + FormSubmit (recomendado)

FormSubmit entrega os envios do formulário no seu email, sem servidor. Opções: resposta automática, templates, e painel (conta opcional).

Passos:
1. No `index.html`, procure por `FORMSUBMIT_ENDPOINT` e substitua `SEU_EMAIL_AQUI` pelo seu email (ex.: contato@sua-empresa.com).
2. Faça o deploy no GitHub Pages (repositório → Settings → Pages → Branch main → root).
3. Abra a landing e faça um teste: você deverá receber o email.

Opções úteis do FormSubmit já incluídas:
- `_subject`: assunto do email
- `_captcha: false`: desativa captcha (mantenha honeypot)

Segurança/Privacidade:
- Não publique tokens pessoais em repositórios públicos. Não é necessário token para FormSubmit.

## 3) Rodar localmente
Basta abrir `index.html` no navegador (duplo clique ou via servidor estático). Em macOS, no Terminal:

```zsh
# opcional: um servidor simples com Python
python3 -m http.server 5173
# abra http://localhost:5173
```

## 4) Deploy
- GitHub Pages: simples e gratuito; use FormSubmit.
- Netlify: se preferir painel de submissões nativo, use Netlify Forms.
- Vercel: se quiser evoluir para backend (API Routes) depois, é uma boa opção.

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
- [ ] Deploy no GitHub Pages ativo.
- [ ] `FORMSUBMIT_ENDPOINT` atualizado com seu email.
- [ ] Teste de envio recebido na caixa de entrada.
- [ ] Mobile: layout e tipografia confortáveis (iOS/Android).
- [ ] Animações suaves e sem layout shift.
- [ ] Link de produção pronto para o pitch.

---
Se quiser evoluir para a "Calculadora Visual" (contagem animada de tCO₂e → R$ → alunos) ou social proof, eu adiciono sem comprometer o minimalismo.