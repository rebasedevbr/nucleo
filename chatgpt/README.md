# O Núcleo no ChatGPT (e no Claude.ai)

As skills em `../skills/` são pastas que o Claude Code lê sozinho. O ChatGPT não lê esse formato,
então aqui as 4 skills viraram **um texto de instruções** pra você colar num Projeto do ChatGPT. No
Claude.ai funciona igual, num Projeto com as mesmas instruções e os mesmos arquivos.

## Montar o Projeto (5 minutos)

1. No ChatGPT, crie um Projeto chamado "Meu Núcleo" (ou um GPT personalizado, se preferir).
2. Em instruções do projeto, cole o conteúdo inteiro de `instrucoes.md` (cabe no limite).
3. Em arquivos do projeto, suba estes 3, que estão nas skills:
   - `skills/nucleo-montar/references/guia-do-nucleo.md`
   - `skills/nucleo-montar/assets/template-nucleo.md`
   - `skills/nucleo-validar/references/exemplos-de-numeros.md`
4. Coloque os seus CVs, o PDF do LinkedIn e o que mais tiver numa pasta sua. Você vai anexar na
   conversa quando pedir pra extrair os Pendentes.

## Como usar

O ChatGPT não guarda o seu Núcleo entre conversas. O jeito que funciona:

- O Núcleo mora no seu Notion ou Google Doc. No começo de cada conversa, cole o documento (ou
  anexe o `.md`).
- Peça pelo modo: "quero montar meu núcleo", "extrai os pendentes desses CVs", "valida o P3",
  "compara essa vaga com meu núcleo".
- Ao fim de cada bloco ele devolve a seção alterada em markdown, e diz qual seção substituir no seu
  documento. Você cola. Nada entra sem você ver.

As regras são as mesmas das skills: uma pergunta por vez, as suas palavras, "não sei" é resposta
válida, número só quando você sustenta, nome de cliente e número de receita ficam de fora.
