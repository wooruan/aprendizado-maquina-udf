<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# Aula 1 — Conceitos e classificação de problemas

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **Engenharia de Software**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Individual**

## Objetivos

Distinguir programação tradicional e Machine Learning, identificar atributos e alvo e diferenciar classificação, regressão e agrupamento.

## 1. Explicação com suas palavras

1. Como um modelo aprende com dados? **Recebe exemplos, encontra padrões e ajusta parâmetros para reproduzi-los em dados novos.**
2. Qual diferença entre algoritmo e modelo? **Algoritmo é o procedimento de aprendizado (ex.: árvore de decisão); modelo é o resultado treinado, usado para prever.**
3. Compare uma regra de bloqueio de palavra com um modelo de spam. **A regra bloqueia só a palavra programada e não muda sozinha; o modelo aprende padrões de mensagens rotuladas e generaliza, mas pode errar.**
4. Dê um exemplo de atributo e alvo e defina o momento da previsão. **Atributos: frequência e nota até a semana 4; alvo: evadiu ou não no fim do semestre; a previsão é feita na semana 4.**

## 2. Quadro comparativo

| Critério | Supervisionado | Não supervisionado |
| --- | --- | --- |
| Presença de alvo no treino | Sim, rótulo conhecido | Não há alvo |
| Pergunta que pode responder | Qual será o rótulo ou valor? | Que grupos ou padrões existem? |
| Tipo de saída | Categoria ou número | Grupos ou padrões |
| Tarefas e exemplo | Classificação (spam) e regressão (vendas) | Agrupamento (perfis de clientes) |
| Dados necessários | Atributos e alvo rotulado | Apenas atributos |
| Forma de avaliação | Compara previsão com alvo real em teste (acurácia, MAE) | Sem gabarito; coesão dos grupos e utilidade para especialistas |
| Limitação | Depende de rótulos confiáveis e caros | Grupos subjetivos, sem verdade para conferir |

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
| 1 Educação | Evadiu/permaneceu (rotulado) | Categoria | Supervisionada, classificação: alvo categórico no histórico | Frequência, notas e entregas de turmas anteriores; rótulos podem ter viés |
| 2 Saúde | Tempo de espera em minutos | Quantidade | Supervisionada, regressão: alvo numérico | Horário, tipo de atendimento, equipe; picos raros são difíceis de prever |
| 3 Comércio | Sem alvo | Grupos | Não supervisionada, agrupamento: não há categorias prévias | Histórico de compras por cliente; grupos subjetivos e difíceis de validar |
| 5 Segurança digital | Spam/legítima (revisadas) | Categoria | Supervisionada, classificação: mensagens já rotuladas | Texto e metadados de mensagens revisadas; spammers mudam de estratégia |
| 6 Comércio | Total de vendas em reais | Quantidade | Supervisionada, regressão: alvo numérico contínuo | Vendas passadas, sazonalidade e promoções; eventos atípicos |

## 4. Raciocínio crítico

“Detectar fraude” define sozinho o tipo de aprendizado? Compare o uso de exemplos rotulados e a busca de operações atípicas sem rótulos. **Não. Com exemplos rotulados de fraude e não fraude, é classificação supervisionada, mas exige rótulos e fraudes novas podem não aparecer neles. Sem rótulos, busca-se operações atípicas (não supervisionada), que sinaliza o diferente, nem sempre fraude.**

## Entrega

Salve este arquivo preenchido. Critérios: distinção conceitual, pertinência dos dados, justificativa e clareza. [Voltar ao início](README.md).
