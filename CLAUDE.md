# CLAUDE.md — regras permanentes deste projeto

Estas são as regras que valem em toda sessão de trabalho neste repositório. Leia-as antes de
agir e siga-as sem exceção.

## Sobre commits (regra inviolável)

Você **nunca** executa `git commit` nem `git push` automaticamente. Depois de qualquer
alteração, você deixa as mudanças prontas para revisão, descreve em uma frase o que foi
alterado e propõe uma mensagem de commit para eu usar. A gravação no histórico é sempre uma
decisão minha, feita por mim. Eu sou o único portão humano do registro.

## Sobre o formato dos arquivos

Todo conteúdo é Markdown puro. Uma unidade de significado por arquivo — uma essência por
conceito, um argumento por arquivo. Nomes de arquivos e pastas em português, sem acentos, sem
espaços, com hífens (ex.: `mapa-do-sistema.md`, `conceitos/atencao.md`).

Todo arquivo de conhecimento começa com frontmatter YAML contendo, no mínimo: `tipo`,
`titulo`, `criado`, `atualizado`.

## Sobre a arquitetura (a regra de ligação)

O repositório tem três compartimentos:

- **`transcricoes/`** — a fonte bruta. Material neutro, datado, **nunca alterado depois de
  criado**.
- **`universo-2-conteudo/`** — o pensamento.
- **`universo-1-jornada/`** — a estratégia acadêmica.

No Universo 2, as camadas se ligam assim: Conceitos → Argumentos → Teses; Problemas-abertos
tensionam conceitos e argumentos; Sínteses empacotam teses para fora. Detalhe completo e
explicado em `mapa-do-sistema.md`.

Use links no formato Obsidian `[[nome-do-arquivo]]`.

## Fonte única de verdade

Cada informação tem um único dono — um único arquivo onde ela é definida por extenso. Nenhum
outro arquivo deve copiar essa informação; quando precisar referenciá-la, aponte para o dono
com um link, em vez de duplicar o conteúdo. O objetivo não é evitar toda repetição (links e
sínteses repetem referências de propósito, e isso é correto), mas evitar que a mesma
informação exista por extenso em dois lugares que precisariam ser atualizados juntos — porque
um será esquecido e os dois vão divergir.

Critério para decidir o dono quando uma informação serve a mais de um arquivo:

- O que o agente precisa **obedecer** mora no `CLAUDE.md`.
- O que eu preciso **entender** sobre a arquitetura mora no `mapa-do-sistema.md`.
- O que serve de **porta de entrada** mora no `README.md`.

Quando uma informação for de fronteira, escolha um dono e deixe os outros apontarem para ele.

## Sobre como trabalhamos

O ponto de entrada de cada sessão é `universo-1-jornada/painel-de-controle.md` — leia-o
primeiro para saber onde paramos.

Ao processar uma transcrição nova, primeiro **discutimos e concordamos** sobre o que é novo,
o que conflita e o que refina; só depois você altera os arquivos. Nunca jogue fora o texto
bruto de uma transcrição.

## Sobre a postura

Prefira simples a engenhoso. Não crie pastas ou arquivos não solicitados. Quando algo na
estrutura não couber bem, aponte o atrito em vez de forçar — refinamos quando dói.
