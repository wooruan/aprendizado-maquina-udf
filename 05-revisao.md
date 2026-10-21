<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Questões de revisão — Registro individual

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **Engenharia de Software**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Individual**

Responda com suas palavras e apresente os cálculos quando solicitados. Os números dos exercícios manuais não são os resultados do laboratório.

## 1. Explique a diferença entre regra programada para bloquear uma palavra e modelo de spam treinado com exemplos.

**Resposta:** A regra executa uma instrução fixa (bloquear palavra); o modelo aprende padrões de mensagens rotuladas e generaliza para casos novos, podendo errar.

## 2. Por que codificar evadiu/permaneceu como 1/0 não transforma classificação em regressão?

**Resposta:** Continua classificação porque o alvo representa categorias; 1 e 0 são só códigos, sem ordem ou distância.

## 3. Uma biblioteca quer estimar empréstimos e descobrir perfis. Que tarefas correspondem a cada pergunta?

**Resposta:** Estimar empréstimos é regressão (alvo numérico); descobrir perfis é agrupamento (sem alvo).

## 4. O que são atributo, alvo e unidade de análise no laboratório educacional?

**Resposta:** Atributos: frequência, nota e entregas na semana 4; alvo: evasão no fim do semestre; unidade: um estudante fictício.

## 5. Por que calcular a mediana antes de dividir os dados pode invalidar a avaliação?

**Resposta:** A mediana usaria informação do teste (vazamento) e deixaria a avaliação otimista; deve ser calculada só no treino.

## 6. Em uma matriz didática com TN=80, FP=5, FN=10, TP=5, calcule acurácia e sensibilidade. O resultado é suficiente para aprovar o modelo?

**Resposta:** Acurácia = (80+5)/100 = 0,85; sensibilidade = 5/(5+10) = 0,33. Não basta: o modelo deixa passar 2/3 dos positivos.

## 7. Valores reais 100, 120, 140 e previsões 110, 115, 130. Calcule MAE e informe a unidade se o alvo for vendas em reais.

**Resposta:** Erros absolutos: 10, 5 e 10. MAE = 25/3 ≈ 8,33 reais.

## 8. Um R² de -0,2 significa “20% de acertos negativos”? Explique.

**Resposta:** Não. R² não é porcentagem; negativo significa pior que prever a média.

## 9. Uma árvore tem acurácia 1,00 no treino e 0,65 na validação. Que hipótese investigar e como?

**Resposta:** Sobreajuste: o modelo memorizou o treino. Investigar com validação cruzada, limitando max_depth e aumentando min_samples_leaf.

## 10. Por que escolher a profundidade pelo teste prejudica a estimativa final?

**Resposta:** O teste passaria a fazer parte da seleção e a estimativa final ficaria otimista; escolher com validação no treino.

## 11. Baixa frequência associada à evasão demonstra causa? Proponha explicação alternativa.

**Resposta:** Não, mostra associação. Alternativa: trabalho ou problema de saúde causa a baixa frequência e a evasão.

## 12. Um modelo sinaliza um estudante como possível evasão. Que ação responsável pode ser adotada?

**Resposta:** Oferecer apoio voluntário com revisão humana, sem punição nem decisão automática, permitindo contestação.

## Fontes adicionais consultadas

**Nenhuma além do material da disciplina. Claude (IA) usado como apoio na redação.**

[Voltar ao início](README.md).
