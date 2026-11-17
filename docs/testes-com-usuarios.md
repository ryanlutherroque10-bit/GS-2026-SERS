# Testes com usuários

> **Situação em 16/11/2026: nenhum teste com pessoas foi realizado.** Este arquivo traz o roteiro e o formulário. As tabelas de resultados estão em branco de propósito e só devem ser preenchidas com o que acontecer de verdade. Testes automatizados e respostas simuladas não substituem participantes reais.

O enunciado pede que a equipe verifique a compreensão e a utilidade das orientações, registrando as situações testadas, os comentários recebidos e os ajustes realizados, sem expor dados pessoais desnecessários. Ele não fixa a quantidade de participantes; sugerimos de 3 a 5 pessoas do público (adultos responsáveis pela conta de luz, de preferência com perfis diferentes: casa própria e alugada, com e sem Tarifa Social).

## Cuidados

- Explique que é um trabalho acadêmico e que a participação é voluntária.
- Não anote nome, CPF, endereço nem número da instalação. Identifique cada pessoa como P1, P2, P3…
- Se a pessoa não souber um número (potência, tarifa), deixe usar o valor sugerido e anote isso.
- Não ajude na interpretação antes de a pessoa responder às perguntas de compreensão.

## Roteiro (cerca de 10 minutos por pessoa)

1. Abra o assistente: `python -m energia.assistente`.
2. **Situação 1 — a casa da pessoa.** Peça que responda com os dados da própria casa.
3. Sem explicar o resultado, faça as perguntas de compreensão:
   - C1. "Quanto o banho gasta por mês na sua casa, segundo o assistente?"
   - C2. "Qual das opções o assistente recomendou fazer primeiro? Por quê?"
   - C3. "O assistente garante que você vai economizar esse valor?" (resposta esperada: não, é estimativa)
   - C4. "Antes de comprar um aquecedor solar, o que o assistente diz para fazer?" (esperado: pedir orçamentos, confirmar com o instalador, ver se pode instalar)
4. **Situação 2 — caso proposto.** Peça que simule: casa alugada, família com Tarifa Social, 2 banhos por dia. Pergunte: "O aquecedor solar vale a pena nesse caso? O que o assistente respondeu?"
5. Perguntas de utilidade e clareza (nota de 1 a 5):
   - U1. As perguntas do assistente foram fáceis de responder?
   - U2. O resultado foi fácil de entender?
   - U3. Você mudaria algo em casa depois de ver esse resultado? O quê?
   - U4. Que palavra, número ou parte da tabela ficou confusa?
   - U5. O que faltou?

## Registro dos testes

Data(s): ____ · Local/forma (presencial ou remota): ____ · Quem aplicou: ____

| Participante | Perfil (sem dados pessoais) | Situação testada | C1 | C2 | C3 | C4 | U1 | U2 | Comentários (U3 a U5) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| P1 | | | | | | | | | |
| P2 | | | | | | | | | |
| P3 | | | | | | | | | |
| P4 | | | | | | | | | |
| P5 | | | | | | | | | |

Para C1 a C4, anote "acertou", "acertou com ajuda" ou "não entendeu".

## Ajustes realizados depois dos testes

| Problema observado | Quem relatou | Ajuste feito | Arquivo e commit |
| --- | --- | --- | --- |
| | | | |

## Resumo (preencher depois dos testes)

- Participantes: ____
- O que foi bem compreendido: ____
- O que precisou de ajuste: ____
- O que ficou sem resolver: ____

## Pontos que já esperamos observar

Hipóteses da equipe para prestar atenção durante os testes (não são resultados):

- a tabela com sete colunas pode ser larga demais para ler no terminal;
- "fração solar" e "kWh" podem precisar de explicação mais simples;
- a diferença entre "economia por ano" e "retorno" pode confundir;
- quem tem Tarifa Social pode estranhar a economia igual a zero.
