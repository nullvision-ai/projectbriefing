# Landing page de briefing — nullvision

Página única (`index.html`), sem dependências externas além das fontes do Google. O cliente escolhe a
categoria (Cinematic/Motion/Design), preenche o formulário (só nome e e-mail são obrigatórios, o resto
é opcional/livre) e envia — o envio vai direto pro e-mail da empresa via
[Formspree](https://formspree.io), chave `mgaevdgg`. Uma cópia é encaminhada automaticamente pro Gmail
pessoal do Matheus (configurado nas próprias configurações do Gmail da empresa) — é essa cópia que o
Claude lê pra processar os briefings.

**No ar em:** https://nullvision-ai.github.io/projectbriefing/ — é esse o link da bio do Instagram.

## Atenção: repositório duplicado

Existe um segundo repositório, `contatomateusaraujom-ctrl/nullvision-briefing`, que foi a primeira
tentativa de publicação. Ele **também está no ar** e aponta para um formulário Formspree **diferente**
(`mgaevrln`) — qualquer briefing enviado por lá cai numa caixa que ninguém acompanha.

Este repositório (`nullvision-ai/projectbriefing`) é o oficial. O outro deve servir apenas como
redirecionamento, nunca como cópia paralela do formulário.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | a landing page do briefing |
| `og-image.png` | imagem de preview (1200×630) ao compartilhar o link |
| `nullvision_brand_identity_v2.html` | referência de identidade visual |
| `nullvision_graphic_elements.html` | elementos gráficos da marca |

## Publicar uma alteração

A pasta local é um clone deste repositório, então publicar é commitar e dar push:

```bash
git add -A
git commit -m "descrição do que mudou"
git push
```

O GitHub Pages republica sozinho em ~1 minuto. Não subir arquivo pela interface web do GitHub: foi
assim que a versão local e a publicada acabaram divergindo sem ninguém perceber.

Depois de mexer no `<head>`, vale limpar o cache de preview do WhatsApp/Facebook em
[developers.facebook.com/tools/debug](https://developers.facebook.com/tools/debug/) — senão o preview
antigo fica grudado por dias.

## Como o Claude processa os briefings automaticamente

O e-mail da empresa encaminha automaticamente uma cópia de cada briefing pro Gmail pessoal do Matheus
(Configurações do Gmail → Forwarding and POP/IMAP). O Claude lê essa cópia numa rotina automática,
atualiza `docs/06_CLIENTES.md` / `docs/07_PROJETOS.md` e só notifica o Matheus quando chega algo novo —
silencioso no resto do tempo.

## Editar o formulário depois

Todo o conteúdo (perguntas, categorias, textos) está em HTML/CSS/JS simples dentro de `index.html` —
qualquer ajuste pode ser pedido ao Claude, que edita o arquivo e publica com o comando acima.
