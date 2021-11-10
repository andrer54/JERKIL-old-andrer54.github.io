MÓDULO 3
Demonstrar o consumo de Web Services através do protocolo REST utilizando Java

Neste módulo, configuraremos dois novos projetos Java: Um provedor de Web Service REST e um Cliente para consumir seus serviços.

ESTRUTURA DA APLICAÇÃO
As arquiteturas dos projetos podem ser vistas a seguir:

Provedor REST
DisciplinasWS_REST (Projeto Java do tipo Web Application)
Servidor: GlassFish
Cliente REST
DisciplinasWS_REST_Cliente (Projeto Java do tipo Web Application)
Servidor: GlassFish
Banco de Dados Java DB
disciplina (banco de dados do tipo Java DB)
tema (tabela de dados – Java DB)
modulo (tabela de dados – Java DB)
ESTRUTURA DO BANCO DE DADOS
Os detalhes/passos para criação de um banco de dados do tipo Java DB não serão abordados aqui – a criação é bem simples:

Acesse a janela “Services” na IDE, ao lado da janela “Projects”, e expanda o nó “Databases”.


Figura 10: Estrutura da tabela “tema”. Fonte: O Autor
A seguir, basta criar o database e as tabelas. Na sequência, podemos ver a estrutura das duas tabelas que utilizaremos em nosso projeto:


Figura 11: Estrutura da tabela “módulo”. Fonte: O Autor
Após criar a estrutura do database, insira alguns valores nas tabelas. O código a seguir contém uma sugestão de valores, com base nos dados usados anteriormente.

INSERT INTO TEMA(TEMA_ID, TEMA_NOME) VALUES(1, 'Programacao Servidor com Java');
INSERT INTO TEMA(TEMA_ID, TEMA_NOME) VALUES(2, 'JPA e JEE');
INSERT INTO TEMA(TEMA_ID, TEMA_NOME) VALUES(3, 'Webservices');

INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(1, 'Webserver Tomcat', 1);
INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(2, 'App Server GlassFish', 1);
INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(3, 'Servlet e JSP', 1);

INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(4, 'Tecnologia JPA', 2);
INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(5, 'Entrepise Java Beans', 2);
INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(6, 'Arquitetura MVC', 2);

INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(7, 'Conceitos Web Services', 3);
INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(8, 'Utilizando SOAP em Java', 3);
INSERT INTO MODULO(MODULO_ID, MODULO_NOME, TEMA_ID) VALUES(9, 'Utilizando REST em Java', 3);
PROVEDOR REST
A primeira aplicação que criaremos será o provedor REST. Tal aplicação será uma aplicação do tipo “Web Application”. Seguindo o passo a passo para criação de aplicações, visto anteriormente, crie uma nova aplicação e dê o nome de “DisciplinasWS_REST”.

CRIAÇÃO DO WEB SERVICE
Para criar o Web Service, clique com o botão direito sobre a raiz do projeto, a seguir clique em “New > RESTful Web Services from Database”. Na janela de configuração, selecione, no campo “Database Connection”, a conexão referente ao database criada anteriormente (disciplina). Após selecionar a conexão, serão exibidas, abaixo, as tabelas do database. Selecione ambas e clique em “Add”. A seguir, clique em “Next”.

Na janela seguinte, configuraremos as Classes de Entidade. No campo “package” adicione, ao final do valor existente, o valor “.entities”. Veja a nossa tela como ficou:


Figura 12: Configuração das Classes de Entidade. Fonte: O Autor
Clique em “Next”. A seguir, clique em “Finish”.

Nesse ponto, temos nosso provedor WS pronto para ser consumido.

CLIENTE REST
O nosso Cliente também será uma aplicação do tipo Web Application. Dê a ela o nome de “DisciplinasWS_REST_Cliente”.

Após a criação do Cliente, chegou a hora de linkarmos o cliente ao provedor.

Para isso, expanda os nós do projeto Provedor (DisciplinasWS_REST), clique com o botão direito do mouse sobre o nó “RESTful Web Services” e, a seguir, na opção “Test RESTful Web Services”.

Na janela seguinte, marque a opção “Web Test Client in Project” e, a seguir, em “Browse”. Na lista de projetos, clique em nosso Cliente – DisciplinasWS_REST_Cliente e em “Ok”. A seguir, clique em “Ok” novamente.

Após os passos acima, o projeto será atualizado. Antes de continuarmos, compile e faça o deploy tanto do provedor quanto do cliente. Para isso: Botão direito do mouse na raiz do projeto, execute o “Run”.

TESTANDO O WEB SERVICE REST
Para testar os Web Services a partir do cliente, digite no navegador:

http://localhost:8080/DisciplinasWS_REST_Cliente/test-services.html

DICA
O arquivo “test-services.html” foi criado dentro da pasta “Web Pages”, do projeto Cliente, ao longo do processo de amarração entre as aplicações, realizado na etapa anterior. Veja que além dele foi criado também o arquivo “test-services.js”.

Na página aberta, veja que, à esquerda, estão as entidades criadas. Expandindo o nó de cada uma, é possível ver alguns métodos criados por default. No tema, clique sobre a opção {id}. Agora, do lado direito, no input com o título ‘id’, digite 1 e clique em “Test”. Na janela abaixo, clique na aba “Raw View” e veja o retorno do método: Os dados relativos ao tema com id igual a 1 no formato JSON.

A figura abaixo mostra a página “test-services.html” e o resultado da chamada ao método {id}:


Figura 13: Página de testes do Web Service. Fonte: O Autor
 SAIBA MAIS
Caso você tenha problemas em testar o Web Service, como erros informando não ter sido possível encontrar uma das tabelas de nosso projeto, configure, no GlassFish, um pool de conexões (JDBC Connection Pools) e um recurso JDBC (JDBC Resources). A seguir, modifique o arquivo “persistence.xml”, na aplicação Provedor (DisciplinasWS_REST), pasta “Other Sources/src/main/resources/META-INF/” e adicione a linha “<jta-data-source>NOME-DO-JDBC-RESOURCE-CRIADO</jta-data-source>”, dentro do nó “<persistence-unit name="my_persistence_unit">”.

INCLUINDO UM NOVO RECURSO
Para finalizar nosso projeto, vamos adicionar um novo recurso no Provedor: Um método para recuperar os módulos de acordo com o tema. Para isso, na aplicação Provedor (DisciplinasWS_REST), abra a classe “ModuloFacadeREST.java” (dentro da pasta “Source Packages”). Insira o método abaixo nessa classe:

/*
* Metodo para recuperar as informações do módulo conforme o tema_id informado
*/
@GET
@Path("/tema/{tema_id}") //Define a URI do recurso
@Produces({MediaType.APPLICATION_XML, MediaType.APPLICATION_JSON})
public List<Modulo> findByTemaId(@PathParam("tema_id") Integer tema_id) {
	//Cria uma query selecionando os dados do modulo de acordo com o tema_id informado
	return em.createQuery(
	"SELECT m.moduloId, m.moduloNome, m.temaId FROM Modulo m WHERE m.temaId = :temaId")
	.setParameter("temaId", tema_id)
	.getResultList();
}
Algumas observações sobre o código acima:

@GET: Define o método HTTP através do qual o recurso estará disponível (aproveite que está com essa classe aberta e veja os demais métodos nela existentes).
@Path: Define a URI do recurso.
@Produces: Define os formatos de retorno de dados. Nesse caso, XML ou JSON.
 Atenção! Para visualizaçãocompleta da tabela utilize a rolagem horizontal
Após compilar e fazer o deploy do projeto, atualize a página de testes do Web Service:

http://localhost:8080/DisciplinasWS_REST_Cliente/test-services.html

Perceba que o recurso que criamos agora está disponível sob a árvore de recursos referentes ao Módulo. Expanda a árvore e clique no recurso “tema/{tema_id}. Insira 1 no campo “tema_id” e clique em “Test”. Veja na aba “Raw View” os dados referentes ao Módulo com tema_id igual a 1, em formato JSON.

COMENTÁRIO
Nesse ponto, chegamos ao final da implantação do provedor e do cliente para fornecer e consumir Web Services no formato REST. Para encerrar, seguem algumas últimas observações:

Embora tenhamos usado alguns recursos facilitadores da IDE na criação de nossos projetos, os códigos gerados são totalmente funcionais e facilmente adaptáveis.
Abra as páginas web e as classes Java geradas ao longo de nossos projetos e analise os códigos. Procure entender os códigos de acordo com as regras que definimos ao longo das explanações.
PRÓXIMOS PASSOS
Para aprimorar nossa aplicação, fica como uma atividade futura a construção de um formulário ou página web, no Cliente REST, para consumir e utilizar os dados provenientes do Provedor REST.


CONSTRUINDO UMA PÁGINA WEB PARA CONSUMO DE DADOS PROVENIENTES DE UM WEB SERVICE REST

OS WEB SERVICES E O “MUNDO REAL”
As aplicações para fornecimento e consumo de Web Services, tanto SOAP quanto REST, que criamos ao longo deste tema, são aplicações compostas por códigos funcionais, que utilizam diversos recursos da linguagem Java e que podem ser facilmente adaptados para utilização em projetos, tanto voltados para fins de estudo quanto para fins profissionais, em aplicações reais.

Com base nessa premissa, discutiremos, a partir de agora, em que situações, no dia a dia, podemos fazer uso de Web Services. Nesse sentido, veremos alguns casos de uso mais simples – e que você poderá utilizar caso esteja iniciando na área de desenvolvimento – e outros mais avançados – para você que já tem alguma experiência no desenvolvimento de aplicações. Para começar, recapitulemos alguns conceitos já vistos. A seguir, discutiremos os casos de uso em si.

RECAPITULANDO CONCEITOS
WEB SERVICES
Um Web Service é um aplicativo projetado para suportar interoperabilidade entre máquinas através de uma rede (W3C, 2004). Logo, os Web Services são agentes de software cuja função é trocar mensagens, possuindo, para tal, um conjunto de funcionalidades definidas.

Partindo dessa definição, podemos ver que as aplicações que criamos atendem às funcionalidades nelas mencionadas, ou seja, trata-se de aplicações, agentes de software, com a função de disponibilizar serviços – os Provedores SOAP e REST – e consumir serviços – os Clientes SOAP e REST.

SOFTWARE
Quando falamos de aplicações, estamos falando de softwares. Em relação a estes, os mesmos podem ser categorizados em alguns tipos, como:

Software de sistema.
Software de aplicação.
Software científico e de engenharia.
Software embutido.
Software para linhas de produtos.
Software para Web.
Software de inteligência artificial.
Outros.
COMENTÁRIO
Dentre essas categorias, cabe ressaltar a definição para o Software de Aplicação: Segundo Pressman (2106), são programas desenvolvidos para execução em um negócio específico ou em uma empresa específica. Essa definição cabe bem dentro das aplicações que desenvolvemos, uma vez que abordamos um tema específico, voltado para a área acadêmica, no qual manuseamos algumas Classes como “Tema” e “Módulos”, naturais do negócio em questão.

API
Uma Interface de Programação de Aplicação (API, acrônimo para Application Programming Interface) segundo Jacobson (2012), é uma maneira de duas aplicações de computador se comunicarem, uma com a outra, em uma rede (predominantemente a Internet) usando uma linguagem comum entendida por ambas. As APIs seguem uma especificação e isso implica que:

O provedor da API descreve exatamente qual funcionalidade a API oferecerá.
O provedor da API descreve quando e como a funcionalidade estará disponível.
O provedor da API pode estabelecer restrições técnicas, legais ou comerciais, como limites de utilização, entre outras.
Há um contrato estabelecido entre o provedor da API e quem dela faz uso, ficando o último comprometido a seguir as regras de uso estabelecidas pelo provedor.
UNINDO CONCEITOS
Os três conceitos apresentados acima são de suma importância para abordarmos o uso de Web Services no mundo real, uma vez que se trata de conceitos intrinsecamente relacionados, como podemos perceber nas suas respectivas definições. Logo, é comum, no dia a dia, confundirmos os conceitos de Web Services e APIs, por exemplo. Frente a isso, cabe destacar algumas de suas diferenças:

Podemos dizer que todos os Web Services são APIs, mas nem todas APIs são Web Services.
Uma API pode usar outras formas de comunicação, além das utilizadas pelos Web Services (SOAP, REST e XML-RPC).
Uma API, diferentemente do Web Service, não precisa de uma rede para funcionar.
UTILIZANDO WEB SERVICES NO MUNDO REAL
Tomando como base as aplicações que criamos anteriormente, podemos pensar em algumas formas de como utilizá-las no mundo real. Por exemplo: Poderíamos ter um website que exibisse informações sobre os cursos oferecidos por uma instituição de ensino. Nesse site, dentre as funcionalidades disponíveis, poderia haver uma para listar todos os cursos e respectivas disciplinas, assim como o conteúdo de cada uma delas.

ATENÇÃO
Nesse caso, poderíamos consumir o Web Service desenvolvido (em SOAP ou REST) tanto a partir do “server side” – carregando as informações no carregamento da página – quanto a partir do “client side” – a partir de formulários de pesquisa e filtro de resultados carregando informações através de AJAX.

Considerando o exemplo acima, você poderia questionar o porquê de utilizarmos Web Services para exibir o conteúdo em questão, uma vez que poderíamos utilizar outras técnicas, como consultas diretas ao Banco de Dados ou até mesmo páginas estáticas, sem o uso de Web Services.


Fonte: VLADGRIN/Shutterstock
Figura 14: Consumo de Web Services utilizando linguagens Server Side.
Nesse caso, a justificativa para a utilização de Web Services está em podermos disponibilizar o conteúdo em questão para outras aplicações além do website. Através deles poderíamos alimentar um aplicativo Mobile, assim como fornecer informações para um sistema de terceiros – um Portal que reúna informações dos cursos de diversas instituições de ensino, por exemplo. Logo, a escolha por uma arquitetura baseada em Web Services deve levar esses fatores em conta.

Imaginando agora outra situação real e um pouco mais avançada, na qual se aplique a utilização de Web Services, temos a Arquitetura de Microsserviços, uma abordagem de desenvolvimento de softwares que prega a decomposição de aplicações em uma gama de serviços – serviços esses disponibilizados através de uma interface de APIs.

Em comparação com a abordagem tradicional de desenvolvimento de aplicações, normalmente monolíticas, ou seja, todos os módulos e funcionalidades fazem parte de um bloco único, a abordagem baseada em microsserviços prega que as aplicações sejam desmembradas em componentes mínimos e independentes que, embora separados, trabalhem juntos para realizarem as mesmas tarefas. Entre as vantagens da abordagem baseada em microsserviços, temos:

Capacidade de compartilhamento de processos e funções semelhantes entre várias aplicações.
Escalabilidade: Maior flexibilidade para acréscimo de novas funcionalidades.
Disponibilidade: Com a aplicação não sendo formada por um único bloco, diminui o risco de indisponibilidade total da mesma.
Além das vantagens acima, e agora com foco no processo de desenvolvimento, há outras vantagens como:

Mais facilidade na criação de testes unitários.
Maior frequência de deploy e facilidade para implementação da entrega contínua.
Otimização no monitoramento e identificação de erros.
Outras.
EXEMPLOS DE APIS COMUMENTE UTILIZADAS
Abaixo, são listados alguns exemplos de APIs comumente utilizadas nas mais diversas aplicações no dia a dia:

APIS DE PAGAMENTO
Serviços que fornecem diversos meios de pagamento e contemplam toda a segurança relacionada a esse processo, além de também oferecerem serviços extras como identificação de fraudes, entre outros.

APIS DE REDES SOCIAIS
A maioria das redes sociais fornecem APIs públicas que permitem tanto o consumo de suas informações como a realização de outras ações: Login utilizando as credenciais da rede social; realizar publicações e compartilhamentos; etc.

APIS DE LOCALIZAÇÃO
Um bom exemplo dessas APIs é o Google Maps.

OUTROS EXEMPLOS
Consulta de CEP; consulta de previsão de tempo; conversão de moedas; serviços de câmbio; serviços de plataformas de e-commerce; chatbots; etc.

VERIFICANDO O APRENDIZADO
1. SOBRE A ARQUITETURA DO PROVEDOR E CLIENTE REST ESTUDADA, SELECIONE A ALTERNATIVA CORRETA:
A arquitetura estudada é uma, entre muitas, possíveis de serem aplicadas para a criação de provedores e clientes de Web Services REST.

A especificação REST determina que a arquitetura do Provedor REST utilize, obrigatoriamente, dados provenientes de um banco Java DB.

O consumo de serviços REST, em Java, é restrito a aplicações do tipo Web.

O servidor GlassFish é o servidor indicado pela especificação REST para armazenar tanto o Provedor quanto o Cliente REST.

Como REST é uma arquitetura simples, que preza pela leveza, não é possível consumir dados complexos, dados que estejam, por exemplo, armazenados em mais de duas diferentes tabelas de bancos de dados.

2. ESTUDAMOS A SINTAXE, A ANATOMIA DE SERVIÇOS ESCRITOS E CONSUMIDOR NA ARQUITETURA REST. NESSE CONTEXTO, SELECIONE A AFIRMATIVA CORRETA:
Um recurso, ou método, consumível na arquitetura REST é identificado pela sua URI, ou seja, pelo endereço do recurso, onde informamos o nome do método e os seus parâmetros, quando necessários.

Os serviços disponíveis em uma arquitetura REST são caracterizados por possuírem uma única URI de acesso comum.

Por ser uma arquitetura mais simples, quando comparada, por exemplo, ao SOAP, é possível, ao utilizarmos REST, definirmos novos métodos no lado cliente, mesmo que esses não existam no provedor.

A única limitação existente na arquitetura REST é a que obriga que todos os métodos disponíveis utilizem o mesmo protocolo HTTP.

A arquitetura REST permite que novos protocolos de transmissão, diferentes dos fornecidos pelo protocolo HTTP, sejam criados no provedor e utilizados pelo cliente na transmissão dos dados das aplicações.

GABARITO
1. Sobre a arquitetura do Provedor e Cliente REST estudada, selecione a alternativa correta:

A alternativa "A " está correta.


Não existe uma arquitetura padrão, em termos de linguagem de programação e seus recursos específicos, definida pela especificação REST para o fornecimento e consumo de Web Services REST.

2. Estudamos a sintaxe, a anatomia de serviços escritos e consumidor na arquitetura REST. Nesse contexto, selecione a afirmativa correta:

A alternativa "A " está correta.


Um serviço REST pode conter inúmeros métodos, cada um com sua própria URI. Além disso, é possível utilizar diferentes métodos HTTP nos diferentes métodos existentes.

CONCLUSÃO
CONSIDERAÇÕES FINAIS
Ao longo deste tema, foram descritos os conceitos teóricos relativos aos Web Services e, especificamente, ao protocolo SOAP e à arquitetura REST. Além disso, tais conceitos foram aplicados, de forma prática, na construção de aplicações provedoras e consumidoras (clientes) de serviços nas tecnologias em questão, permitindo, assim, ao aluno empregar o conhecimento adquirido. Ao final, discorremos sobre a aplicabilidade de Web Services como agentes de software em cenários do “mundo real”.


AVALIAÇÃO DO TEMA:
REFERÊNCIAS
JACOBSON, D.; BRAIL, G.; WOODS, D. APIs: A Strategy Guide. California: O’Reilly, 2012.

KALIN, M. Java Web Services: Up and Running. 2nd. ed. California: O’Reilly, 2013.

PRESSMAN, R.; MAXIM, B. Engenharia de Software: Uma abordagem profissional. Porto Alegre: McGraw-Hill – Artmed, 2016.

W3C. W3C Working Group Note 11. In: W3C ‒ Web Services Architecture. Publicado em meio eletrônico em: fev. 2014.

