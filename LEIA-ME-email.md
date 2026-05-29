# ONESecure — E-mail marketing para Outlook

Esta pasta contém a versão do e-mail pronta para envio, compatível com Outlook
(desktop Windows, Outlook web e Mac), Gmail, Apple Mail e a maioria dos clientes.

## Arquivos

- `email.html` ............... versão de PRÉ-VISUALIZAÇÃO (caminhos relativos). Abra no
                               navegador para conferir. NÃO use para envio.
- `email-para-envio.html` .... versão de ENVIO (imagens com URL absoluta). É esta que
                               você cola na ferramenta de e-mail.
- `email-assets/` ............ todas as imagens usadas no e-mail (hero, CTA, ONEScore,
                               ícones, logo). Precisam ficar hospedadas em uma URL pública.
- `index.html` ............... versão web (página), caso queira hospedar o e-mail como link.

## Como publicar as imagens na Vercel

1. Faça o deploy desta pasta inteira na Vercel (arraste a pasta em vercel.com/new,
   ou rode `vercel` dentro dela).
2. A Vercel te dá uma URL, por exemplo: `https://meu-projeto.vercel.app`
3. As imagens ficarão acessíveis em:
   `https://meu-projeto.vercel.app/email-assets/hero.png` (etc.)

## Como preparar o HTML para envio

1. Abra `email-para-envio.html` em um editor de texto.
2. Substitua TODAS as ocorrências de:
       https://SEU-PROJETO.vercel.app
   pela sua URL real da Vercel, por exemplo:
       https://meu-projeto.vercel.app
   (são 12 ocorrências — use "Substituir tudo".)
3. Troque o link do botão: procure por `href="#"` e coloque a URL real de agendamento.
4. Substitua `[Nome]` pela tag de personalização da sua ferramenta (ex.: {{first_name}}).

## Como enviar

- **Outlook / Exchange / ferramentas de e-mail marketing (RD Station, Mailchimp,
  HubSpot etc.):** cole o conteúdo de `email-para-envio.html` no editor de código/HTML
  da ferramenta. NÃO copie e cole o e-mail "renderizado" — use o modo HTML.
- As imagens NÃO ficam embutidas no e-mail (e-mail não suporta isso de forma confiável);
  elas são carregadas das URLs da Vercel. Por isso a pasta precisa continuar publicada.

## Observações de design (compatibilidade Outlook)

- Hero, "Apresentamos", ONEScore e o bloco final foram exportados como imagens, pois usam
  efeitos (halftone, gradientes, sombras) que o Outlook desktop não renderiza em CSS.
- O texto das demais seções é "vivo" (selecionável, bom para entrega e acessibilidade).
- A fonte Lexend é aplicada onde o cliente suportar; no Outlook desktop cai para Arial,
  mantendo a hierarquia.
- Paleta azul institucional preservada conforme o design system.
