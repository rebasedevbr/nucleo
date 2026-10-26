---
name: nucleo-vaga
description: Compara a descrição de uma vaga com o Núcleo inteiro da pessoa (mentoria Rebase) e diz, requisito por requisito, o que está no Confirmado, o que está só nos Pendentes e o que é lacuna real; aponta os 3 a 5 itens pro topo do CV e quais Pendentes validar nesta semana. Também rascunha respostas de formulário de candidatura usando só o Confirmado. Use sempre que a pessoa colar ou linkar uma vaga (LinkedIn, Rebase Jobs, site da empresa) e disser "compara com meu núcleo", "eu sirvo pra essa vaga", "o que eu tenho pra essa vaga", "me ajuda com o formulário dessa aplicação", "o que falta pra essa vaga", "quais itens eu uso no CV pra essa vaga", ou chamar /nucleo-vaga. Não escreve o CV completo nem inventa experiência.
---

# /nucleo-vaga · a vaga contra o Núcleo

Uma IA que só tem o CV acha que a pessoa não sabe uma tecnologia que ela sabe, porque o CV é um
recorte. O Núcleo é tudo que ela já fez. Esta skill compara a vaga com o Núcleo inteiro e devolve um
mapa honesto: o que ela prova, o que ainda precisa validar, o que falta mesmo.

Regra de ouro: **só o Confirmado é evidência**, e o "Quem sou" conta como Confirmado (stack, inglês,
fuso, contrato, pretensão, anos). Item dos Pendentes vira pergunta pra pessoa, nunca afirmação. Lacuna
não se cobre com experiência "parecida". Nada do Núcleo é reescrito.

Item do Confirmado é C1, C2, C3; item dos Pendentes é P1, P2, P3. Cite sempre com o prefixo: "o 4"
existe nas duas listas, e citar o errado numa candidatura é o erro que o Núcleo existe pra evitar.

## Entrada

- A vaga: texto colado, ou link. Se for link e você consegue abrir, leia a página inteira (requisitos,
  responsabilidades, fuso, modelo de contrato, faixa salarial se houver, perguntas do formulário).
  Se não consegue, peça pra colar o texto.
- O Núcleo: `nucleo.md` na pasta atual (ou o documento que ela indicar). Leia inteiro, incluindo
  "Quem sou", "Lacunas que eu assumo" e "O que eu não digo".

## Passos

1. **Requisitos com as palavras do anúncio.** Três tipos: obrigatório, desejável e responsabilidade
   (o "what you will do" filtra tanto quanto o "must have"). Inclua os implícitos (fuso, país,
   modelo de contrato, nível de inglês, senioridade).
2. **Pra cada requisito, onde ele está no Núcleo:**
   - no **Confirmado**: cite o item (C1, C2) e a empresa; anos de experiência se provam pela linha
     do tempo ou pelos períodos das empresas; stack, inglês, fuso e contrato, pelo "Quem sou";
   - **Confirmado, em parte**: o fato existe, mas sem o número que o anúncio pede ("Postgres at
     scale" com Postgres em produção e nenhum volume). Cite o item e aponte o Pendente ou a pergunta
     que fecharia;
   - só nos **Pendentes**: cite o item e diga o que falta validar;
   - em **lugar nenhum**.
3. **Lacunas reais**: requisitos sem nada no Núcleo. Se já está em "Lacunas que eu assumo", diga que
   a resposta de entrevista já existe. Não estique experiência vizinha pra cobrir.
4. **Fit com "Quem sou"**: confira fuso (convertendo com horário de verão, se houver), contrato,
   pretensão (diga a interseção entre a faixa dela e a da vaga) e "o que me faz descartar". Se bate
   num critério de descarte, diga antes de qualquer outra coisa.
5. **Topo do CV**: os 3 a 5 itens do Confirmado que essa vaga mais valoriza, na ordem. Só isso: o CV
   em si é assunto das próximas aulas.
6. **O que validar nesta semana**: os Pendentes que a vaga toca, em ordem de risco. É assim que os
   Pendentes andam, puxados pela vaga da vez. Ofereça rodar `/nucleo-validar` neles agora.
7. **Fato novo**: se a pessoa disser "eu tenho isso, só não está no Núcleo" (o caso clássico: anos de
   uma linguagem num projeto que o CV nunca mencionou), isso não entra na comparação como evidência
   ainda. Vai pelo caminho da `nucleo-validar` e sobe pro Confirmado com data; depois a comparação
   se refaz.

## Formulário de candidatura (quando ela pedir)

Formulário longo depois de uma tarde adaptando CV é onde muita candidatura morre. Com o Núcleo dá pra
rascunhar rápido:
- responda cada pergunta do formulário usando **só itens do Confirmado**, citando o número do item
  usado (C1, C2);
- em "eu", com as palavras dela, no idioma do formulário;
- pergunta que só tem resposta num Pendente: deixe a resposta em branco e escreva "valide o P<n> antes";
- pergunta sobre algo que está em "Lacunas que eu assumo": responda com a lacuna, sem enfeitar;
- pergunta de motivação ("why us?"): não tem item que responda sozinho. Use o que o anúncio e o
  Núcleo têm em comum (os itens do topo do CV e "o que eu valorizo") e deixe claro que o motivo
  pessoal ela completa. Não invente pesquisa sobre a empresa;
- marque o conjunto como **rascunho, revisar antes de enviar**. Quem envia é a pessoa.

## Saída

```
## <empresa> · <cargo>
Fit com "Quem sou": <bate / atenção: ...>

| requisito (palavras do anúncio) | tipo | no Núcleo | item |
|---|---|---|---|
| ... | obrigatório | Confirmado | C2 Contafy |
| ... | obrigatório | Pendente | P3: fui eu ou o time? |
| ... | responsabilidade | Confirmado, em parte | C6 Contafy; falta o volume (ver P7) |
| ... | desejável | lacuna | já assumida em Lacunas |

Topo do CV pra esta vaga:
- C2: <por quê, uma frase>
- C6: ...

Validar nesta semana (ordem de risco):
- P3 (risco 1): <o que a vaga toca e o que falta>
- P1 (risco 1): ...

Lacunas reais:
- <requisito>: <já assumida em Lacunas / nova: existe fato pra validar?>
```

Fale em português do Brasil, direto, sem promessa de resultado (se a pessoa escrever em inglês,
responda em inglês; o Núcleo continua em português). Não diga "você tem grandes chances"
nem "a vaga é perfeita": diga o que bate, o que falta e o que fazer.

## Exemplo curto

Vaga: "Senior Backend Engineer · Python ou Go · sistemas distribuídos · experiência com automação de
testes · fuso até UTC-3".

Núcleo do Rafael (exemplo fictício do guia): Java, Kafka, Postgres, AWS no Confirmado; nada de Python
ou Go em lugar nenhum; "Kubernetes" nos Pendentes; UTC-3 em "Quem sou".

Saída: fuso bate; Python ou Go é lacuna real (dizer, não contornar com "linguagens parecidas");
sistemas distribuídos tem evidência no C3 (Kafka em produção por 2 anos) e no C6 (migração com dupla
escrita); automação de testes não aparece no Núcleo: perguntar se existe fato pra validar; topo do CV:
C3, C6, C2. Validar nesta semana: nenhum Pendente tocado pela vaga além do Kubernetes (P6), que só
importa se o anúncio citar.
