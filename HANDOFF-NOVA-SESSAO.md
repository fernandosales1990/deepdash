# Handoff — Projeto Deep Dash

Cole essa mensagem inteira no início da nova conversa (com Claude Sonnet) para o assistente já entrar com todo o contexto.

---

## Contexto do projeto

Sou o **Fernando** (sales.fernando1990@gmail.com). Tenho uma marca de **música eletrônica chamada Deep Dash** — a gente faz festas. Criei um site para a marca, mas o site estava inteiro em um único arquivo HTML muito pesado (996 KB) porque as imagens estavam todas embutidas em base64 dentro do próprio código.

O arquivo original chama-se `deepdash-v2_63.html`.

## O que já foi feito na sessão anterior

1. **Extraí as 16 imagens embutidas** do HTML para arquivos separados em uma pasta `imagens/`.
2. **Reescrevi o HTML** usando caminhos relativos (`imagens/arquivo.jpg`) em vez de base64.
3. **Adicionei `loading="lazy"`** em todas as `<img>` para carregamento sob demanda.
4. Resultado: HTML caiu de **996 KB para 55 KB** (redução de 94,5%).

## Decisões já tomadas (preferências do Fernando)

- **Hospedagem escolhida:** GitHub Pages (gratuito).
- **Otimização/compressão de imagens:** NÃO comprimir — manter qualidade original.
- **Lazy loading:** SIM, ativado em todas as imagens.

## Arquivos atuais na pasta `site-deepdash/`

- `index.html` (55 KB) — HTML limpo, caminhos relativos, lazy loading.
- `imagens/` — 16 arquivos (3 PNG grandes + 13 JPG), total 707 KB.
- `LEIA-ME.md` — passo a passo de upload no GitHub Pages.
- `manifest.txt` — lista das imagens com tamanhos.

## Tamanhos das imagens extraídas

A maior de todas é `img-03-10b145b73e.png` com **390 KB** (provavelmente o logo/hero principal) — é a candidata óbvia para otimizar se quiser reduzir mais.

## Próximos passos em aberto (o que ainda posso querer fazer)

1. **Subir tudo no GitHub Pages** — seguir o `LEIA-ME.md`.
2. **Otimizações adicionais** (opcionais, não decididas ainda):
   - Converter imagens para **WebP** (reduz 30–60% com qualidade idêntica).
   - Minificar o CSS e JavaScript inline (~15 KB a mais de redução).
   - Colocar **Cloudflare gratuito** na frente do GitHub Pages (CDN global + cache).
3. **Domínio próprio** (ex: `deepdash.com.br`) — se eu comprar, preciso de ajuda pra apontar DNS.
4. **Marketing** — eventualmente posso querer falar sobre branding, tráfego pago, redes sociais, etc. (temos skill `agencia-marketing` disponível).

## Como prefiro trabalhar

- Fala em português direto.
- Explica decisões técnicas de forma simples (não sou dev).
- Se tiver trade-off, me diz qual é e recomenda o melhor caminho.
- Antes de começar trabalho grande, me pergunta as opções.

---

**Comece a próxima conversa perguntando o que eu quero fazer em seguida, ou continue de onde parou se eu já mandar uma tarefa nova.**
