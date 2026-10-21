<img src="assets/logo-udf.jpg" alt="UDF Centro Universitário" width="230">

**Profa. Kadidja Valéria | UDF**  
Ciência de Dados e Aprendizado de Máquina · Sistemas de Informação · 2026.2

# PBL — Biblioteca em Foco

## Identificação

- Estudante ou equipe: **Pedro Ruan de Oliveira Moura**
- Turma: **Engenharia de Software**
- Data de realização: **21/10/2026**
- Integrantes e contribuições (se em equipe): **Individual**

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
| Problema e decisão | Filas em horários de pico e serviços pouco usados; decidir horários de atendimento e alocação de equipe |
| Público-alvo | Estudantes usuários, equipe de atendimento e gestão |
| O que sabemos | Há filas em certos horários e baixa utilização de alguns serviços (cenário didático) |
| O que precisamos investigar | Em quais horários as filas são maiores e quais serviços são pouco usados |
| Pergunta de negócio 1 | Quantos atendimentos haverá por semana em cada horário, para planejar a equipe? |
| Pergunta de negócio 2 | Existem perfis de uso dos serviços, para direcionar a divulgação? |
| Unidade de análise e período | Um dia/horário de operação; período de um semestre |
| Atributos, unidades e origem pretendida | Dia da semana, hora, usuários ativos, serviço (contagens, horas); origem: registros do sistema da biblioteca, agregados e sem identificação |
| Alvo e momento em que será conhecido, ou ausência de alvo | Pergunta 1: atendimentos por semana (número), conhecido ao fim da semana; pergunta 2: sem alvo |
| Abordagem e justificativa | Pergunta 1: regressão (alvo numérico); pergunta 2: agrupamento (sem alvo) |
| Alternativa sem ML | Gráficos e médias por horário e serviço, que talvez já bastem para ajustar a equipe |
| Como avaliar a proposta | Pergunta 1: MAE comparado a prever a média, em período separado; pergunta 2: utilidade dos grupos para a equipe |
| Privacidade e limitações | Dados agregados e anônimos, acesso restrito, sem perfilar ou discriminar usuários; limitações: um período, sazonalidade |

## Registro de colaboração

| Integrante | Papel | Contribuição |
| --- | --- | --- |
| Estudante | Individual | Preenchimento do canvas |

## Conclusão da equipe

**Proposta:** Começar com análise descritiva dos picos e, se necessário, regressão simples para prever a demanda semanal, com dados agregados.

**Dúvida ainda aberta:** Quais dados a biblioteca já registra e por quanto tempo?

**Feedback recebido e melhoria realizada:** Feedback não recebido (atividade individual); melhoria: incluí alternativa sem ML e cuidados de privacidade.

## Entrega

Canvas preenchido e síntese para apresentação de dois minutos. Avaliar coerência da pergunta, dados, abordagem, responsabilidade e colaboração. [Voltar ao início](README.md).
