# Deep Dash — Site otimizado

## O que foi feito

O seu HTML original tinha **996 KB** porque as 16 imagens estavam embutidas em base64 dentro do próprio arquivo. Isso é o que deixava o site pesado e lento para carregar.

Agora você tem:

- **`index.html`** — 55 KB (redução de 94%)
- **`imagens/`** — pasta com as 16 imagens separadas (707 KB no total)
- Todas as `<img>` têm `loading="lazy"`: a imagem só carrega quando o usuário rola até ela. O site abre instantaneamente mesmo em 4G fraco.

Resultado: o HTML ficou **18 vezes menor**, as imagens carregam sob demanda, e o primeiro "print" na tela do usuário é praticamente imediato.

---

## Como subir no GitHub Pages (passo a passo)

### 1. Criar conta no GitHub (se não tiver)

Acesse https://github.com e crie uma conta gratuita. Anote seu nome de usuário (vou chamar de `SEU-USUARIO` nas instruções).

### 2. Criar um repositório novo

- Clique no `+` no canto superior direito → **New repository**.
- **Repository name:** `deepdash` (pode ser outro nome, mas mantenha simples e sem espaços)
- Marque **Public** (obrigatório para GitHub Pages gratuito)
- Marque **Add a README file**
- Clique em **Create repository**.

### 3. Subir os arquivos

Dentro do repositório recém-criado:

1. Clique em **Add file → Upload files**.
2. Arraste **tudo** que está dentro da pasta `site-deepdash/` (o arquivo `index.html` E a pasta inteira `imagens/`).
3. Role para baixo, deixe a mensagem "Add site files" e clique em **Commit changes**.

O upload dos 16 arquivos de imagem leva uns 30 segundos.

### 4. Ativar o GitHub Pages

1. Dentro do repositório, vá em **Settings** (aba no topo).
2. No menu lateral esquerdo, clique em **Pages**.
3. Em **Source**, selecione **Deploy from a branch**.
4. Em **Branch**, escolha **main** e **/(root)** → clique **Save**.

Em 1 a 2 minutos seu site estará no ar em:

```
https://SEU-USUARIO.github.io/deepdash/
```

Pronto. É só compartilhar esse link.

---

## Perguntas frequentes

**"Preciso editar o HTML para trocar o caminho das imagens?"**
Não. O HTML usa caminhos relativos (`imagens/arquivo.jpg`), ou seja, desde que o `index.html` esteja na mesma pasta que a `imagens/`, tudo funciona — em qualquer host (GitHub Pages, Hostinger, Netlify, Vercel, servidor próprio).

**"Quero usar meu domínio próprio (ex: deepdash.com.br)"**
Dentro do GitHub, em **Settings → Pages**, existe um campo **Custom domain**. Basta apontar o seu domínio lá e configurar um registro DNS. Me chama depois que comprar o domínio que te ajudo com isso.

**"E se eu quiser trocar uma imagem no futuro?"**
Você entra no repositório, vai na pasta `imagens/`, substitui o arquivo (mesmo nome) ou sobe um novo e edita o `index.html` apontando para ele. Alterações ficam online em segundos.

**"Por que o HTML ainda tem 55 KB? Dá pra diminuir mais?"**
Sim. Os próximos passos (se quiser) são:
1. Minificar o CSS e o JavaScript inline (tira ~15 KB a mais).
2. Converter as imagens maiores (a de 390 KB é a mais pesada) para WebP, formato moderno que reduz de 30% a 60% com qualidade idêntica.
3. Usar uma CDN (Cloudflare gratuito) na frente do GitHub Pages para cache global.

Se quiser que eu faça qualquer um desses passos, é só pedir.

---

## O que entregou redução real?

| Item               | Antes     | Depois   | Redução |
|--------------------|-----------|----------|---------|
| HTML               | 996,6 KB  | 54,8 KB  | **94,5%** |
| Requisição inicial | 996,6 KB  | 54,8 KB  | **94,5%** |
| Total (HTML+imgs)  | 996,6 KB  | 762 KB   | 23,5%   |

A grande sacada é a **primeira requisição**: antes o navegador precisava baixar o documento inteiro de 997 KB antes de renderizar qualquer coisa. Agora baixa 55 KB, renderiza, e vai carregando as imagens conforme o usuário rola. É isso que dá a sensação de "site fluido".
