<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 2 — Registro do laboratório supervisionado

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **Engenharia de Software**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Individual**

## Percurso escolhido

- [x] Python/Colab ou Jupyter.
- [ ] Orange Data Mining.

Use o [notebook de apoio](notebooks/laboratorio.ipynb) ou o [CSV sintético](dados/educacionais-sinteticos.csv). O CSV contém 600 registros fictícios. Atributos: `frequencia_sem4`, `nota_sem4`, `entregas_sem4`. Alvo: `evasao_fim_semestre` (0 permaneceu, 1 evadiu). As associações foram definidas pela simulação, sem validade empírica sobre estudantes reais.

## 1. Ambiente e reprodução

| Item | Registro |
| --- | --- |
| Ambiente e data | Python 3.12.14 (Jupyter), 21/10/2026 |
| Versões das ferramentas/bibliotecas | NumPy 2.3.5, pandas 2.2.3, matplotlib 3.10.8, scikit-learn 1.8.0 |
| Semente aleatória | 42 |
| Caminho do notebook executado ou fluxo Orange | notebooks/laboratorio-equipe.ipynb |
| Origem dos dados e condição sintética | CSV sintético fornecido (600 registros fictícios), gerado por simulação |

## 2. Problema e preparação

- Pergunta de negócio: **Quem poderia receber convite voluntário de apoio antes do fim do semestre?**
- Unidade de análise e horizonte: **Um estudante fictício; horizonte até o fim do semestre**
- Atributos disponíveis no instante da previsão: **frequencia_sem4, nota_sem4 e entregas_sem4 (semana 4)**
- Variável-alvo e sua natureza: **evasao_fim_semestre, binária (0 permaneceu, 1 evadiu): classificação**
- Ausências e outros problemas encontrados: **30 valores ausentes em nota_sem4**
- Tratamentos e conjunto usado para aprendê-los: **Imputação pela mediana aprendida só no treino (Pipeline)**

## 3. Desenvolvimento e teste

- Método de divisão e justificativa: **train_test_split 75/25, estratificado, semente 42; registros independentes**
- Quantidades de treino e teste: **Treino 450 e teste 150**
- Procedimento de validação no treino: **Validação cruzada estratificada de 5 partes no treino**
- Parâmetros da árvore e como foram escolhidos: **max_depth=5 (melhor validação entre 2, 3, 5 e None); min_samples_leaf=10 fixo**
- Como o teste ficou fora da seleção: **Teste usado só uma vez, após escolher o modelo**

### Alternativa Orange

Confira o alvo como categórico. Registre as conexões: File/Select Columns → Test & Score (Data), Tree → Test & Score (Learner), Test & Score → Confusion Matrix (Evaluation Results). Data Table permite inspeção. Se usar Preprocess, conecte o preprocessor ao learner para ajustar transformações dentro do treino. Não use apenas `Test on train data` como avaliação final.

**Fluxo e método de avaliação realmente utilizados:** Não usei Orange; usei Python (scikit-learn) com validação cruzada.

Se comparar configurações, use validação no treino e reserve teste independente. Documente em Test & Score as entradas Data e Test Data, quando utilizadas.

## 4. Resultados calculados de classificação

| Modelo | Configuração | Acurácia de treino | Acurácia de validação e dispersão | Acurácia de teste |
| --- | --- | --- | --- | --- |
| Referência | DummyClassifier (classe mais frequente) | não calculada | não calculada | 0,5933 |
| Árvore final | Árvore, max_depth=5, min_samples_leaf=10 | 0,8133 | 0,7222 (desvio 0,0391) | 0,7800 |

Não invente valores. Se sua ferramenta não produziu uma medida, registre “não calculada” e explique.

**Matriz: linhas reais e colunas previstas; classe positiva = 1.**

| Real / previsto | Permaneceu (0) | Evadiu (1) |
| --- | --- | --- |
| Permaneceu (0) | 75 (TN) | 14 (FP) |
| Evadiu (1) | 19 (FN) | 42 (TP) |

- Acurácia calculada manualmente pela matriz: **(75+42)/150 = 0,78**
- Sensibilidade da classe 1: **42/(42+19) = 0,6885**
- Comparação com referência: **Árvore 0,78 contra 0,5933 da referência**
- Consequências dos falsos positivos: **Convite desnecessário a 14 estudantes; custo baixo se o apoio for voluntário**
- Consequências dos falsos negativos: **19 estudantes em risco sem apoio (31% dos evadidos); é o erro mais grave**
- Interpretação do gráfico e da árvore: **Há mais falsos negativos que falsos positivos; a árvore divide por perguntas sobre frequência, nota e entregas, relações definidas pela simulação**

## 5. Experimentos no treino

Compare parâmetros usando apenas treino/validação. Após conhecer o teste, uma nova seleção exige novo teste independente para avaliação final.

| Experimento | Alteração | Resultado de validação | Interpretação |
| --- | --- | --- | --- |
| 1 | min_samples_leaf = 5, 10, 20, 40 | 0,7222; 0,7222; 0,7267; 0,7289 (desvios 0,030 a 0,048) | Diferenças dentro do desvio; mantive 10, pois mudar após ver o teste exigiria novo teste |
| 2 | Retirar frequencia_sem4 | 0,7156 (desvio 0,0362) contra 0,7222 | Queda pequena, dentro do ruído; não prova causalidade |

Responda:

1. Como a profundidade e o tamanho das folhas podem afetar o sobreajuste? **Árvore profunda e folhas pequenas memorizam o treino: o treino sobe e a validação não acompanha. Limitar profundidade e exigir folhas maiores reduz isso.**
2. Retirar um atributo e observar mudança no desempenho prova causalidade? **Não. Mostra só a dependência do modelo; atributos correlacionados podem compensar.**
3. Se 95% permanecem, o que acontece com um modelo que sempre prevê permanência? **Acerta 95% sem detectar nenhum evadido (sensibilidade 0); a matriz mostraria TP=0.**

## 6. Regressão — seção independente

Execute a seção da biblioteca no notebook ou registre o procedimento equivalente em Orange. Dados também sintéticos. Alvo numérico: empréstimos por semana.

| Item | Registro |
| --- | --- |
| Atributos e alvo | Atributos: usuarios_ativos e horas_abertura; alvo: emprestimos_semana |
| Divisão e preparação | Divisão aleatória 75/25 (semente 42); imputação pela mediana no Pipeline |
| MAE do modelo e unidade | 28,59 empréstimos/semana |
| MAE da referência | 84,73 empréstimos/semana (média do treino) |
| R² do teste | 0,8774 |
| Interpretação do gráfico observado/previsto | Pontos próximos da linha de igualdade: previsões perto do observado |
| Interpretação dos resíduos | Resíduos em torno de zero, compatíveis com o ruído da simulação |
| Limitação de extrapolação | Fora de 100–1000 usuários ou 20–60 horas seria extrapolação, não confiável |

Explique por que R² não é porcentagem de acertos: **R² compara os erros quadráticos com os de prever a média; pode ser negativo e não conta acertos.**

## 7. Evidências e conclusão

- Link relativo do notebook/fluxo: **notebooks/laboratorio-equipe.ipynb**
- Links das imagens, se houver: **Não há imagens salvas; os gráficos estão no notebook**
- Principal aprendizado: **Escolher parâmetros só com validação e manter o teste para o final**
- Limitações de generalização e vieses possíveis: **Dados sintéticos e uma única divisão: não valem para estudantes reais; vieses por grupo não podem ser avaliados**
- Cuidados com privacidade e uso responsável: **Só dados sintéticos; em caso real, minimizar dados, restringir acesso e manter revisão humana**

Para inserir uma imagem salva, use `![Matriz de confusão](assets/minha-matriz.png)` e confira se o arquivo existe. Mostre apenas dados sintéticos.

[Voltar ao início](README.md).
