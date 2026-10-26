# Exemplos de como um fato virou número

Casos da aula do Núcleo da Rebase (2026-10-22). Os que vieram de alguém da turma estão generalizados:
ficou a pergunta que destravou, não a história da pessoa. Servem pra abrir o repertório: cada exemplo
é um tipo de pergunta que você pode fazer.

## 1. Plantão sem número (exemplo fictício do guia)

Bullet: "Participei do plantão e ajudei a melhorar a estabilidade."
Perguntas: o que você fazia no plantão → "a gente ou você?" → quantos → o que acontecia antes → e
depois → quanto tempo levou.
Resultado: "Escrevi 15 runbooks em 3 meses pros alertas mais frequentes; os pages noturnos caíram de
cerca de 10 pra 2 por semana." Como eu sei: histórico do PagerDuty. O rodízio era do time; os
runbooks foram dela.

## 2. "Fiz errado e corrigi": a ferramenta que substituiu um fornecedor (caso da aula, generalizado)

A pessoa construiu uma ferramenta interna de ponta a ponta e dizia não ter métrica porque "as melhorias
foram do meu próprio trabalho, fiz errado e corrigi".

A primeira pergunta do Fred: **como era antes?** A empresa dependia de um fornecedor externo que deixou
de atender, e tinha cliente pagante esperando. Daí saíram vários números possíveis, sem inventar nenhum
(os valores abaixo são ilustrativos):
- custo de ferramenta antes (o que se pagava ao fornecedor) e depois (o que o serviço próprio custa
  pra rodar), contado como proporção se o valor for sensível;
- o cliente que estava em risco e foi mantido (receita retida, também como proporção ou "um cliente
  que respondia por X% da receita");
- tempo de execução da primeira versão em produção e da versão atual ("cerca de 40 min → 15 min");
- frequência de atualização ("rodava algumas vezes ao dia → a cada meia hora");
- estabilidade: falhas por 10 execuções antes e depois ("4 em 10 → 1 em 10").

A lição: "fiz errado e corrigi" é uma versão em produção que funcionava e depois melhorou. O antes é a
primeira versão. Só não dá pra contar se nunca foi pro ar.

## 3. Número de segurança sem expor a empresa (caso da aula, generalizado)

A pessoa revisava PRs em busca de problemas de segurança e auditava código existente; uma auditoria
achou dezenas de problemas em produção. Receio: dizer o número expõe a empresa.

Saídas do Fred:
- proporção em vez de valor absoluto: "reduzi em cerca de 60% as vulnerabilidades em produção" em vez
  do número exato;
- medir antes da produção: "a cada 20 PRs, 2 traziam problema de segurança; depois da checagem,
  nenhum";
- se existe um incidente público da empresa, ele pode ser âncora ("depois do processo, nunca mais houve
  caso como o de tal ano"). Nunca o tipo de vulnerabilidade: isso não se conta.

## 4. Migração que foi decisão, não execução (Núcleo do Fred)

Migração de cloud de AWS pra OVH. O número (65% de redução de custo) era projeção; depois que ele saiu
da empresa, confirmou com o CTO que ficou e virou Confirmado. "O que foi meu": a decisão e o business
case, alocar o time. Não foi ele que migrou serviço nenhum. "Como eu sei": o corte aconteceu, conferido
com o CTO.

## 5. Build 60% mais rápido que a IA atribuiu a ele (Núcleo do Fred)

A IA escreveu num CV que ele implementou SWC e a melhoria de build na migração do framework. Foi o time
de open source. A parte dele: roadmap, prioridades, pedir a medição de antes e depois. É assim que entra
("the team shipped, under my leadership"), e é um item que só existe porque ele mediu.

## 6. Contratações aproximadas (Núcleo do Fred)

"Reconstruí o time do zero; ninguém da formação de entrada ficou. Foram 10 a 12 contratados diretos no
pico, 16 contando parceiros." Ele não lembra se 10 ou 12. Ninguém audita. O que ele sustenta: recrutou
os líderes, conferiu quem entrou e quem saiu.

## 7. Migração de front com número pequeno que faz diferença (exemplo fictício da aula)

"Escrevi o plano de migração do painel de Create React App pra Next.js, cerca de 40 telas no escopo;
migrei 12." E: "o carregamento caiu de cerca de 8 s pra 3 s; a minha parte foi propor a medição e montar
o dashboard de web vitals antes de começar." Também: "criei a biblioteca de componentes, 46 componentes
usados por 3 produtos, sozinho nos primeiros 8 meses"; "rodízio de on-call 1 semana a cada 5 por 18
meses"; "mentor de 2 devs júnior com 1:1 quinzenal por 1 ano". Nenhum é grande. Todos têm número.

## 8. Quando você não mediu: dá pra voltar

O Fred migrou um sistema e sentiu que ficou mais rápido, mas não tinha medido. Fez deploy da versão
anterior de novo, deixou as duas rodando e mediu. Histórico do repositório permite reconstruir o antes.

## 9. Número de testes: bom ou ruim?

Depende do contexto. Mais testes pode ser cobertura; menos testes pode ser deploy mais rápido. A
pergunta certa é o que mudou pra quem: tempo de pipeline, regressões em produção, cobertura. E se o
formulário da vaga pergunta de automação de teste, é porque pra aquela empresa isso pesa.

## Perguntas que mais destravaram

- Como era feito antes de você? (manual, fornecedor, não existia)
- Quanto custava, quanto demorava, quantas vezes falhava, com que frequência rodava?
- Quem sentiu a diferença e o que aconteceria se não tivesse sido feito?
- Você tocou, desenhou, decidiu, priorizou, revisou ou pediu a medição?
- Dá pra reconstruir o antes (histórico do repositório, deploy da versão antiga, dashboard, ticket)?
- Isso é público? Se não, qual proporção ou contagem conta a mesma história?
