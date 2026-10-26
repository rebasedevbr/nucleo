---
name: nucleo-pendentes
description: Lê CVs antigos, LinkedIn, formulários e textos escritos com IA sobre a carreira da pessoa, extrai cada afirmação factual, marca conflito, só numa fonte, número absoluto e advérbio, e joga tudo na parte Pendentes do Núcleo (mentoria Rebase), sem decidir o que é verdade. Use sempre que a pessoa mandar ou apontar CVs, PDF do LinkedIn, textos de candidatura, ou disser "extrai as afirmações dos meus currículos", "joga meus CVs no núcleo", "compara meus currículos", "o que meus CVs dizem de diferente", "monta os pendentes", ou chamar /nucleo-pendentes. Use também quando a nucleo-montar chegar no passo das fontes. Não serve pra reescrever ou melhorar CV.
---

# /nucleo-pendentes · das fontes pros Pendentes

Trabalho mecânico: ler tudo que a pessoa já escreveu sobre a própria carreira, tirar a afirmação por
trás de cada frase e marcar onde as fontes discordam. Quanto mais fontes, mais conflito aparece, e
conflito é exatamente o que se quer achar agora, em casa, e não na entrevista.

Você não decide o que é verdade. Tudo que sai daqui vai pros Pendentes, mesmo o que parece certo. A
pessoa valida depois, item a item, com a skill `nucleo-validar`. Por isso: não reescreva, não
melhore, não resuma, não sugira frase nova, não arredonde número, não complete o que falta.

## Entrada

- Arquivos (PDF, MD, TXT, export do LinkedIn) ou texto colado. Leia cada um inteiro. Formato que você
  não consegue ler (DOCX costuma falhar): peça pra ela exportar em PDF ou colar o texto. Nunca
  adivinhe o conteúdo de um arquivo que não abriu.
- Cada fonte recebe um nome curto ("CV Empresa X 03/2026", "CV genérico v2", "LinkedIn", "resumo IA
  08/2026"). Se a pessoa não deu nome, proponha um a partir do arquivo e siga; ela corrige se quiser.
- Telefone, endereço e email: ignore. Não fazem falta e não vão pro Núcleo. Cidade não é endereço:
  entra, porque alimenta o "Quem sou" (cidade e fuso).
- Fontes em idiomas diferentes: escreva a afirmação em português e mantenha a palavra original entre
  aspas quando ela for o que está em jogo ("led" / "liderei", "garantimos"). Se a pessoa escrever
  em inglês, responda em inglês; a tabela continua em português.
- Pergunte, antes de começar, só isto: "algum desses CVs já foi enviado pra uma vaga, e tem processo
  aberto?" A resposta define o risco.

Se não existir `nucleo.md` na pasta, pergunte se ela quer criar agora (a skill `nucleo-montar` faz a
montagem inteira) ou se prefere só receber a tabela pra colar no Notion ou Google Doc.

## Extração

1. **Uma afirmação por linha, a mais curta possível.** "Atuei na liderança técnica de um squad
   multidisciplinar de alta performance com 8 pessoas" vira "liderou time de 8". Mantenha o número
   exatamente como está na fonte. Mantenha a palavra que a fonte usou ("liderou", "participou",
   "arquitetou"): a palavra é parte do que vai ser validado.
2. **Separe o que vem junto.** Uma frase com 3 fatos vira 3 linhas.
3. **Agrupe o mesmo fato entre fontes** e liste em quais aparece. Datas e cargos de cada empresa
   também são fatos: CV que diz "jan/2014 no Rio" e outro que diz "até ago/2014 em Goiânia" é
   conflito de linha do tempo e entra na tabela.
4. **Marque** cada afirmação com uma ou mais marcas:
   - **conflito**: as fontes dizem coisas diferentes sobre o mesmo fato (mostre as versões lado a
     lado: "time de 4 / 8 / 12");
   - **só numa fonte**: apareceu uma vez e nunca mais (o maior risco de ter sido inflada);
   - **número absoluto**: receita, custo, salário, preço de cliente em valor absoluto;
   - **advérbio**: resultado sem número ("significativamente", "melhorias de performance",
     "reduzindo muito").
   Afirmação que bate em todas as fontes e não tem número absoluto nem advérbio fica com a marca
   **bate**. Ela continua Pendente: bater entre cópias não prova nada.
   Fonte escrita ou revisada por IA conta como fonte normal, mas anote "(IA)" no nome.
   A mesma frase pode ter conflito em dois eixos (time de 6 ou 12; "squad de conciliação" ou
   "plataforma de pagamentos"): são duas linhas.
   Lista de skills: uma linha por tecnologia que só aparece numa fonte ou gera dúvida; as que batem em
   todas as fontes podem ficar numa linha só, com a pergunta "quais dessas eu sustento numa entrevista".
5. **Risco**: 1 se está em CV já enviado ou processo aberto; 2 se repete em muitas fontes (repetição
   costuma ser cópia, não prova); 3 o resto. O 1 prevalece sobre o 2. LinkedIn público conta como
   enviado quando há processo aberto: o recrutador leu.
6. **"O que falta", como pergunta**, uma por linha: "foram 6 ou 12?", "de onde veio o 70%, qual
   endpoint, qual percentil?", "fui eu ou o time de plataforma?", "quanto, comparado com o quê?".
   Quando der, aponte onde achar: ex-colega, dashboard, PR, ticket, CV mais antigo.
7. **Ordene**: conflito e só numa fonte primeiro, depois por risco, depois pelas que mais se repetem.

Se não der pra saber algo, escreva "não sei". Não preencha lacuna por dedução.

## Saída

Tabela no formato da Parte 2 do Núcleo:

| # | afirmação | fonte | marca | risco | o que falta |

Numere P1, P2, P3 (o Confirmado usa C1, C2, C3; o prefixo evita citar o item errado numa candidatura).

- Se há `nucleo.md`: acrescente as linhas na Parte 2 (as linhas vazias do template são modelo:
  substitua; se já há itens, continue a numeração P), registre cada fonte na Parte 3 (Referências) com
  nome curto, link ou caminho, se foi enviada e pra onde (ou "nunca enviado") e a data de hoje, e
  atualize o "Atualizado em". Nada entra na Parte 1.
- Devolva no chat o total de itens, quantos conflitos e quantos "só numa fonte", e as 3 ou 4 linhas
  que ela deve conferir contra o original agora (as de risco 1). Diga, em uma frase, que a IA às
  vezes troca número ou junta 2 fatos num item, e que a conferência é dela.
- Fatos que a pessoa já sabe que são verdade e sustenta: ela escreve de novo, com as palavras dela,
  via `nucleo-validar`. Não é você que sobe.

## Exemplo

Fonte "CV v1": "Led a team of 6 engineers in the payments platform."
Fonte "CV v3": "Liderei 12 engenheiros na plataforma de pagamentos."
Fonte "LinkedIn": "Tech Lead · time de 12."

| # | afirmação | fonte | marca | risco | o que falta |
|---|---|---|---|---|---|
| P1 | liderou time de 6 / 12 / 12 na plataforma de pagamentos | CV v1, CV v3, LinkedIn | conflito | 1 (CV v3 enviado, processo aberto) | Foram 6 ou 12? Os 12 foram só durante o projeto de antifraude? Por quanto tempo cada número? |
