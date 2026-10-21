<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# PBL — Biblioteca em Foco

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **PREENCHER**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **PREENCHER**

## Situação-problema

Uma biblioteca universitária enfrenta filas em horários específicos e baixa utilização de alguns serviços. A coordenação deseja melhorar o atendimento e planejar recursos. Este é um cenário didático.

**Público-alvo:** estudantes usuários, equipe de atendimento e gestão.

**Questão norteadora:** como os dados podem orientar o planejamento da biblioteca e a oferta de serviços sem identificar ou discriminar seus usuários?

## Investigação em equipe

1. Delimitem o problema e a decisão a apoiar.
2. Registrem o que já sabem e o que precisam investigar.
3. Formulem duas perguntas de negócio.
4. Definam a unidade de análise, os atributos e o alvo, quando houver.
5. Justifiquem a abordagem e indiquem se uma análise descritiva já seria suficiente.
6. Proponham avaliação, cuidados com os dados e limitações.

## Canvas da equipe

| Campo | Registro |
| --- | --- |
| Problema e decisão | Filas em horários específicos e baixa procura por alguns serviços. Decisão: como distribuir a equipe e os horários de atendimento e quais serviços divulgar ou reformular. |
| Público-alvo | Estudantes usuários, equipe de atendimento e gestão. |
| O que sabemos | Segundo a coordenação, há filas em certos horários e alguns serviços são pouco usados. O cenário é didático e não há dados reais. |
| O que precisamos investigar | Em quais dias e horários ocorrem as filas e qual a espera; quais serviços têm pouca procura e por quê (desconhecimento, horário, localização); se a demanda muda ao longo do semestre (por exemplo, em períodos de prova). |
| Pergunta de negócio 1 | Em quais dias e horários a demanda por atendimento supera a capacidade, e como isso varia ao longo do semestre? |
| Pergunta de negócio 2 | Quais serviços têm baixa utilização e que perfis de uso, em dados agregados, podem orientar a divulgação deles? |
| Unidade de análise e período | Pergunta 1: uma hora de um dia de funcionamento (contagens agregadas). Pergunta 2: um serviço em uma semana. Período: um semestre letivo. |
| Atributos, unidades e origem pretendida | Dia da semana e hora (categorias), fase do calendário acadêmico (categoria), usuários ativos (contagem), horas de abertura (h), atendentes em turno (contagem) e serviço (categoria). Origem: registros agregados do sistema de empréstimo e atendimento e o calendário acadêmico. |
| Alvo e momento em que será conhecido, ou ausência de alvo | Pergunta 1: número de atendimentos por hora (ou espera média em minutos), conhecido ao fim da hora; a previsão seria feita com antecedência, por exemplo no dia anterior. Pergunta 2: sem alvo. |
| Abordagem e justificativa | Pergunta 1: regressão supervisionada, pois o alvo é uma quantidade. Pergunta 2: agrupamento não supervisionado, pois não há categorias prévias de serviços ou perfis. |
| Alternativa sem ML | Análise descritiva: médias de atendimento por dia e hora, mapa de calor e ranking de uso dos serviços. Pode ser suficiente para reorganizar as escalas antes de qualquer modelo. |
| Como avaliar a proposta | Pergunta 1: MAE em atendimentos por hora, comparado a uma referência (a média do treino), com divisão que preserve a ordem do tempo (treinar em semanas passadas e testar em semanas futuras). Pergunta 2: interpretação dos grupos pela equipe. Depois, um piloto para verificar se a fila diminuiu. |
| Privacidade e limitações | Usar apenas dados agregados, sem nome nem matrícula; acesso restrito e prazo de retenção definido. Limitações: um semestre pode não representar outros, há sazonalidade, e dados de uso não mostram quem não frequenta a biblioteca. Não discriminar usuários por perfil. |

## Registro de colaboração

| Integrante | Papel | Contribuição |
| --- | --- | --- |
| Pedro Ruan de Oliveira Moura | PREENCHER | PREENCHER |

## Conclusão da equipe

**Proposta:** Começar por uma análise descritiva dos atendimentos por dia e hora para reorganizar as escalas. Em seguida, estimar a demanda por hora com regressão e agrupar os serviços pelo padrão de uso, sempre com dados agregados.

**Dúvida ainda aberta:** Se os registros existentes têm granularidade horária e como medir o tempo de espera na fila.

**Feedback recebido e melhoria realizada:** PREENCHER

## Entrega

Canvas preenchido e síntese para apresentação de dois minutos. Avaliar coerência da pergunta, dados, abordagem, responsabilidade e colaboração. [Voltar ao início](README.md).
