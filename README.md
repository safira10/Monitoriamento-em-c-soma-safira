# Desafio de Monitoramento de Temperatura

## 1. Identificação
- **Aluna:** Safira
- **Disciplina:** [PREENCHER — nome da disciplina]
- **Professora:** Profa. Karla Sartin
- **Título do projeto:** Sistema de Monitoramento de Temperatura em C

## 2. Objetivo
O programa simula um sistema de monitoramento de temperatura, que recebe leituras sucessivas de um sensor e verifica se cada uma ultrapassa um limite pré definido. Caso ocorram 3 leituras consecutivas acima do limite, o monitoramento é encerado automaticamente.

## 3. Funcionamento do programa
- **Limite:** definido no início, com validação em `do...while` (aceita apenas -50 a 100°C).
- **Leituras:** a cada volta do laço principal o usuário digita uma temperatura, também validada em `do...while` (-100 a 150°C).
- **Valores inválidos:** enquanto o valor tiver fora da faixa, o programa mostra erro e pede de novo.
- **Acima do limite:** se a leitura for maior que o limite, conta como ocorrência e incrementa o contador de consecutivas.
- **Consecutivas:** o contador zera toda vez que aparece uma leitura dentro do limite, assim só conta sequências sem interrupção.
- **Encerramento:** para automático ao atingir 3 consecutivas, ou manual quando o usuario responde "0" pra continuar.

## 4. Estruturas de repetição
- **`do...while`**: usado na validação do limite e de cada temperatura, pois precisa ler o valor primeiro pra depois poder validar.
- **`while`**: usado no laço principal, já que não se sabe quantas leituras vão acontecer — depende do usuário e de não ter 3 consecutivas ainda.

## 5. Como executar
```bash
gcc monitoramento.c -o monitoramento
./monitoramento
```

## 6. Testes realizados
- **Teste 1:** entradas inválidas (limite 500, temperatura -200) — programa recusou e pediu novamente. `evidencias/teste01.png`
- **Teste 2:** temperaturas acima do limite mas não consecutivas (35, 20, 38, 22) — contador reiniciou e não encerrou sozinho. `evidencias/teste02.png`
- **Teste 3:** três temperaturas seguidas acima do limite (32, 34, 36) — programa detectou e encerou o monitoramento automaticamente. `evidencias/teste03.png`

## 7. Relatório final
No fim, o programa mostra: quantidade de leituras, soma, média, maior, menor, quantas ficaram acima do limite e o percentual.
