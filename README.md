# Central Vanessa Cunha · Braper

Portal do cliente do projeto Vitrine Digital (Vanessa Cunha Cerâmica). Site estático: sem build e sem dependências. Basta publicar os arquivos como estão.

## Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | A Central completa: login, visão geral, entregas e materiais. **O nome precisa ser exatamente `index.html`.** |
| `materiais/kickoff.html` | Apresentação de Kick-off |
| `materiais/pre-briefing.html` | Formulário de pré-briefing de encomendas (envia as respostas pelo WhatsApp) |
| `materiais/guia-foto-video.html` | Guia Prático de Foto & Vídeo, versão responsiva |
| `materiais/guia-foto-video.pdf` | Guia Prático de Foto & Vídeo, versão em PDF para download |
| `materiais/img/guia/` | Fotos usadas no guia |
| `assets/logos/` | Logos da Vanessa Cunha em PNG (areia, preto, branco, off-white), em alta resolução |
| `assets/logo-vc-*.png` | Versões leves das logos, usadas nas páginas |

Os materiais abrem dentro da Central (visualizador interno) e também funcionam sozinhos, em nova aba.

## Publicar (GitHub → Vercel)

1. Crie o repositório e suba **todos os arquivos e pastas deste pacote** para a raiz (branch `main`), mantendo a estrutura de pastas.
2. Na Vercel, importe o repositório como projeto estático (framework: *Other*, sem build command, output = raiz).
3. Cada push na `main` publica automaticamente.

Para atualizar: substitua os arquivos alterados e faça o push. Nunca renomeie o `index.html` nem as pastas `materiais` e `assets`.

## Acesso

- Usuário: qualquer nome · Senha: `ceramica#2026#`
- A validação acontece no navegador. É um controle de acesso simples, não segurança forte: não publique aqui dados sensíveis.

## Formulário de pré-briefing

O link público do formulário, que vai no Linktree, é publicado à parte, em repositório próprio (pacote `formulario-pre-briefing`). A Central traz uma cópia em `materiais/pre-briefing.html` para abrir no visualizador interno.

Para a Central abrir o link público em vez da cópia, preencha no `index.html` a linha `const PREBRIEFING_URL='';` com o endereço publicado, por exemplo `const PREBRIEFING_URL='https://SEU-DOMINIO/';`.

As respostas são enviadas por WhatsApp para o número definido na linha `var WHATSAPP='5511976875699';` do formulário (DDI + DDD + número, só dígitos). Se trocar o número, troque nas duas cópias.

## Suporte

O botão de suporte da Central abre o WhatsApp da Braper: (11) 97303-0448.

## Atualizar o andamento das entregas

No `index.html`, a lista `const E=[ ... ]` tem uma linha por entrega. Em `etapas`, cada etapa termina em `1` (pronta) ou `0` (não pronta):

```js
etapas:[['Conta configurada',1],['Revisão da tela de checkout',0]]
```

Troque `0` por `1` quando a etapa ficar pronta. O status da entrega, o percentual do projeto, os indicadores e a área de Materiais se atualizam sozinhos. Quando todas as etapas de uma entrega estão em `1`, ela aparece como Pronto.

As marcações feitas na tela (círculos) valem só para a visita de quem marcou. Elas não alteram o arquivo.

## Liberar novos materiais

1. Suba o arquivo na pasta `materiais/`.
2. No `index.html`, em `const M=[ ... ]`, acrescente `href:'materiais/arquivo.html'` (e, se houver, `pdf:'materiais/arquivo.pdf'`) no material correspondente.
3. Marque as etapas da entrega como prontas, como descrito acima.
