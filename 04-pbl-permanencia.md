<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# PBL integrador — Apoio à Permanência

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **PREENCHER**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **PREENCHER**

## Contexto

Uma instituição quer compreender sinais associados à evasão e oferecer apoio antes do fim do semestre. Público-alvo: estudantes matriculados e equipe de apoio acadêmico. O cenário é didático e a prática usa dados sintéticos.

**Questão norteadora:** como identificar situações que merecem atenção e oferecer apoio, reconhecendo erros do modelo e dificuldades que os dados não capturam?

## Proposta da equipe

### 1. Delimitação

- Problema e público: **Identificar a tempo estudantes em situações que merecem atenção para oferecer apoio antes do fim do semestre. Público: estudantes matriculados e equipe de apoio acadêmico.**
- Decisão que o resultado pode apoiar: **Quem convidar, de forma voluntária, para uma conversa de apoio na semana 4.**
- Definição de evasão, unidade e horizonte: **Evasão: abandono ou não permanência do estudante até o fim do semestre (definição a validar com a instituição). Unidade: um estudante em um semestre. Horizonte: da semana 4 ao fim do semestre.**

### 2. Perguntas de negócio

1. **Que combinações de frequência, nota e entregas até a semana 4 estão associadas à evasão ao fim do semestre?**
2. **Dos estudantes que evadem, qual proporção o modelo sinaliza (sensibilidade), e quantos sinalizados não evadiriam?**

### 3. Dados necessários

| Dado | Papel no projeto | Disponível quando? | Origem pretendida | Necessidade e risco |
| --- | --- | --- | --- | --- |
| Frequência até a semana 4 (%) | Atributo | Fim da semana 4 | Registro de presença | Sinal precoce de afastamento. Risco: reflete também trabalho, saúde ou deslocamento. |
| Nota até a semana 4 (0 a 10) | Atributo | Após as primeiras avaliações | Sistema acadêmico | Indica desempenho. Risco: ausências (imputadas) e critérios diferentes entre docentes. |
| Entregas até a semana 4 (contagem) | Atributo | Fim da semana 4 | Ambiente virtual de aprendizagem | Indica engajamento. Risco: depende da política de cada disciplina. |
| Evasão ao fim do semestre (0/1) | Alvo | Só ao fim do semestre | Secretaria acadêmica | Necessário para treinar e avaliar. Risco: definição imprecisa de evasão. |
| Matrícula e nome | Não entra no modelo | Não se aplica | Secretaria acadêmica | Não é necessário para prever. Risco de identificação; manter separado e restrito. |

Diferencie dados usados na simulação e dados que seriam necessários para uma investigação real: **Na simulação há 600 registros sintéticos com três atributos, gerados por uma função com ruído e sem estudantes reais. Uma investigação real exigiria definição formal de evasão, vários semestres e turmas, dados de contexto coletados com consentimento e minimização, avaliação ao longo do tempo, aprovação institucional e ética e escuta dos estudantes sobre os motivos.**

### 4. Abordagem e algoritmo

- Classificação, regressão ou outra formulação, com justificativa: **Classificação binária supervisionada, pois o alvo é categórico (evadiu ou permaneceu) e há histórico rotulado.**
- Algoritmo introdutório escolhido: **Árvore de decisão (`max_depth=5`, `min_samples_leaf=10`): legível, sem necessidade de padronização e adequada à introdução.**
- Referência simples: **Classificador que prevê sempre a classe mais frequente (permaneceu): acurácia de 0,5933 no teste e sensibilidade 0.**

### 5. Avaliação

- Preparação, divisão e validação: **Imputação pela mediana aprendida no treino (`Pipeline`); 450 registros de treino e 150 de teste, estratificados, semente 42; validação cruzada em 5 partes no treino para escolher a profundidade (2, 3, 5 ou sem limite), com resultado 5. O teste só foi usado no final.**
- Métricas e razão da escolha: **Acurácia, para comparar com a referência; matriz de confusão e sensibilidade da classe 1, porque os erros têm custos diferentes e a acurácia sozinha esconde falsos negativos.**
- Resultados efetivamente calculados e link da evidência: **Acurácia de treino 0,8133, de validação 0,7222 ± 0,0391 e de teste 0,7800 (referência 0,5933). Matriz: TN 75, FP 14, FN 19, TP 42; sensibilidade 0,6885. Evidência: [notebooks/laboratorio-equipe.ipynb](notebooks/laboratorio-equipe.ipynb) e [assets/matriz-confusao.png](assets/matriz-confusao.png).**
- Erros relevantes e consequências: **19 falsos negativos: estudantes que evadiram sem sinalização, sem oferta de apoio. 14 falsos positivos: convites desnecessários, com custo de atenção e risco de estigma se mal conduzidos.**

### 6. Limites e proteção

- Por que os resultados não demonstram causalidade? **Os dados são observacionais (e aqui simulados) e o modelo captura associação. Baixa frequência pode ser consequência de outra situação (trabalho, saúde, desmotivação) que também leva à evasão. Sem delineamento adequado ou intervenção não se separa causa de associação.**
- Por que dados sintéticos não validam uso institucional? **As associações foram definidas pela função de simulação; os resultados refletem essa função, não estudantes reais, e não há validade externa nem avaliação em outras turmas.**
- Que grupos podem ser mal representados? Como investigar isso com evidências apropriadas? **Estudantes que trabalham, de turnos diferentes, com deficiência ou de menor renda, entre outros. Com dados reais, autorizados e em quantidade suficiente, comparar sensibilidade e falsos positivos por grupo, com avaliação de especialistas e escuta dos estudantes. Este conjunto não contém grupos reais e não permite afirmar equidade.**
- Como minimizar dados, restringir acesso e definir retenção? **Usar só os atributos necessários e nenhum identificador no modelo; acesso restrito à equipe de apoio com registro de consultas; prazo de retenção definido e eliminação ao fim dele.**
- Como garantir revisão humana e contestação? **O modelo só sugere. Um profissional analisa cada caso antes de qualquer contato, o estudante pode recusar o convite e contestar a sinalização, e não há decisão automática prejudicial.**

### 7. Recomendações de apoio

- Ação voluntária proposta: **Convite individual e acolhedor para uma conversa de apoio (orientação acadêmica, monitoria, auxílios disponíveis), feito por pessoa da equipe após revisar o caso, deixando claro que a previsão não é certeza.**
- Como acolher estudantes não sinalizados pelo modelo: **Manter canal aberto de procura espontânea, comunicar o apoio a toda a turma e orientar docentes a notar sinais que o modelo não vê. O modelo não pode ser a única porta de entrada.**
- O que precisa ser verificado antes de aplicação real: **Definição de evasão; dados reais disponíveis e autorizados (LGPD); avaliação ao longo do tempo; desempenho por grupo; efeito real do apoio; aprovação ética e institucional; plano de contestação.**

Previsões não são certezas. Priorize apoio e revisão humana, sem punições ou decisões automáticas prejudiciais.

## Apresentação de cinco minutos

| Tempo | Conteúdo | Responsável |
| --- | --- | --- |
| 1 minuto | Problema e dados | PREENCHER |
| 2 minutos | Método e resultados | PREENCHER |
| 1 minuto | Limitações | PREENCHER |
| 1 minuto | Recomendações de apoio | PREENCHER |

## Contribuições

| Integrante | Contribuição verificável |
| --- | --- |
| Pedro Ruan de Oliveira Moura | PREENCHER |

[Voltar ao início](README.md).
