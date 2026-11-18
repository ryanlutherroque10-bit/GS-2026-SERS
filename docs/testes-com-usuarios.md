# Testes com usuários

> **Testes realizados em 17/11/2026:** Ryan Luther informou que aplicou remotamente os testes com P1 a P5. As respostas foram recebidas para registro em 18/11/2026.

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

Data: 17/11/2026 · Forma: remota · Quem aplicou: Ryan Luther

| Participante | Perfil (sem dados pessoais) | Situação testada | C1 | C2 | C3 | C4 | U1 | U2 | Comentários (U3 a U5) |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| P1 | Casa com 3 moradores | Casa informada e caso proposto de aluguel com Tarifa Social | 74,25 kWh/mês; cerca de R$ 70,54 | Banhos de 9 para 5 minutos, sem custo | Entendeu que é estimativa | Dois orçamentos e avaliação profissional | 4 | 4 | Usaria cronômetro; “retorno” confundiu; pediu destaque para o gasto mensal. No caso alugado, entendeu que precisa de autorização. |
| P2 | Casa com 4 moradores | Casa informada e caso proposto de aluguel com Tarifa Social | 61,6 kWh/mês; cerca de R$ 55,44 | Banhos de 5 minutos, sem compra | Entendeu que não há garantia | Autorização do proprietário e orçamentos | 3 | 3 | Conversaria com moradores; não entendeu “kWh”; pediu ajuda para localizar os dados na conta. Precisou reler a tabela. |
| P3 | Casa com 5 moradores | Casa informada e caso proposto de aluguel com Tarifa Social | Cerca de 110 kWh/mês; R$ 107,80 | Reduzir o tempo dos banhos | Entendeu que depende do uso real | Avaliar telhado, tamanho e orçamentos | 5 | 4 | Combinaria banhos mais curtos; confundiu economia anual com total em 10 anos; pediu economia mensal da casa. |
| P4 | Casa com 3 moradores e Tarifa Social | Casa informada e caso proposto de aluguel com Tarifa Social | 46,2 kWh/mês; cerca de R$ 32,58 atribuídos ao banho | Reduzir banhos sem comprar equipamento | Entendeu a influência dos outros aparelhos | Autorização, local e orçamentos | 3 | 2 | Diminuiria banhos e acompanharia a conta; achou confuso o limite de 80 kWh; pediu exemplo do desconto. |
| P5 | Casa com 4 moradores | Casa informada e caso proposto de aluguel com Tarifa Social | 81,6 kWh/mês; cerca de R$ 81,60 | Banhos de 5 minutos antes de comprar | Entendeu a variação por potência e hábitos | Permissão do imóvel e orçamentos | 4 | 5 | Mediria primeiro o tempo real; estranhou o aquecedor na tabela quando não pode instalar; pediu indicação clara da opção viável. |

As respostas C1 a C4 foram preservadas em resumo, pois não foi informado se houve ajuda durante a aplicação. Todos relataram que, no caso alugado proposto, o aquecedor não é indicado sem autorização do proprietário.

## Ajustes realizados depois dos testes

| Problema observado | Quem relatou | Ajuste feito | Arquivo e commit |
| --- | --- | --- | --- |
| Gasto mensal pouco visível e tabela difícil de ler | P1, P2, P3 | Destacar o custo mensal do banho e explicar as colunas da comparação | `energia/assistente.py`; commit `203d0c2` |
| Dificuldade com kWh, dados da conta e Tarifa Social | P2, P4 | Incluir orientações curtas na coleta e um exemplo do limite de 80 kWh no resultado | `energia/assistente.py`; commit `203d0c2` |
| Aquecedor aparece quando a instalação não é permitida | P5 | Identificar os cenários solares como indisponíveis e destacar a alternativa viável | `energia/assistente.py`; commit `203d0c2` |
| Economia mensal da família não aparece diretamente | P3 | Mostrar a redução mensal estimada na conta ao escolher a alternativa A | `energia/assistente.py`; commit `03def2b` |

## Resumo

- Participantes: 5 pessoas testadas remotamente em 17/11/2026 por Ryan Luther, sem dados pessoais identificadores no registro.
- O que foi bem compreendido: reduzir a duração do banho é a primeira ação sem investimento; os resultados são estimativas; instalar aquecedor em imóvel alugado requer autorização.
- O que precisou de ajuste: destaque do valor mensal, explicação de kWh e Tarifa Social, leitura da tabela e sinalização das opções solares indisponíveis.
- O que ficou sem resolver: validar as mudanças com participantes depois da revisão da interface.

## Pontos que já esperamos observar

Hipóteses da equipe para prestar atenção durante os testes (não são resultados):

- a tabela com sete colunas pode ser larga demais para ler no terminal;
- "fração solar" e "kWh" podem precisar de explicação mais simples;
- a diferença entre "economia por ano" e "retorno" pode confundir;
- quem tem Tarifa Social pode estranhar a economia igual a zero.

