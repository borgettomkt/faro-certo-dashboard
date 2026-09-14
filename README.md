# Relatório Faro Certo Imóveis

Dashboard estático de performance de Meta Ads para o cliente **Faro Certo Imóveis**, produzido pela BGT.

- Site estático puro (HTML + CSS + JS, Chart.js via CDN) — sem build step.
- Publicado via **Cloudflare Pages**, conectado a este repositório.
- Domínio: `farocerto.borgetto.com.br`

## Estrutura

- `index.html` — dashboard completo (dados, estilos e lógica embutidos no próprio arquivo).
- `videos/` — vídeos de criativos em veiculação referenciados por URL relativa (evita embutir base64 de arquivos grandes).

## Manutenção mensal

1. Prints do Gerenciador de Anúncios da Meta são repassados para extração dos números.
2. O array `ENTRIES` (dentro do `<script>` de `index.html`) recebe uma nova entrada por `monthKey` (`AAAA-MM`).
3. Novos criativos em veiculação são adicionados a `CREATIVES_TOPO` / `CREATIVES_FUNDO`. Vídeos grandes vão para `videos/` e são referenciados por URL, não em base64.
4. Cada atualização é commitada e enviada (`git push`) para publicação automática no Cloudflare Pages.
