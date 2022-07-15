# Credit Score Modeling

## 1. Trabalho de Conclusão de Curso (TCC)
Esse notebook foi desenvolvido como atividade de Trabalho de Conclusão de Curso (TCC) do curso de Data Science e Analytics da Universidade de São Paulo-ESALQ.


## 2. Entendimento do Negócio
  O risco de crédito é a possibilidade de o devedor não cumprir com as obrigações relativas às transações financeiras de crédito. O não cumprimento dessas obrigações é chamado de inadimplência. Na finalidade de maximizar seus lucros, a instituição financeira deve avaliar e minimizar o risco de crédito de sua carteira de clientes, devendo adotar ferramentas estatísticas mais eficientes para a análise e o controle de risco de crédito associado aos empréstimos.
 
 Uma dessas ferramentas são os modelos de “credit scoring”, que visam medir de forma objetiva, rápida e em massa, o risco de inadimplência do solicitante, geralmente atribuindo-se pesos a variáveis que caracterizam a operação, impactando diretamente na rentabilidade da carteira de crédito da companhia (Sicsú, 2010).
  
  Analisar se o tomador de empréstimo conseguirá arcar com suas obrigações é investigar tanto o seu histórico de pagamentos quanto a sua intenção, assim como a sua capacidade de pagar olhando as perspectivas financeiras. Ambas as apurações necessitam de dados atualizados e, de modo geral, quanto mais informações obtiver, melhor a instituição financeira poderá decidir quanto à concessão do crédito. De acordo com Mori e Rochman (2014), embora ambas as verificações sejam fundamentais, o aspecto econômico é mais importante, pois é mais fácil um tomador deixar de pagar porque não pôde do que por não estar disposto.
 
 Levando esses dois aspectos em consideração, o presente trabalho busca detalhar o desenvolvimento, implantação, monitoramento, calibração e validação de um modelo de “credit scoring” para o processo de aprovação de crédito.


## 3. A Base de Dados e o LendingClub
  O dataset foi composto de 2.260.701 empréstimos aceitos na plataforma LendingClub no período de 2007 a 2018 e está disponível na plataforma Kaggle pelo link https://www.kaggle.com/datasets/wordsforthewise/lending-club
 
  A LendingClub é a maior plataforma de empréstimos peer-to-peer do mundo, com sede em San Francisco, Califórnia, permitindo que seus usuários façam empréstimos pessoais não securitizados entre US$ 1.000 e US$ 40.000 com período padrão de amortização de três anos. Os Investidores podem selecionar seus tomadores de empréstimos através das informações fornecidas na plataforma, ganhando dinheiro com os juros dessas operações. A LendingClub atua como intermediadora cobrando uma taxasobre os empréstimos.
 
  Para este estudo de caso, será utilizado análise exploratória dos dados e Machine Learning. Também desenvolveremos uma compreensão básica sobre a análise de risco em serviços bancários e financeiros.

-----

## 4. Objetivo
  Os dados fornecidos contêm as informações sobre os solicitantes de empréstimos anteriores e se eles honraram o pagamento ou não. 

  O objetivo é identificar padrões que indiquem se uma pessoa é suscetível de inadimplência, e quais são as ações em que o tomador de decisão poderá fazer, dentro da margem de risco. Ele poderá tomar ações como:
 - negar o empréstimo
 - reduzir o valor do empréstimo
 - emprestar (para candidatos de risco) a uma taxa de juros mais alta, etc.

Quando uma pessoa solicita um empréstimo, existem dois tipos de decisões que podem ser tomadas pela empresa:
- Rejeitar o empréstimo: quando o candidato não atende aos requisitos de risco.
- Aceitar o empréstimo: existem 3 cenários possíveis
  - Totalmente pago (Fully paid): O requerente pagou integralmente o empréstimo (o principal e a taxa de juros).
  - Pagamento em curso (Current): O requerente está em processo de pagamento das parcelas, ou seja, o prazo do empréstimo ainda não está concluído.
  - Inadimplente (Charged-off): O solicitante perdeu o prazo de pagamento e não paga as parcelas há muito tempo.
