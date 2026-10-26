# Skills do Núcleo · Rebase

Quatro skills pra montar e manter o seu Núcleo com a IA te entrevistando, em vez de escrevendo por
você. Elas seguem o Guia do Núcleo e o que o Fred mostrou na aula: uma pergunta por vez, as suas
palavras, número só quando você sustenta, e quem decide o que é verdade é você.

| skill | quando usar | o que faz |
|---|---|---|
| `/nucleo-montar` | primeira vez, ou pra retomar | entrevista completa: quem sou, fontes, confirmado da memória, pendentes por risco, checklist |
| `/nucleo-pendentes` | você tem CVs antigos, LinkedIn, formulários | extrai cada afirmação, marca conflito, só numa fonte, número absoluto e advérbio, joga nos Pendentes |
| `/nucleo-validar` | todo dia, um item por vez | hot seat: as perguntas que puxam o número, "foi você ou a gente", e o item sobe, é corrigido ou sai |
| `/nucleo-vaga` | apareceu uma vaga | compara a vaga com o Núcleo inteiro, diz o que bate, o que validar nesta semana, e rascunha o formulário só com o Confirmado |

## Instalar

As skills são pastas com um `SKILL.md`. Funcionam no Claude Code e em qualquer agente que leia
esse formato.

1. Clone o repositório (é público, não precisa de convite):

   ```bash
   git clone https://github.com/rebasedevbr/nucleo.git
   ```

2. Crie uma pasta pro seu Núcleo, por exemplo `~/meu-nucleo/`, e coloque os seus CVs, o PDF do
   LinkedIn e o que mais tiver numa subpasta `fontes/`.
3. Copie as 4 pastas de `skills/` pra `~/meu-nucleo/.claude/skills/` (só nesse projeto) ou pra
   `~/.claude/skills/` (em qualquer pasta):

   ```bash
   mkdir -p ~/meu-nucleo/.claude/skills
   cp -R nucleo/skills/* ~/meu-nucleo/.claude/skills/
   ```

4. Abra o Claude Code dentro de `~/meu-nucleo/` e chame `/nucleo-montar`.

O Núcleo fica em `~/meu-nucleo/nucleo.md`. Quando for entregar, cole o conteúdo no Notion ou num
Google Doc e mande o link por DM pro Fred e pro Gabs. No canal da turma não: é coisa pessoal sua.

**Privacidade.** O `nucleo.md` guarda a sua pretensão salarial, a sua carreira inteira e, nas fontes,
os seus CVs. Essa pasta nunca vira repositório público: se quiser versionar, repositório privado, e
nada de subir junto com código de trabalho. Se preferir trabalhar dentro do clone deste repositório,
o `.gitignore` dele já ignora `nucleo.md` e `fontes/`.

**Usa ChatGPT, ou o Claude no navegador?** A pasta `chatgpt/` tem as mesmas 4 skills num texto só de
instruções pra um Projeto, e o passo a passo pra montar. O seu documento no Notion ou Google Doc
faz o papel do `nucleo.md`.

## Como usar bem

- Responda por voz se preferir (o Fred usa o Whisper). A skill ouve tudo e devolve a lista de itens
  pra você confirmar antes de escrever.
- "Não sei" é resposta válida. Vira pergunta nos Pendentes, com a pista de onde achar.
- Feche os CVs na hora de escrever o Confirmado. A skill vai pedir. É de propósito: copiar traz o
  exagero junto.
- Número aproximado com "cerca de" vale, desde que você saiba contar a história por trás.
- Receita, custo e preço de cliente em valor absoluto não entram. Nome de colega e de cliente também
  não. A skill troca por proporção, contagem ou descrição e anota em "O que eu não digo".
- Quebre em 2 sessões se cansar. A skill salva a cada bloco.

## O mínimo pra conversa individual com o Fred

"Quem sou" com pretensão em faixa e moeda; 5 itens no Confirmado das 2 experiências mais recentes,
com data; 10 itens nos Pendentes com fonte e marca; todos os CVs listados nas Referências. Mais
Pendentes que Confirmado na primeira semana é o esperado.

## Dentro desta pasta

- `chatgpt/` · instruções e passo a passo pra usar no ChatGPT ou num Projeto do Claude.ai

- `skills/nucleo-montar/` · a entrevista completa, o template (`assets/template-nucleo.md`) e a cópia
  do Guia do Núcleo com os acréscimos da aula (`references/guia-do-nucleo.md`)
- `skills/nucleo-pendentes/`
- `skills/nucleo-validar/` · com `references/exemplos-de-numeros.md`, os casos da aula
- `skills/nucleo-vaga/`
