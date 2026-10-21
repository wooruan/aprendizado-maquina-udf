<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# PBL integrador — Apoio à Permanência

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **Engenharia de Software**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Individual**

## Contexto

Uma instituição quer compreender sinais associados à evasão e oferecer apoio antes do fim do semestre. Público-alvo: estudantes matriculados e equipe de apoio acadêmico. O cenário é didático e a prática usa dados sintéticos.

**Questão norteadora:** como identificar situações que merecem atenção e oferecer apoio, reconhecendo erros do modelo e dificuldades que os dados não capturam?

## Proposta da equipe

### 1. Delimitação

- Problema e público: **Estudantes matriculados com risco de evasão; apoiar a equipe a identificar quem merece atenção**
- Decisão que o resultado pode apoiar: **Quem convidar para apoio voluntário antes do fim do semestre**
- Definição de evasão, unidade e horizonte: **Evasão: não permanecer matriculado ao fim do semestre; unidade: estudante; horizonte: da semana 4 ao fim do semestre**

### 2. Perguntas de negócio

1. **Quais estudantes têm maior chance de evadir até o fim do semestre?**
2. **Quais sinais da semana 4 se associam à evasão?**

### 3. Dados necessários

| Dado | Papel no projeto | Disponível quando? | Origem pretendida | Necessidade e risco |
| --- | --- | --- | --- | --- |
| frequencia_sem4 | Atributo | Semana 4 | Registro de presença (sintético) | Necessário; pode refletir problemas externos (trabalho, saúde) |
| nota_sem4 | Atributo | Semana 4 | Notas lançadas | Necessário; há ausências e critérios variáveis |
| entregas_sem4 | Atributo | Semana 4 | Ambiente virtual | Necessário; mede acesso, não esforço |
| evasao_fim_semestre | Alvo | Fim do semestre | Secretaria acadêmica | Necessário para treinar; só conhecido tarde e a definição pode variar |

Diferencie dados usados na simulação e dados que seriam necessários para uma investigação real: **A simulação usa 3 atributos sintéticos; uma investigação real exigiria definir evasão, mais variáveis de contexto, consentimento e base legal (LGPD).**

### 4. Abordagem e algoritmo

- Classificação, regressão ou outra formulação, com justificativa: **Classificação binária, pois o alvo é evadiu/permaneceu**
- Algoritmo introdutório escolhido: **Árvore de decisão (interpretável)**
- Referência simples: **DummyClassifier: sempre prevê a classe mais frequente**

### 5. Avaliação

- Preparação, divisão e validação: **Imputação pela mediana no Pipeline, divisão 75/25 estratificada e validação cruzada de 5 partes no treino**
- Métricas e razão da escolha: **Acurácia e sensibilidade: a acurácia sozinha engana e a sensibilidade mostra evadidos não detectados**
- Resultados efetivamente calculados e link da evidência: **Teste: acurácia 0,78 (referência 0,5933), sensibilidade 0,6885; notebooks/laboratorio-equipe.ipynb**
- Erros relevantes e consequências: **19 falsos negativos (sem apoio) e 14 falsos positivos (convite desnecessário)**

### 6. Limites e proteção

- Por que os resultados não demonstram causalidade? **O modelo capta associações; outras causas (trabalho, saúde, finanças) não estão nos dados**
- Por que dados sintéticos não validam uso institucional? **Os dados vêm de simulação com regras definidas e não refletem estudantes reais**
- Que grupos podem ser mal representados? Como investigar isso com evidências apropriadas? **Grupos pouco representados (ex.: estudantes que trabalham); comparar erros por grupo com dados reais e autorizados**
- Como minimizar dados, restringir acesso e definir retenção? **Usar só atributos necessários, acesso restrito à equipe de apoio e prazo de retenção definido**
- Como garantir revisão humana e contestação? **Pessoas decidem a partir do alerta; o estudante pode contestar e recusar o apoio**

### 7. Recomendações de apoio

- Ação voluntária proposta: **Convite voluntário para conversar com a equipe de apoio e tutoria**
- Como acolher estudantes não sinalizados pelo modelo: **Canal aberto a todos e acompanhamento pelos professores, pois o modelo erra (19 FN)**
- O que precisa ser verificado antes de aplicação real: **Validar com dados reais, avaliar vieses, aprovação ética e LGPD, e piloto supervisionado**

Previsões não são certezas. Priorize apoio e revisão humana, sem punições ou decisões automáticas prejudiciais.

## Apresentação de cinco minutos

| Tempo | Conteúdo | Responsável |
| --- | --- | --- |
| 1 minuto | Problema e dados | Estudante |
| 2 minutos | Método e resultados | Estudante |
| 1 minuto | Limitações | Estudante |
| 1 minuto | Recomendações de apoio | Estudante |

## Contribuições

| Integrante | Contribuição verificável |
| --- | --- |
| Estudante | Elaboração da proposta, execução do notebook e análise |

[Voltar ao início](README.md).
