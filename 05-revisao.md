<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Questões de revisão — Registro individual

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **PREENCHER**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Atividade individual**

Responda com suas palavras e apresente os cálculos quando solicitados. Os números dos exercícios manuais não são os resultados do laboratório.

## 1. Explique a diferença entre regra programada para bloquear uma palavra e modelo de spam treinado com exemplos.

**Resposta:** Na regra, uma pessoa escreve a condição (se contém a palavra X, bloqueia). Ela é previsível e explicável, mas rígida: não reconhece variações e pode bloquear mensagens legítimas. No modelo, o comportamento vem de exemplos já rotulados como spam ou legítima: ele aprende combinações de sinais e generaliza para mensagens novas, mas erra e depende da qualidade dos rótulos.

## 2. Por que codificar evadiu/permaneceu como 1/0 não transforma classificação em regressão?

**Resposta:** Porque 1 e 0 apenas representam duas classes, sem ordem nem magnitude: evadiu não é “o dobro” de permaneceu. A tarefa depende do significado do alvo. Aqui a saída é uma classe, avaliada por acertos e matriz de confusão, e não uma quantidade com unidade, como reais ou minutos, avaliada por erro numérico.

## 3. Uma biblioteca quer estimar empréstimos e descobrir perfis. Que tarefas correspondem a cada pergunta?

**Resposta:** Estimar empréstimos é regressão, supervisionada, pois o alvo é uma quantidade (empréstimos por semana). Descobrir perfis é agrupamento, não supervisionado, pois não há rótulo ou categoria prévia.

## 4. O que são atributo, alvo e unidade de análise no laboratório educacional?

**Resposta:** Atributos são as informações de entrada disponíveis no momento da previsão: `frequencia_sem4`, `nota_sem4` e `entregas_sem4`. O alvo é o que se quer prever: `evasao_fim_semestre` (0 permaneceu, 1 evadiu). A unidade de análise é o que cada linha representa: um estudante fictício em um semestre.

## 5. Por que calcular a mediana antes de dividir os dados pode invalidar a avaliação?

**Resposta:** Porque a mediana calculada com todos os dados usa informação dos registros de teste. Essa informação vaza para o treino (vazamento de dados), o teste deixa de ser independente e o desempenho estimado fica otimista. O correto é dividir primeiro, aprender a mediana só no treino (por exemplo, dentro de um `Pipeline`) e aplicá-la ao teste.

## 6. Em uma matriz didática com TN=80, FP=5, FN=10, TP=5, calcule acurácia e sensibilidade. O resultado é suficiente para aprovar o modelo?

**Resposta:** Total = 80 + 5 + 10 + 5 = 100. Acurácia = (80 + 5) / 100 = 0,85. Sensibilidade = TP / (TP + FN) = 5 / (5 + 10) = 5 / 15 ≈ 0,33. Não é suficiente: o modelo encontra só um terço dos casos positivos. Além disso, há 85 negativos e 15 positivos, então um modelo que sempre prevê a classe negativa também teria acurácia de 0,85. A acurácia de 0,85 não mostra vantagem sobre a referência.

## 7. Valores reais 100, 120, 140 e previsões 110, 115, 130. Calcule MAE e informe a unidade se o alvo for vendas em reais.

**Resposta:** Erros absolutos: |100 − 110| = 10, |120 − 115| = 5 e |140 − 130| = 10. Soma = 25. MAE = 25 / 3 ≈ 8,33. A unidade é a do alvo: R$ 8,33, ou seja, o erro médio é de cerca de 8,33 reais.

## 8. Um R² de -0,2 significa “20% de acertos negativos”? Explique.

**Resposta:** Não. R² não é porcentagem de acertos. Ele compara a soma dos erros quadráticos do modelo com a de prever sempre a média do conjunto avaliado. Um R² de -0,2 indica que o modelo é pior que essa referência: sua soma de erros quadráticos é cerca de 20% maior que a de prever a média.

## 9. Uma árvore tem acurácia 1,00 no treino e 0,65 na validação. Que hipótese investigar e como?

**Resposta:** A hipótese é sobreajuste: a árvore memorizou o treino, incluindo ruído, e não generaliza. Para investigar, comparar profundidades e tamanhos mínimos de folha por validação cruzada no treino, registrando médias e dispersões e a diferença entre treino e validação; limitar a profundidade ou aumentar `min_samples_leaf`; conferir se há vazamento de dados. O teste não participa dessa escolha.

## 10. Por que escolher a profundidade pelo teste prejudica a estimativa final?

**Resposta:** Porque o teste passa a participar da escolha do modelo. O valor escolhido se ajusta ao acaso daquele teste, e a acurácia medida nele fica otimista, sem dados independentes para a avaliação final. A profundidade deve ser escolhida com treino e validação, deixando o teste para o fim. Se for preciso reselecionar depois de ver o teste, reserva-se um novo teste independente.

## 11. Baixa frequência associada à evasão demonstra causa? Proponha explicação alternativa.

**Resposta:** Não, demonstra apenas associação. Uma explicação alternativa é uma terceira variável, como a necessidade de trabalhar, problemas de saúde ou de deslocamento, que causa tanto as faltas quanto a evasão. Também pode haver causalidade reversa: quem já decidiu sair deixa de frequentar. Para falar de causa seria preciso outro tipo de delineamento.

## 12. Um modelo sinaliza um estudante como possível evasão. Que ação responsável pode ser adotada?

**Resposta:** Um profissional da equipe de apoio revisa o caso e faz um convite voluntário e acolhedor para uma conversa de apoio, explicando que a previsão não é certeza. O estudante pode recusar ou contestar, os dados são protegidos e não há punição nem decisão automática prejudicial.

## Fontes adicionais consultadas

**Além do material da disciplina e das referências listadas em [06-autoavaliacao.md](06-autoavaliacao.md), nenhuma.**

[Voltar ao início](README.md).
