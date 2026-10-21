<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 1 — Conceitos e classificação de problemas

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **PREENCHER**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Atividade individual**

## Objetivos

Distinguir programação tradicional e Machine Learning, identificar atributos e alvo e diferenciar classificação, regressão e agrupamento.

## 1. Explicação com suas palavras

1. Como um modelo aprende com dados? **Um modelo aprende ajustando seus parâmetros a partir de exemplos. No aprendizado supervisionado, ele compara a previsão com o alvo conhecido de cada exemplo e se ajusta para reduzir o erro. Assim captura regularidades dos dados sem que uma pessoa escreva as regras. O que importa é o desempenho em dados novos, não a memorização dos exemplos de treino.**
2. Qual diferença entre algoritmo e modelo? **O algoritmo é o procedimento de aprendizado (por exemplo, a construção de uma árvore de decisão). O modelo é o resultado desse procedimento aplicado a dados específicos (a árvore pronta, com perguntas e limiares definidos), que é usado para prever. O mesmo algoritmo com dados diferentes gera modelos diferentes.**
3. Compare uma regra de bloqueio de palavra com um modelo de spam. **A regra é escrita por uma pessoa: se a mensagem contém a palavra X, bloqueia. É simples, previsível e explicável, mas fácil de driblar (grafia alterada) e bloqueia mensagens legítimas que contenham a palavra. O modelo de spam é treinado com mensagens já revisadas e aprende combinações de sinais (remetente, links, texto), generalizando para variações novas. Em troca, erra (falsos positivos e negativos), depende da qualidade dos rótulos e precisa ser reavaliado ao longo do tempo.**
4. Dê um exemplo de atributo e alvo e defina o momento da previsão. **Unidade: um estudante em um semestre. Atributos: frequência, nota e entregas observadas até a semana 4. Alvo: evasão ao fim do semestre (0 permaneceu, 1 evadiu). O momento da previsão é o fim da semana 4: só podem entrar atributos disponíveis até ali, e o alvo só é conhecido no fim do semestre.**

## 2. Quadro comparativo

| Critério | Supervisionado | Não supervisionado |
| --- | --- | --- |
| Presença de alvo no treino | Sim: cada exemplo tem rótulo ou valor conhecido | Não: só há atributos |
| Pergunta que pode responder | Qual será a classe ou o valor de um caso novo? | Existem grupos, estruturas ou casos atípicos nos dados? |
| Tipo de saída | Categoria (classificação) ou número (regressão) | Grupo atribuído ou pontuação de atipicidade |
| Tarefas e exemplo | Classificação (spam ou legítima); regressão (tempo de espera em minutos) | Agrupamento (perfis de compra); detecção de anomalias |
| Dados necessários | Atributos e alvo conhecido, em quantidade e representatividade suficientes | Apenas atributos, sem custo de rotulagem |
| Forma de avaliação | Comparação com o alvo em dados de teste (acurácia, matriz de confusão, MAE, R²) | Sem gabarito: coesão e separação dos grupos, interpretação com especialistas, utilidade para a decisão |
| Limitação | Rotular custa e pode carregar viés; só aprende o que está nos rótulos | Os grupos podem não ter significado; dependem dos atributos e do número de grupos; difícil validar |

## 3. Situações-problema

Os casos são cenários didáticos. Escolha **pelo menos cinco** e justifique sua classificação pelo significado do alvo ou por sua ausência.

| Caso | Situação-problema |
| --- | --- |
| 1 Educação | Prever evadiu/permaneceu com histórico rotulado de turmas anteriores. |
| 2 Saúde | Estimar o tempo de espera em minutos a partir de registros de atendimento. |
| 3 Comércio | Descobrir perfis de compra sem categorias prévias de clientes. |
| 4 Finanças | Prever inadimplente/adimplente com contratos e desfechos conhecidos. |
| 5 Segurança digital | Distinguir spam/legítima com mensagens já revisadas. |
| 6 Comércio | Estimar o total de vendas em reais na próxima semana. |
| 7 Educação | Agrupar perfis de acesso ao ambiente virtual sem rótulo de evasão. |
| 8 Saúde | Classificar exames em categorias previamente definidas por especialistas. |

| Caso escolhido | Alvo ou ausência de alvo | Categoria, quantidade ou grupos? | Abordagem e justificativa | Dados necessários e limitação |
| --- | --- | --- | --- | --- |
| 1 Educação | Alvo: evadiu ou permaneceu, conhecido nas turmas anteriores | Categoria (duas classes) | Supervisionada, classificação: o alvo é um rótulo conhecido no histórico | Frequência, notas e entregas até o momento da previsão, mais o desfecho das turmas anteriores. Limitação: associação não é causa, e motivos de evasão que os dados não captam |
| 2 Saúde | Alvo: tempo de espera em minutos | Quantidade | Supervisionada, regressão: o alvo é numérico e contínuo | Dia, horário, tipo de atendimento, equipe disponível e fila no momento, mais o tempo realmente medido. Limitação: picos incomuns e mudanças de rotina; extrapolação |
| 3 Comércio | Sem alvo: não há categorias prévias | Grupos | Não supervisionada, agrupamento: queremos descobrir perfis, não prever um rótulo | Histórico de compras por cliente (frequência, valor, categorias). Limitação: os grupos dependem dos atributos e do número de grupos, exigem interpretação e não têm gabarito; cuidado com privacidade |
| 5 Segurança digital | Alvo: spam ou legítima, definido na revisão | Categoria (duas classes) | Supervisionada, classificação: há mensagens já rotuladas | Texto, remetente e links de mensagens revisadas. Limitação: spammers mudam de padrão, rótulos podem ter erro, e falso positivo bloqueia mensagem legítima |
| 6 Comércio | Alvo: total de vendas em reais na próxima semana | Quantidade | Supervisionada, regressão: o alvo é um valor numérico | Série semanal de vendas, promoções, calendário e sazonalidade. Limitação: é preciso respeitar a ordem temporal; eventos imprevistos e extrapolação |
| 7 Educação | Sem alvo: não há rótulo de evasão | Grupos | Não supervisionada, agrupamento: busca perfis de acesso sem rótulo | Registros de acesso (frequência, horários, tempo, atividades). Limitação: os grupos não dizem quem vai evadir; interpretação subjetiva; privacidade dos registros |

## 4. Raciocínio crítico

“Detectar fraude” define sozinho o tipo de aprendizado? Compare o uso de exemplos rotulados e a busca de operações atípicas sem rótulos. **Não define. Com exemplos rotulados (fraude e legítima) o problema é de classificação supervisionada: o modelo aprende os padrões das fraudes já conhecidas e permite medir o desempenho, mas só reconhece o que se parece com o passado. Os rótulos são raros (classes desbalanceadas, em que a acurácia engana) e demoram a existir. Sem rótulos, a busca de operações atípicas (detecção de anomalias, não supervisionada) pode revelar tipos novos de fraude, mas atípico não é o mesmo que fraudulento: gera falsos alarmes e é difícil de avaliar sem gabarito. O tipo de aprendizado depende dos dados disponíveis e de como o problema é formulado. Na prática, costuma-se combinar as duas abordagens, com revisão humana dos casos sinalizados.**

## Entrega

Salve este arquivo preenchido. Critérios: distinção conceitual, pertinência dos dados, justificativa e clareza. [Voltar ao início](README.md).
