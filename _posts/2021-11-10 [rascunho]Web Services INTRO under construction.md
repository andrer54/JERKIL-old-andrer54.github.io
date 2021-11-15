Vamos bater um papo sobre os conceitos relacionados a Web Services,  
como SOA (Arquitetura Orientada a Serviços),  
SOAP (Protocolo Simples de Acesso a Objetos)  
e REST (Transferência Representacional de Estado),  
demonstrando o fornecimento e consumo de Web Services SOAP e REST  
utilizando a linguagem de programação Java.


Quando falamos de SOA, estamos falando de um padrão de arquitetura de software,  
baseado nos princípios da computação distribuída,  
onde as funcionalidades existentes no software  
devem estar disponíveis no formato de serviços.


Temos, então, o SOAP e o REST, que são duas diferentes abordagens que permitem a transmissão de dados nos Web Services.

-----

No início da computação distribuída,  
a comunicação entre cliente e servidor era restrita a uma rede interna,  
ficando o servidor responsável por efetuar todo o processamento.


Posteriormente, esse processamento passou a ser feito entre vários servidores,   
onde era comum a utilização de middlewares como CORBA, DCOM e RMI,   
sendo tais middlewares responsáveis por prover a comunicação nos sistemas distribuídos.


Mais recentemente, as aplicações cliente x servidor migraram para a Internet,  
dando origem então aos Web Services, que surgiram como  
uma extensão dos conceitos de chamada remota de métodos,    
presentes nos middlewares já mencionados, para a Web. Logo, podemos dizer que os Web Services  
são aplicações distribuídas que se comunicam por meio de mensagens.    
Ou, usando outras palavras, um Web Service é uma interface que descreve uma coleção de operações 
acessíveis pela rede através de mensagens.   
Nesse sentido, temos transações e regras de negócio de uma aplicação expostas através de protocolos acessíveis e 
compreensíveis por outras aplicações – podendo essas ser escritas em qualquer linguagem de programação, além de residirem 
em qualquer sistema operacional.



--para não ficar muito longo esse post, eu vou fazer a parte 2 começando por
"OS WEB SERVICES E EUS ARQUITETURA"
OS WEB SERVICES E SUA ARQUITETURA
A arquitetura dos Web Services é baseada em três componentes:

Provedor de serviços;
Consumidor de serviços;
Registro dos serviços.
Vamos conhecer um pouco mais sobre cada um desses componentes.

* PROVEDOR DE SERVIÇOS
O primeiro componente, o provedor de serviços, é responsável pela criação e descrição do Web Service – em um formato padrão, compreensível para quem precise utilizar o serviço ‒ assim como pela sua disponibilização a fim de que possa ser utilizado.

* CONSUMIDOR DE SERVIÇOS
Esse componente, ou papel, é representado por quem utiliza um Web Service disponibilizado em um provedor de serviços.

*REGISTRO DOS SERVIÇOS
Trata-se de um repositório a partir do qual o provedor de serviços pode disponibilizar seus Web Services e no qual o consumidor de serviços pode utilizá-los. Em termos técnicos, o registro dos serviços contém informações, como os detalhes da empresa, os serviços por ela oferecidos e a descrição técnica dos Web Services.

-------

OUTROS ELEMENTOS DA ARQUITETURA DOS WEB SERVICES
Conforme pode ser visto na Figura 1, além dos elementos já apresentados, há ainda outros que compõem a arquitetura dos Web Services, como a WSDL, o SOAP, assim como a XML e a UDDI. A seguir, conheceremos um pouco mais sobre as tecnologias WSDL e UDDI. Já o SOAP será visto mais adiante, com o REST, em tópicos específicos.


*WSDL
A WSDL (Web Services Description Language) é uma linguagem baseada em XML, cuja função é descrever, de forma automatizada, os serviços do Web Service através de um documento acessível aos clientes que desejam fazer uso do Web Service. A WSDL é responsável por fornecer as informações necessárias para utilização de um Web Service, como as operações disponíveis e suas assinaturas.

*UDDI
A UDDI (Universal Description, Discovery and Integration) é responsável por prover um mecanismo para a descoberta e publicação de Web Services. Nesse sentido, a UDDI contém informações categorizadas sobre as funcionalidades e serviços disponíveis no Web Service, permitindo, ainda, a associação de informações técnicas, normalmente definidas com o uso da WSDL, a esses serviços.


--------------

* SOAP E REST
Conforme mencionado anteriormente, inicialmente, no contexto da computação distribuída, eram utilizadas tecnologias como RMI, DCOM e CORBA para a integração de aplicações. Nesse cenário, tais tecnologias obtiveram sucesso quando aplicadas em ambientes de rede locais e homogêneos. Posteriormente, já no ambiente heterogêneo da Internet, outras soluções foram aplicadas através da construção de aplicações web escritas em linguagens como ASP, PHP e Java (JSP). Tais aplicações, em termos de integração com outras aplicações, faziam uso de XML.

Embora a XML seja um formato de transmissão de dados padronizado, faltava padronização por parte das empresas em termos de desenvolvimento, utilização de protocolos, transações, segurança etc. Frente a isso, o W3C desenvolveu um padrão cujo principal objetivo era prover a interoperabilidade entre aplicações. Tal padrão recebeu o nome de “Padrões WS-*” e é constituído por especificações para criação de Web Services baseados no protocolo SOAP.


O REST, diferentemente do SOAP, não é uma especificação e nem foi criado pelo W3C. Em linhas gerais, trata-se de uma forma alternativa, uma arquitetura web, para o consumo de Web Services e que se baseia na utilização de recursos oferecidos pelo HTTP.

Veremos mais sobre SOAP e REST a seguir.
------------------

* SOAP
O SOAP é um protocolo, baseado em definições XML, utilizado para a troca de informações/comunicação em ambiente distribuído. Tal protocolo encapsula as chamadas e os retornos a métodos Web Services, trabalhando, principalmente, sobre o protocolo HTTP. Com o uso de SOAP, é possível invocar aplicações remotas utilizando RPC ou troca de mensagens, sendo indiferente o sistema operacional, a plataforma ou a linguagem de programação das aplicações envolvidas.

** Comunicação em SOAP
Web Services que fazem uso do protocolo SOAP podem utilizar dois modelos distintos de comunicação:

> RPC
Nesse modelo, é possível modelar chamadas de métodos com parâmetros, assim como receber valores de retorno. Com ele, o corpo (body) da mensagem SOAP contém o nome do método a ser executado e os parâmetros. Já a mensagem de resposta contém um valor de retorno ou de falha.

>Document
Nesse modelo, o body contém um fragmento XML que é enviado ao serviço requisitado, no lugar do conjunto de valores e parâmetros presente no RPC.

* Formato de mensagem
Uma mensagem SOAP é composta por três elementos:
>ENVELOPE
Elemento principal (raiz do documento) do XML, responsável por definir o conteúdo da mensagem. É um elemento obrigatório.
>HEADER
Mecanismo genérico que torna possível a adição de características, de informações adicionais, à mensagem. É um elemento opcional, mas que, quando utilizado, deve ser o primeiro elemento do Envelope.
>BODY
Corpo da mensagem. Contém a informação a ser transportada. Assim como o Envelope, é um elemento obrigatório.

    <SOAP-ENV:envelope>

      <SOAP-ENV:header>
      </SOAP-ENV:header>

      <SOAP-ENV:body>

        <SOAP-ENV:fault>
        </SOAP-ENV:fault>

      </SOAP-ENV:body>

    </SOAP-ENV:envelope>


>Exemplo de requisição e resposta utilizando SOAP
Para melhor compreensão, veremos a seguir um exemplo prático de requisição e resposta de Web Service utilizando o protocolo SOAP. Nesse exemplo, será invocado o método “GetModulosTema”. Tal método recebe como parâmetro o nome do tema, representado pela variável “TemaNome”. Como resposta, são retornados os nomes dos módulos relacionados ao tema informado. O XML contendo o envelope da requisição pode ser visto no código abaixo:


      <?xml version="1.0"?>
      <soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope">
        <soap:Header>
        </soap:Header>
        <soap:Body>
          <GetModulosTema>
            <TemaNome>Webservices<TemaNome>
          </GetModulosTema>
        </soap:Body>
      </soap:Envelope>
      
A seguir, é demonstrado o XML do envelope contendo a resposta do método invocado.


      <?xml version="1.0"?>
      <soap:Envelope
       xmlns:soap="http://www.w3.org/2003/05/soap-envelope/"
       soap:encodingStyle="http://www.w3.org/2003/05/soap-encoding">

        <soap:Body>
          <GetModulosTemaResponse>
            <Modulos>
              <Modulo>
                <Nome>SOAP e REST</Nome>
              </Modulo>
              <Modulo>
                <Nome>Utilização de SOAP XML em JAVA</Nome>
              </Modulo>
              <Modulo>
                <Nome>Utilização de REST JSON em JAVA</Nome>
              </Modulo>
            </Modulos>
          </GetModulosTemaResponse>
        </soap:Body>

      </soap:Envelope>

      
 REST
O REST foi proposto por Roy Fielding, um dos criadores do protocolo HTTP, em 2000, com a premissa de utilizar os recursos oferecidos pelo HTTP. Trata-se de um modelo mais simples que o SOAP, além de não ser um protocolo, mas, sim, uma arquitetura web, composta pelos seguintes elementos:

Cliente (do Web Service);
Provedor (do Web Service);
Protocolo HTTP.
Considerando os elementos acima, o consumo de um Web Service que faz uso de REST tem seu ciclo de vida iniciado com o cliente enviando uma solicitação a um determinado provedor. Tal provedor, após processar a requisição, responde ao cliente. Além disso, o HTTP é o protocolo que define o formato das mensagens enviadas e recebidas, além de também ser responsável pelo transporte dessas mensagens.



Estrutura dos recursos REST
Na arquitetura REST, os serviços ou recursos disponíveis correspondem a uma URI (Uniform Resource Identifier) específica e que também é única. Se considerarmos o exemplo visto no protocolo SOAP, podemos dizer que “GetModulosTema” é um método pertencente a um recurso – que vamos chamar de “Tema”. Logo, a URI para consumo desse serviço seria:



http://www.dominio.com.br/tema/GetModulosTema/{nome-do-tema}

Considerando então que “Tema” é o nome do recurso, podemos imaginar outros métodos disponíveis no mesmo. Poderíamos ter, por exemplo, um método para listar todos os temas; um método para inserir um novo tema; etc. Cada um desses serviços teria uma URI própria:

Listagem de todos os temas
        http://www.dominio.com.br/tema

Inserção de tema
        http://www.dominio.com.br/tema/CreateTema/{nome-do-tema}

Uma vez que os Web Services REST são baseados no protocolo HTTP, a estrutura dos recursos REST, como visto acima, provém justamente dos métodos e códigos de retorno HTTP. Isto, em termos práticos, significa dizer que devemos usar os diferentes métodos HTTP de acordo com as operações para manipulação de dados dos recursos que desejamos fazer.

Por exemplo: Para recuperar dados, como no caso onde queremos listar todos os temas existentes, devemos usar o método HTTP GET.

Abaixo, na Tabela 1, estão listados os métodos HTTP e suas funções em relação à arquitetura REST:


Método HTTP	Descrição / Para que é usado
GET	Usado na recuperação ou listagem de recursos
POST	Usado na inclusão de um recurso
PUT	Usado na edição de um recurso
DELETE	Usado na exclusão de um recurso

Como já mencionado, REST utiliza os recursos do protocolo HTTP. Logo, em relação às respostas dos serviços, temos disponíveis os códigos de retorno HTTP.

Por exemplo: Para verificarmos se um recurso foi atualizado com sucesso, devemos verificar se o código HTTP é igual a 200. Caso algum erro tenha ocorrido, teremos então o código 400 ou 404.



Exemplo de requisição e resposta utilizando REST
O consumo de um recurso REST é feito através de uma URI. Logo, poderíamos acessar tal recurso até mesmo através de um navegador web, sendo a forma mais usual, quando falamos de integração entre aplicações, implementarmos um cliente, através de uma linguagem de programação, que acesse o recurso em questão, enviando parâmetros, quando necessário, e tratando o retorno do mesmo. Nesse contexto, vamos usar o mesmo exemplo visto em SOAP e recuperar a listagem de módulos disponíveis para um determinado tema.

Para consumir o serviço, vamos utilizar a seguinte URI:

http://www.dominio.com.br/tema/GetModulosTema/Webservices


Um possível retorno para essa requisição é visto a seguir:



  
      {
        "Modulos": [{
            "Nome": "SOAP e REST"
          }, {
            "Nome": "Utilização de SOAP XML em JAVA"
          }, {
            "Nome": "Utilização de REST JSON em JAVA"
          }
        ]
      }
      
Importante
Como vimos, as informações retornadas pelo Web Service consumido estão no formato JSON. Embora não seja o único tipo de dado disponível para o transporte de informações em REST – ou melhor, em mensagens HTTP, ele é o mais utilizado nessa arquitetura.

Como curiosidade, em requisições REST podemos usar qualquer um dos tipos de conteúdo (Content-Type) abaixo:

Application/xml
Application/json
Text/plain
Text/xml
Text/html


para não ficar muito extenso, vou fazer o modulo 2 falando de webservivers, arquiteturas, sopa e rest.



------------


REFERÊNCIAS
JACOBSON, D.; BRAIL, G.; WOODS, D. APIs: A Strategy Guide. California: O’Reilly, 2012.

KALIN, M. Java Web Services: Up and Running. 2nd. ed. California: O’Reilly, 2013.

PRESSMAN, R.; MAXIM, B. Engenharia de Software: Uma abordagem profissional. Porto Alegre: McGraw-Hill – Artmed, 2016.

W3C. W3C Working Group Note 11. In: W3C ‒ Web Services Architecture. Publicado em meio eletrônico em: fev. 2014.
      
