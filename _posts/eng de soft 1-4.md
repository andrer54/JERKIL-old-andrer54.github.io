
MÓDULO 4
Descrever a importância do Gerenciamento de Risco no projeto de software

RISCO
As melhores práticas desenvolvidas neste módulo têm por fundamento o PMBOK, cujos processos estão definidos na figura 15, vista no módulo 3.


Fonte: kitzcorner/Shutterstock
Imagine você realizando um planejamento de uma viagem ao exterior nas próximas férias. Considerando que o roteiro está definido, bem como as reservas dos hotéis realizadas, as passagens reservadas e uma quantidade de dólares adquiridos, podemos, intuitivamente, aplicar uma abstração denominada risco, ou seja, o que pode ocorrer de errado na minha viagem?

Vamos, então, gerar uma pequena lista de possíveis eventos negativos para entendermos os conceitos:

Ocorrência de um problema de saúde, por causa de um acidente ou ter contraído alguma doença.
Cancelamento da passagem pela companhia aérea.
A quantidade de dólar adquirida não ser suficiente.
Observe que a avaliação de risco gera uma preocupação que o conduz ao futuro, inserindo um grau de incerteza – ele pode ou não ocorrer. Ao mesmo tempo, espera-se que fique clara a importância de sua avaliação, pois, caso ocorra algum dos eventos listados durante a sua viagem, essa pode estar seriamente comprometida.

UM RISCO É UM EVENTO OU CONDIÇÃO INCERTA QUE, SE OCORRER, PROVOCARÁ UM EFEITO POSITIVO OU NEGATIVO EM UM OU MAIS OBJETIVOS DO PROJETO.
(PMI, 2017)

Você pode agora questionar: efeito positivo?

O risco não trata de efeitos negativos ou coisas que podem dar errado? Realmente, o mais comum é associar risco a algo negativo, mas, conceitualmente, pode ser algo positivo. Vamos exemplificar.

Imagine uma empresa exportadora de minério que elabora o seu plano de investimento para o próximo ano e que identificou o seguinte risco: variação cambial do dólar, sendo essa a moeda padrão da comercialização de commodities. O planejamento inclui aplicar os recursos de investimentos em novos projetos de prospecção de minas.

Neste momento, faz-se necessário realizar uma projeção do valor do câmbio para o próximo ano, pois, como apresentado, o faturamento da empresa está atrelado à referida moeda – vamos imaginar que o valor projetado para o dólar foi de R$ 5,50 (reais). Temos então dois cenários possíveis:


Fonte: Porcupen/Shutterstock
CENÁRIO NEGATIVO
O dólar chega a valer R$ 4,00, ou seja, a empresa terá que reduzir o seu portfólio de projetos em função da redução do capital de investimento, pois a empresa irá faturar menos com a mesma quantidade de produtos exportados. Esse cenário é um obstáculo para a consecução dos resultados esperados.


Fonte: Porcupen/Shutterstock
CENÁRIO POSITIVO
O dólar chega a valer R$ 7,00, ou seja, a empresa poderá incrementar o seu portfólio de projetos em função do aumento de capital de investimento, pois a empresa irá faturar mais com mesma quantidade de produtos exportados. Esse cenário é uma oportunidade para a consecução dos resultados esperados.

ATENÇÃO
Lembrando que nosso contexto é a Engenharia de Software, a melhor prática é focar nos cenários negativos.

Como citado anteriormente, o risco permite planejar o futuro e evitar que empresas tenham “sustos” nos seus projetos em função de eventos inesperados e, a partir destes, iniciar as devidas tratativas. Em síntese, a área de Gerenciamento de Risco permite a sistematização dessas tratativas em forma de plano.

Veja, na figura 15, os processos que fazem parte da área de conhecimento Gerenciamento de Riscos. Os referidos processos permitem a sistematização da identificação, da análise e das respostas aos riscos de um projeto.

IDENTIFICAÇÃO DE RISCOS
Alinhado às descrições apresentadas, podemos determinar que um risco possui três componentes: um evento; a probabilidade de ocorrência do evento, associada ao grau de incerteza; e o impacto decorrente do evento, caso aconteça, associado ao grau de perda.

Como parte do Plano de Gerenciamento de Riscos, a elaboração de uma Estrutura Analítica do Risco (EAR) auxilia na definição de potenciais fontes de riscos para o projeto, permitindo a identificação de riscos de forma categorizada, exemplificada na figura 19.

O processo de Identificação de Riscos requer uma clara compreensão da missão, escopo e objetivos do projeto.


Fonte: Wikipedia
Figura 19 - Extrato de um exemplo de EAR.
Segundo Pressman (2016), uma proposta para identificação de categorias genéricas de risco relacionadas com o software inclui:

TAMANHO DO PRODUTO
Riscos associados ao tamanho do software.

IMPACTO NO NEGÓCIO
Riscos oriundos de restrições impostas pelo cliente ou pelo mercado.

CARACTERÍSTICAS DO ENVOLVIDO
Riscos relacionados com a comunicação oportuna, por exemplo, entre engenheiro de software e um determinado cliente.

DEFINIÇÃO DO PROCESSO
Riscos relacionados com a auditoria de processos por parte da equipe de qualidade.

AMBIENTE DE DESENVOLVIMENTO
Riscos associados às ferramentas disponíveis para criar o software, tais como, ferramentas case disponíveis.

TECNOLOGIA A SER CRIADA
Risco relacionado com as inovações tecnológicas aplicadas no desenvolvimento do software, tal como, um novo framework de persistência de dados.

QUANTIDADE DE PESSOAS E EXPERIÊNCIA
Riscos que associados aos perfis dos engenheiros de software, administradores de banco de dados, web designers, enfim, da equipe que realizará o trabalho.


Fonte: G-Stock Studio/Shutterstock
O processo de identificação de riscos é iterativo, pois novos riscos podem aparecer durante o projeto. Uma técnica muito comum a ser utilizada na identificação de riscos é a técnica denominada de Brainstorming. Esta inclui uma reunião com um conjunto multidisciplinar de especialistas com a finalidade de obter uma lista abrangente de cada risco de projeto e as fontes do risco geral do projeto, sendo as ideias geradas sob a orientação de um facilitador.


Fonte: Boophuket/Shutterstock
Uma segunda técnica é conhecida como Lista de Verificação ou Check List, ou seja, uma lista de riscos baseada em informações históricas e conhecimentos acumulados de projetos semelhantes e outras fontes de informações. Essas listas ajudam a identificar pontos fracos no projeto atual a partir de experiências passadas.


Fonte: djile/Shutterstock
Uma terceira técnica proposta pelo PMBOK é a entrevista.

A seguir, vamos explorar um exemplo da aplicação dessa técnica com experientes gerentes de projeto de software, que levantaram as seguintes questões e foram apresentadas por Pressman (2016).

Exemplo da Técnica de Entrevista

A alta gerência e o cliente estão formalmente comprometidos em apoiar o projeto?
Os usuários estão bastante comprometidos com o projeto e o sistema/produto a ser criado?
Os requisitos são amplamente entendidos pela equipe de engenharia de software e clientes?
Os clientes foram totalmente envolvidos na definição dos requisitos?
Os usuários têm expectativas realistas?
O escopo do projeto é estável?
A equipe de Engenharia de Software tem a combinação de aptidões adequadas?
Os requisitos de projetos são estáveis?
A equipe de projeto tem experiência com a tecnologia a ser implementada?
O número de pessoas na equipe de projeto é adequado para o trabalho?
Todos os clientes e usuários concordam com a importância do projeto e com os requisitos do sistema/produto a ser criado?
Caso alguma questão seja respondida negativamente, insira o risco, ou riscos, na sua lista de riscos.

ANÁLISE QUALITATIVA DOS RISCOS
Até o momento, temos uma lista com os prováveis riscos do projeto.

Vamos imaginar que tenhamos uma longa lista. Isso, intuitivamente, nos leva a considerar a necessidade de determinarmos a importância relativa entre os referidos riscos, a fim de que possamos saber quais os riscos prioritários.

É interessante destacar que a tratativa de riscos poderá gerar alocação de recursos financeiros, impactando o orçamento do projeto, ou seja, não é possível tratar os riscos listados com a mesma prioridade, devido às limitações de tempo e recursos.

O objetivo da Análise Qualitativa dos Riscos é priorizar os riscos, combinando a probabilidade de ocorrência e, caso o risco ocorra, o seu impacto. Essa combinação permite determinar o potencial de cada risco em influenciar os resultados do projeto. A probabilidade determina a dimensão da incerteza e o impacto, o efeito sobre os objetivos do projeto.

No início deste módulo, definimos três eventos, a título de exemplo, no projeto de uma viagem ao exterior. Vamos agora aplicar a Análise Qualitativa de Riscos nesses eventos.

PROBABILIDADES
Temos que definir as probabilidades que serão adotadas:

Grande chance de ocorrer

0,95

Provavelmente ocorrerá

0,75

Igual chance de ocorrer ou não

0,50

Baixa chance de ocorrer

0,25

Pouca chance de ocorrer

0,10

 Atenção! Para visualização completa da tabela utilize a rolagem horizontal
GRAUS DE IMPACTO
Definir os graus de impacto:

Grau de impacto

Peso

Muito grande

5

Grande

4

Moderado

3

Pequeno

2

Muito pequeno

1

 Atenção! Para visualização completa da tabela utilize a rolagem horizontal
APLICAÇÃO
Podemos, então, aplicar os valores a cada evento:

Evento

Probabilidade

Impacto

Probabilidade x Impacto

1) Ocorrência de um problema de saúde, por causa de um acidente ou ter contraído alguma doença

0,75

5

3,75

1) Cancelamento da passagem pela companhia aérea

0,50

3

1,5

3) A quantidade de dólar adquirida não ser suficiente

0,50

4

2,0

 Atenção! Para visualização completa da tabela utilize a rolagem horizontal
Temos agora prioridades! De acordo com a tabela, o evento mais crítico está relacionado com a saúde, em seguida, com a quantidade de dólar e, finalmente, com a passagem.

 SAIBA MAIS
A Força Aérea Americana determina em seus projetos de software os seguintes componentes de risco: desempenho, custo, suporte e cronograma. As categorias de impacto incluem: catastrófico, crítico, marginal e negligenciável.

Você pode questionar: como determino a probabilidade e o impacto, valores que agregam incertezas? Lembre-se de que a área de conhecimento Gerenciamento de Risco do Projeto requer, como as demais áreas, especialistas na respectiva área. Os profissionais que trabalham com risco têm a expertise necessária no trato desses números que representam incertezas, principalmente, por experiências em projetos passados semelhantes.

O gerente de projetos é um integrador de conhecimentos e não precisa ter expertise em todas as áreas de conhecimento, mas tem que entender bem dos processos aplicados nas diferentes áreas.

ANÁLISE QUANTITATIVA DOS RISCOS
A Análise Quantitativa dos Riscos é um processo de analisar numericamente os efeitos dos riscos priorizados pela Análise Qualitativa de Riscos, pois estes podem gerar impacto potencial e substancial nos resultados do projeto.

As técnicas aplicadas incluem simulações, árvore de decisão entre outras. No contexto da Engenharia de Software, podemos aplicar a árvore de decisão, a fim de avaliar (1) a contratação de uma fábrica de software para desenvolvimento de um determinado software ou (2) realizar o desenvolvimento na empresa.

Vamos agora dar continuidade ao nosso pequeno exemplo. A tabela a seguir, considerando a simplicidade do cenário adotado, ilustra o resultado da análise quantitativa:

Prioridade

Evento

Custo (R$)

1

Ocorrência de um problema de saúde, por causa de um acidente ou ter contraído alguma doença

10.000,00

2

A quantidade de dólar adquirida não ser suficiente

1.000,00

3

Cancelamento da passagem pela companhia aérea

3.000,00

 Atenção! Para visualização completa da tabela utilize a rolagem horizontal
PLANEJAMENTO DE RESPOSTAS AOS RISCOS
O processo Planejar Respostas aos Riscos inclui o planejamento de ações para o aumento das oportunidades e redução das ameaças aos objetivos do projeto, gerenciando os riscos de acordo com sua prioridade. As referidas ações são representadas pelas respostas adequadas a cada risco, podendo ser incluído o tratamento a ser aplicado, por exemplo, mitigação, quando se busca reduzir o impacto no resultado do projeto, ou eliminação, uma resposta que elimine o referido impacto.

Retornando ao nosso pequeno exemplo, temos uma proposta de respostas aos riscos identificados na tabela a seguir:

Prioridade

Evento

Tratamento

Resposta

1

Ocorrência de um problema de saúde, por causa de um acidente ou ter contraído alguma doença

Eliminação

Contratar o seguro viagem

2

A quantidade de dólar adquirida não ser suficiente

Eliminação

Atualizar o cartão de crédito para uso internacional

3

Cancelamento da passagem pela companhia aérea

Mitigação

Confirmar a reserva em companhia aérea com boas alternativas de voos

 Atenção! Para visualização completa da tabela utilize a rolagem horizontal

Assista agora ao vídeo sobre o Processo de gerenciamento de riscos na etapa de planejamento.


RESUMINDO
Neste módulo, podemos destacar a importância da área de conhecimento Gerenciamento dos Riscos do Projeto. Um risco é um evento ou condição incerta que, se ocorrer, provocará um efeito positivo ou negativo em um ou mais objetivos do projeto.

A identificação dos riscos pode ser facilitada pela definição de uma Estrutura Analítica de Riscos (EAR), pois essa permite a categorização dos riscos.

Definidos os riscos, surge a necessidade de priorização destes, pois a tratativa dos riscos poderá impactar o orçamento final do projeto. O processo de análise qualitativa permite a referida priorização definindo para cada risco a sua probabilidade de ocorrência e o grau de impacto, caso ocorra, nos resultados do projeto. Obtidos os dois valores numéricos, pode-se então priorizar os riscos.

Priorizados os riscos, o próximo processo inclui a realização da análise quantitativa dos riscos, permitindo, de acordo com a priorização realizada anteriormente, quantificar os impactos sobre os custos do projeto em função dos riscos.

O planejamento tem como último processo a elaboração do Planejamento de Respostas aos Riscos, incluindo as ações que irão realizar as tratativas que permitirão eliminar ou mitigar os impactos nos resultados do projeto. O referido plano é colocado em execução por meio do processo Implementar Respostas aos Riscos e devidamente monitorado pelo processo Monitorar os Riscos (veja figura 15).

O projeto de software possui características que necessitam das melhores práticas de gerenciamento de riscos contidas no PMBOK, com destaque para as atualizações constantes das tecnologias e a alta volatilidade dos requisitos durante o projeto.

Lembre-se, analise os riscos do seu projeto.


A Análise qualitativa dos riscos permite definir, para cada risco identificado, uma probabilidade e um grau de impacto, o que permite priorizar os riscos em função de seu efeito sobre os resultados do projeto.

CONCLUSÃO
CONSIDERAÇÕES FINAIS
Apresentamos os principais conceitos da Engenharia de Software relacionados com processo de desenvolvimento de software e Gerenciamento de Projetos.

O processo de desenvolvimento de software permite identificar as atividades que permitem a geração do produto software. Embora existam diferentes modelos de processos, destacamos as atividades típicas ou genéricas que compõem os referidos processos, cujo entendimento permite ao engenheiro de software compreender os possíveis modelos a serem adotados em um determinado projeto de software.

O Gerenciamento de Projetos tem foco na gestão durante o desenvolvimento de software, diferentemente do processo de software, que determina as atividades técnicas. Ele define as atividades de gestão relacionadas à iniciação, ao planejamento, à execução, ao monitoramento e controle e ao encerramento do projeto. Nesse contexto, destacamos o gerenciamento de risco.
