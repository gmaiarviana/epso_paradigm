# CLAUDE.md — regras permanentes deste projeto

Estas são as regras que valem em toda sessão de trabalho neste repositório. Leia-as antes de
agir e siga-as sem exceção.

## Sobre o terminal (regra fixa)

Eu **sempre** uso PowerShell no Windows. **Nunca** uso bash, Git Bash ou sintaxe POSIX. Todos
os comandos que você me entregar para copiar e colar devem ser PowerShell válido — caminhos
com `\`, variáveis com `$`, sem `&&`/`||` para encadear (use `;` ou `if ($?) { ... }`), sem
`rm -rf`/`ls`/`cat`/`find` (use os equivalentes ou as ferramentas próprias). Para mensagens de
commit multilinha, use here-string de aspas simples (`@'` … `'@`, com o `'@` na coluna 0).

## Sobre commits (regra inviolável)

Você **nunca** executa `git commit` nem `git push` automaticamente. Depois de qualquer
alteração, você deixa as mudanças prontas para revisão, descreve em uma frase o que foi
alterado e propõe uma mensagem de commit para eu usar. A gravação no histórico é sempre uma
decisão minha, feita por mim. Eu sou o único portão humano do registro.

Ao propor o commit, entregue dentro de um bloco de código, pronto para eu copiar e colar, os
comandos completos **em PowerShell** (ver regra do terminal acima): um `git add` para **cada
arquivo específico** que mudou (nunca `git add .`, para termos precisão sobre o que entra no
commit) seguido do `git commit -m`. Ex.:

```powershell
git add transcricoes/2026-06-26-a-tese-mudanca-de-paradigma.md
git commit -m "transcricoes: adiciona transcricao bruta de 2026-06-26"
```

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

Antes de classificar material novo como redundante, superado ou conflitante com o que já
existe, **leia por extenso os arquivos-donos** envolvidos e cite-os. Nunca infira obsolescência
ou conflito a partir de título, resumo ou forma de apresentação — só a partir da substância.
Quando a relação não estiver clara depois de ler, traga como **pergunta, não como veredito**.

## Sobre a postura

Prefira simples a engenhoso. Não crie pastas ou arquivos não solicitados. Quando algo na
estrutura não couber bem, aponte o atrito em vez de forçar — refinamos quando dói.

Este é um pensamento **em elaboração**, não um resultado fechado. Ao escrever, preserve a
provisoriedade: registre ideias como candidatas, hipóteses e pontos de entrada — nunca como o
que a pesquisa "é". Distinga sempre o que já está assentado do que ainda está em aberto, e nunca
feche por escrito uma decisão que está aberta de propósito (ex.: o recorte em
`foco-academico.md`). Na dúvida sobre o grau de certeza, escreva no tom mais aberto.

Nem todo material de origem merece registro. Só sobe para o repositório o que for **durável e
faz trabalho** — o que sustenta uma decisão ou ação futura. Pontuações subjetivas, fotos do
momento, listas genéricas e o que apenas repete conteúdo que já vive em outro arquivo ficam de
fora. Na dúvida, não registre: é mais fácil acrescentar depois do que limpar redundância.
