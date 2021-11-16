
DESCRIÇÃO
Linguagem de marcação XML, serialização de dados em sistemas web, formato de transmissão de dados JSON, formato de transmissão de dados YAML, consumo de dados serializados nas requisições AJAX.

XML: eXtensible Markup Language

JSON: Javascript Object Notation

YAML: YAML Ain't Markup Language

AJAX: Asynchronous Javascript and XML

PROPÓSITO
Apresentar os conceitos de transmissão e consumo de dados em sistemas web, utilizando os formatos XML, JSON e YAML e obter o conhecimento básico necessário para o consumo de dados nesses formatos em requisições AJAX.

PREPARAÇÃO
Para aplicação dos exemplos, será necessário um editor de texto com suporte a linguagens de marcação. No Sistema Operacional Windows, é indicado o Notepad++. No Linux, o Nano Editor. Além disso, para visualização dos exemplos dos códigos que utilizam AJAX, será necessário hospedar as páginas HTML em um servidor web. No SO Windows, é indicada a instalação/utilização de softwares, como o XAMP, que consistem em um ambiente contendo, entre outros softwares, o servidor web Apache. Uma alternativa é a instalação apenas do próprio Apache ou de outro servidor, como o IIS. Em ambiente Linux, recomenda-se a utilização dos servidores Apache ou Nginx.

Vamos começar nossa jornada acessando os códigos-fontes dos exercícios propostos para o aprendizado das diferentes notações. Baixe o arquivo "Códigos-fontes dos exercícios_Tecnologias de Transmissão de Dados em Sistemas Web", descompactando-o em seu dispositivo. Assim, você poderá utilizar os códigos como material de apoio ao longo do tema!

OBJETIVOS
MÓDULO 1
Descrever a linguagem de marcação XML e sua aplicabilidade em sistemas web

MÓDULO 2
Descrever os formatos de transmissão de dados JSON e YAML

MÓDULO 3
Demonstrar como utilizar dados nos formatos XML, JSON e YAML em requisições AJAX

INTRODUÇÃO
No desenvolvimento de software, mais precisamente no que concerne às informações a serem manipuladas, lidamos, normalmente, com algumas fontes de dados: Os provenientes da própria aplicação, os provenientes de outras fontes, como outros sistemas, bases de dados externas, APIs (Application Programming Interface) etc. Em paralelo, temos ainda os processos de recuperação e armazenamento de tais informações. 

Além disso, há outro fator que deve ser levado em consideração: O formato dos dados que trataremos em nosso software, onde podemos ter dados nos mais diversos formatos e até mesmo dados não formatados. 

Ao longo deste tema, veremos três dentre os vários formatos de serialização e transmissão de dados disponíveis. Tais formatos — a linguagem de marcação XML, o JSON e o YAML — serão descritos conceitualmente. Também demonstraremos, de forma prática, como utilizar esses formatos em requisições AJAX. 

MÓDULO 1
Descrever a linguagem de marcação XML e sua aplicabilidade em sistemas web

A LINGUAGEM XML
A linguagem XML — acrônimo para eXtensible Markup Language – é, a exemplo da HTML, uma linguagem de marcação. Criada pelo W3C (World Wide Web Consortium), em 1996, e transformada em uma recomendação pelo mesmo órgão em 1998, tal linguagem possui algumas importantes diferenças em relação à HTML, visto que foi criada justamente para ser diferente desta — em outras palavras, para estender as funcionalidades da HTML.


Autor: Julian Popov / Fonte: Shutterstock
Podemos dizer que a XML é um padrão para a formatação e transmissão de dados de fácil entendimento tanto para humanos quanto para máquinas. Sua principal característica — e diferença para HTML – é ser composta por tags definidas pelo usuário (ou programador). Ou seja, diferentemente da HTML, na qual todas as tags são predefinidas, em XML nós mesmos criamos nossas tags.

VOCÊ SABIA
A principal função e utilização da XML é transmitir dados através da web.

ANATOMIA DE UM ARQUIVO XML
Os documentos XML são constituídos por unidades de armazenamento chamadas entidades, que contêm dados. Tais dados são compostos por caracteres, alguns dos quais formam dados de caracteres enquanto outros formam a marcação (W3C, 2020). 

Vejamos, a seguir, nosso primeiro arquivo XML. A partir deste arquivo simples, começaremos a entender o seu formato.

<?xml version="1.0" encoding="UTF-8" ?>
<correntistas>
<!-- Nesse documento há dados de duas 'pessoas' -->
<pessoa>
<tipo>física<</tipo>
<nome>José Maria</nome>
<numero>000.000-00</numero>
</pessoa>
<pessoa>
<tipo>jurídica</tipo>
<nome>José Maria SA</nome>
<numero>111.111-11</numero>
</pessoa>
</correntistas>
Analisando linha a linha da XML acima, temos:

Na primeira linha, a declaração XML, responsável por especificar a versão e por informar ao navegador que se trata de um arquivo XML. Nessa primeira linha, também é definido o charset do documento.
Na segunda linha, representado pela tag <correntistas>, o nó principal — ou nó raiz — do documento.
Entre a segunda e a terceira, um comentário: Repare que os comentários em um documento XML são iguais aos usados em HTML.
Na terceira linha, temos o primeiro elemento filho do nó raiz, o elemento <pessoa>.
Na quarta, quinta e sexta linhas, temos os elementos filhos do elemento <pessoa>.
Nas linhas seguintes, temos outro elemento <pessoa> e seus respectivos elementos filhos.
CHARSET
Charset é o conjunto de caracteres utilizados para escrever o documento.

Em termos de sintaxe, repare que: 

Toda tag deve ser iniciada e fechada.
Há um aninhamento representando hierarquia entre os dados. Por exemplo: As tags <tipo>, <nome> e <numero> estão indentadas, aninhadas e englobadas pela tag <pessoa>. Da mesma forma, todas as tags filhas estão aninhadas dentro do nó principal, <correntistas>; 
Veja na figura, a seguir, como o documento acima é renderizado no navegador:

RENDERIZAÇÃO
Renderização é o processo pelo qual se obtém o produto final de um processamento digital qualquer.


Figura 1 - Documento XML exibido no navegador web. Fonte: O Autor.
Considerando sua sintaxe, dizemos que XML é um documento bem formatado. Logo, deixar de fechar uma tag ou construir um documento sem tag raiz torna o arquivo mal formatado ou inválido. 

Na figura 2, pode ser visto o resultado da renderização no navegador de um documento XML mal formatado – nesse caso, foi removida a tag de fechamento do elemento <correntistas>, do documento XML visto anteriormente.


Figura 2: Renderização de XML mal formatado. Fonte: O Autor.
UTILIZANDO ATRIBUTOS
Veja este novo exemplo de documento XML:

<?xml version="1.0" encoding="UTF-8" ?>
<correntistas>
<conta agencia="0123-4">
<tipo>física</tipo>
<nome>José Maria</nome>
<numero>000.000-00</numero>
</conta>
<conta agencia="5678-9">
<tipo>jurídica</tipo>
<nome>José Maria SA</nome>
<numero>111.111-11</numero>
</conta>
</correntistas>
Agora, sua renderização no browser:


Figura 3: Exemplo de Documento XML contendo atributo. Fonte: O Autor.
Em relação ao primeiro documento XML, neste último, no elemento <conta>, foi adicionado o atributo “agencia” e um valor para esse atributo. Logo, podemos ter em um documento XML, além dos elementos, também atributos. Inclusive, poderíamos modificar o documento anterior, trocando os elementos filhos de <conta> por atributos, gerando este novo documento:

<?xml version="1.0" encoding="UTF-8" ?>
<correntistas>
<conta agencia="0123-4" tipo="fisica" nome="José Maria" numero="000.000-00" />
<conta agencia="5678-9" tipo="jurídica" nome="José Maria SA" numero="111.111-11" />
</correntistas>
Perceba que, no lugar de elementos filhos, os dados de cada conta foram armazenados diretamente no elemento <conta>, na forma de atributos. Sobre os atributos, como visto no exemplo, é necessário envolvê-los com aspas. Por último, veja que o elemento <conta> foi simplificado, sendo aberto e fechado numa única linha, com a utilização da barra antes do sinal de maior ( /> ).

Anatomia em termos Conceituais
Em termos conceituais, um arquivo XML é composto por:
1. Dados de caracteres (sequência de texto).
2. Instruções de processamento através de anotações, normalmente inseridas no cabeçalho do documento.
3. Comentários, quando necessário.
4. Declaração de entidade.
5. Nós — Elemento rotulado com um nome ou conjunto de atributos, cada um contendo nome e valor.
 Atenção! Para visualização completa da tabela utilize a rolagem horizontal
POR QUE UTILIZAR XML?
Como vimos, ao tratarmos de sistemas web, a aplicabilidade da XML é servir como formato de transmissão de dados. Nesse sentido, considerando que tal formato foi especificado para ser simples, de fácil leitura por humanos e computadores, temos a principal justificativa quanto à sua adoção em sistemas web.

Além dessa, podemos ainda mencionar as seguintes vantagens de utilização da XML: 

XML é autodocumentado, ou seja, seu formato descreve sua estrutura, elementos e valores.
XML é independente de plataforma e linguagem de programação.
XML é facilmente interpretado pela maioria das linguagens de programação (nas quais normalmente utilizamos recursos chamados de “parsers”, responsáveis por interpretar a estrutura e dados do documento).
XML é extensível. Logo, podemos tanto usar entidades criadas por outros, quanto criar nossas próprias tags e atributos.
XML possui suporte a Unicode.
XML possui suporte à validação através de DTD e Schema.
UNICODE
Unicode é um padrão internacional que permite que todos os caracteres, de qualquer sistema de escrita existente, possam ser entendidos e manipulados por computadores.

DTD
Document Type Definition

SCHEMA
Estrutura pré-definida com regras de validação de um documento

Convém também citar algumas desvantagens desse formato, para a transmissão de dados através da Internet, em relação a outros disponíveis: 

A sintaxe XML é detalhada e redundante quando comparada a outros formatos baseados em texto, como JSON.
XML não suporta arrays.
Um documento XML é menos legível que outros formatos como JSON e YAML.
XML pode gerar arquivos grandes dada a sua sintaxe detalhada.
MANIPULANDO UM ARQUIVO XML COM A INTERFACE DOM
O DOM (Document Object Model) é uma interface de plataforma e linguagem neutra que permite que programas e scripts acessem e atualizem dinamicamente o conteúdo, a estrutura e o estilo de um documento. (W3C, 2020). 

Utilizando a interface DOM, é possível manipular tanto documentos HTML quanto documentos XML. Em ambos, o documento, através desse objeto, é representado na forma de árvore.

XML DOM
O XML DOM é um padrão para obter, modificar, adicionar ou remover elementos XML. Através dele, é possível acessar todos os elementos de um documento XML. Utilizando o documento XML apresentado anteriormente, e novamente disponibilizado a seguir, veja o código no qual, utilizando Javascript, o arquivo em questão é manipulado.

PASSO 01
PASSO 02
<?xml version="1.0" encoding="UTF-8" ?>
<correntistas>
<conta agencia="0123-4">
<tipo>física</tipo>
<nome>José Maria</nome>
<numero>000.000-00</numero>
</conta>
<conta agencia="5678-9">
<tipo>jurídica</tipo>
<nome>José Maria SA</nome>
<numero>111.111-11</numero>
</conta>
</correntistas>

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
</head>
<body>
<p id="result"></p>
<script type="text/javascript">

//Cria o XML visto no código acima no formato de string JS
var xmlString = '<?xml version="1.0" encoding="UTF-8" ?>  \
<correntistas> \
<conta agencia="0123-4"> <tipo>física</tipo> \
<nome>José Maria</nome> <numero>000.000-00</numero> \
</conta> \
<conta agencia="5678-9"> <tipo>jurídica</tipo> \
<nome>José Maria SA</nome> <numero>111.111-11</numero> \
</conta> \
</correntistas>';

//Converte a string acima para um documento XML válido
var parser = new DOMParser();
var xmlDoc = parser.parseFromString(xmlString, "text/xml");

//Chamada a função responsável por coletar e exibir dados do XML
manipulaXML(xmlDoc);

function manipulaXML(xml) {
document.getElementById("result").innerHTML =
xml.getElementsByTagName("nome")[0].childNodes[0].nodeValue;
}
</script>
</body>
</html>
Como visto no código, foi criada uma string JS que, a seguir, foi transformada em um documento XML válido. Estando nesse formato, foi possível manipular o seu conteúdo através do DOM. Com o método ‘getElementsByTagName’ e as propriedades “childNodes” e “nodeValue”, foi acessado o conteúdo do primeiro elemento <nome> e atribuído o seu valor à tag HTML <p>, para exibição do resultado na tela.

ATENÇÃO
Nos exemplos aqui demonstrados foi utilizada a linguagem de programação Javascript. Entretanto, conforme já mencionado, é possível usar qualquer linguagem de sua preferência para a manipulação do XML DOM.


Exemplos de manipulação de XML DOM


Propriedades XML DOM

Estas são algumas das propriedades disponíveis cujos nomes são autoexplicativos: 

nodeName
nodeValue
parenteNode
childNodes
attributes
Métodos XML DOM

Em relação aos métodos, estes são alguns dos disponíveis cujos nomes são autoexplicativos: 

getElementsByTagName(name)
getAttributeNode(node)
appendChild(node)
removeChild(node)
createElement(name)
createTextNode(value)
OUTRAS FORMAS DE NAVEGAR POR UM DOCUMENTO XML
Além dos recursos vistos acima, há outras formas de navegar pelos elementos e atributos de um documento XML. Entre eles, destacam-se:

XPATH
XPath, que é uma recomendação do W3C e possui mais de 200 funções prontas para navegar em documentos XML utilizando a sintaxe “path like”.

XQUERY
XQuery, que é uma linguagem para realização de consultas no formato de queries – representando para o XML o mesmo que o SQL representa para os bancos de dados.

RECURSOS AVANÇADOS
Além dos conceitos e exemplos vistos ao longo desse módulo, há muito mais para se estudar e aprender a respeito de XML. Por exemplo: DTDs (Document Type Definition), Schemas, Entidades, Notações, tipos de dados (datas, números, strings etc.). Embora o que vimos seja o bastante para utilizar o formato XML para a transmissão de dados em sistemas web na maioria dos casos, é recomendado que, caso você precise de recursos mais avançados, leia mais a respeito desse formato. A especificação W3C é um bom ponto de partida.

VERIFICANDO O APRENDIZADO
1. CONSIDERANDO O DOCUMENTO XML A SEGUIR, ASSINALE A ALTERNATIVA CORRETA E QUE DESCREVA O PORQUÊ DESSE DOCUMENTO NÃO SER CONSIDERADO VÁLIDO (BEM FORMATADO).

<?XML VERSION="1.0" ENCODING="UTF-8"?>
<NOTE>
<TO>TOVE</TO>
<FROM>JANI</>
<HEADING>REMINDER</HEADING>
<BODY>DON'T FORGET ME THIS WEEKEND!</BODY>
</NOTE>
Não é permitido iniciar um documento XML com uma tag escrita em letras minúsculas.

Em XML podemos criar nossas próprias tags. Entretanto, não é possível utilizar nomes de tags já existentes em HTML, como a tag <body>, acima.

As tags XML precisam ser abertas e fechadas corretamente. Logo, uma tag não fechada da maneira correta torna o documento inválido.

Não é permitido utilizar verbos como nome de tags em XML.

2. EM RELAÇÃO AO XML DOM, ASSINALE A AFIRMATIVA CORRETA:
A interface DOM, relacionada a documentos XML, nada tem a ver com a interface DOM, relacionada a documentos HTML, já que ambos são linguagens não relacionadas.

Em XML, temos a liberdade de criar nossos próprios métodos dentro da interface DOM para manipulação de um documento, da mesma forma que temos liberdade para criar nossas próprias tags.

A interface DOM é um padrão para manusear documentos nos formatos HTML e XML. Através dessa interface, podemos acessar os elementos e atributos de um documento através das propriedades e métodos por ela disponibilizados.

A manipulação de documentos XML através do DOM só é possível através da linguagem de programação Javascript.

GABARITO
1. Considerando o documento XML a seguir, assinale a alternativa correta e que descreva o porquê desse documento não ser considerado válido (bem formatado).

<?xml version="1.0" encoding="UTF-8"?>
<note>
<to>Tove</to>
<from>Jani</>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
</note>
A alternativa "C " está correta.


Na linguagem de marcação XML, devemos ter alguns cuidados, embora tenhamos a flexibilidade de criarmos nossas próprias tags. Nesse sentido, o documento precisa, entre outras premissas, ser composto por tags válidas — sendo uma tag considerada válida quando aberta e fechada adequadamente, por exemplo. No exemplo anterior, a tag <from> foi fechada incorretamente, tornando assim o documento inválido.

2. Em relação ao XML DOM, assinale a afirmativa correta:

A alternativa "C " está correta.


O Document Object Model (DOM) é uma interface de plataforma e linguagem neutra. Logo, documentos escritos com linguagens de marcação como HTML e XML podem ser manuseados através dessa interface (sendo possível usar a maioria das linguagens de programação) que oferece métodos e propriedades distintas, para cada tipo de documento, que permitem acesso tanto aos seus elementos, quanto ao seu conteúdo.

MÓDULO 2
Descrever os formatos de transmissão de dados JSON e YAML

INTRODUÇÃO
Por muitos anos, XML foi o principal formato para armazenamento e transmissão de dados na Internet. Entretanto, após a sua criação, novos formatos foram e continuam sendo criados. Neste módulo, serão descritos dois entre os mais utilizados — JSON e YAML. Com isso, após conhecer cada um desses três formatos, é esperado que você tenha os subsídios necessários para escolher, frente a cada cenário, qual formato utilizar no desenvolvimento de sistemas web.


Autor: kangshutters / Fonte: Shuttestock
O FORMATO JSON
JSON, acrônimo para Javascript Object Notation, é uma sintaxe para armazenamento e troca de dados. Trata-se de um formato de texto escrito com notação de objeto Javascript (W3C, 2020). Com JSON, é possível representar dados de forma estruturada e transmiti-los na web, enviando e recebendo dados de servidores remotos e exibindo-os em páginas HTML ou em aplicativos, por exemplo. 

A data de criação desse formato remete ao início dos anos 2000. Em 2001, ele foi apresentado pela primeira vez através do site json.org. A especificação mais atual do JSON é a ECMA-404. Tal especificação define um pequeno conjunto de regras para a representação estruturada de dados e seu principal objetivo é definir a sintaxe de um documento JSON válido.

JSON
Embora derivado e normalmente associado ao Javascript e, consequentemente, ao ECMAScript, JSON é um formato independente de linguagem de programação. Logo, pode ser usado em conjunto com qualquer linguagem.

A SINTAXE JSON
A sintaxe JSON é composta por duas estruturas: 

Coleção de pares nome: Valor (estrutura que, nas linguagens de programação, pode ser representada por objetos, dicionário, hash table, array associativo, entre outros).
Lista ordenada de valores (nas linguagens de programação, pode ser representada como um array, vetor, lista, sequência, entre outros). 
Logo a seguir, é apresentado o JSON correspondente ao XML usado no módulo anterior. Após o código, cada elemento JSON será descrito.

{
"correntistas": {
"conta": [
{
"agencia": "0123-4",
"tipo": "física",
"nome": "José Maria",
"numero": "000.000-00"
},
{
"agencia": "5678-9",
"tipo": "jurídica",
"nome": "José Maria SA",
"numero": "111.111-11"
}
]
}
}
O código acima também pode ser chamado de texto JSON. Os dados após as chaves “agencia”, “tipo”, “nome” e “numero” são os valores JSON. O par chave: valor — como “agencia”: “0123-4” — é chamado de objeto JSON. A chave “conta” é um array.

Vejamos esses elementos em detalhes.

TEXTO JSON
Um texto JSON é uma sequência de tokens formados a partir de código Unicode, em conformidade com a gramática JSON. Tal conjunto de tokens possui seis tokens estruturais (e que podem ser vistos no código acima): 

[
]
{
}
:
,
VALORES JSON
Um valor JSON pode ser: 

Um objeto
Um array
Um número
Uma string
true
false
null
OBJETOS JSON
A estrutura de um objeto JSON é representada como um par de chaves “{“ e “}” que englobam nenhum ou alguns pares de nome/valor, no qual o nome é uma string, seguido de dois pontos (:) que separam o nome do valor. Esse par “nome:valor” pode ou não ser procedido de um ou mais pares nome/valor, devendo esses serem separados por vírgula.

DICA
A sintaxe JSON não determina nenhuma restrição relacionada às strings utilizadas como nome, assim como não exige que os nomes sejam exclusivos. Além disso, a especificação JSON não define nenhum significado para a ordenação dos pares nome:valor.

ARRAYS EM JSON
Um array, em JSON, é uma estrutura representada por colchetes que englobam nenhum ou alguns conjuntos de pares “nome:valor”, que deverão ser separados por vírgulas. Além disso, a sintaxe JSON não prevê nenhuma forma para ordenar os valores do array. Como mencionado no exemplo anterior, a chave “conta” é um array.

JSON NA PRÁTICA
Vejamos, através de alguns códigos, como enviar, receber e armazenar dados em JSON, utilizando a linguagem Javascript.

ENVIANDO DADOS
Neste exemplo, é criado um objeto Javascript, que depois é convertido em texto JSON para ser enviado para um servidor remoto, onde poderá ser processado por uma linguagem server side, como Java, PHP etc.

//Cria um objeto Javacript
var objtoJS   = {agencia: "5678-9", tipo: "física", nome: "Maria José", numero: "222.222-22"};

//Converte o objeto Javascript em texto JSON
var textoJson = JSON.stringify(objtoJS);

//Redireciona a página para o endereço especificado, passando, via GET, o texto JSON
window.location = "processa/json/?conta=" + textoJson;
RECEBENDO DADOS
Neste exemplo, será criado um texto JSON, que será convertido em um objeto Javascript e então atribuído a um elemento HTML. Esse exemplo simula, entre outros, a situação em que, através de uma requisição AJAX, ou outro tipo de requisição, recebemos como retorno um texto JSON e precisamos manipulá-lo para acessar e utilizar seus dados.

//Representa um texto JSON (que poderia ter sido recebido de uma requisição, por ex)
var textoJson   = '{"agencia": "5678-9", "tipo": "física", "nome": "Maria José", "numero": "222.222-22"}';

//Converte o texto JSON em um objeto Javascript
var objtoJS = JSON.parse(textoJson);

//Exibe na tag html com id=resultado os dados da conta
document.getElementById("resultado").innerHTML = 'Agência: ' + objtoJS.agencia + ' Tipo: ' + objtoJS.tipo + ' Nome: ' + objtoJS.nome + ' Número: ' + objtoJS.numero;
ARMAZENANDO DADOS
O exemplo, a seguir, demonstra como armazenar dados no formato JSON. Para isso, será utilizado um objeto Javascript que será convertido em texto JSON e, a seguir, armazenado. Além disso, também será demonstrado como recuperar os dados armazenados.

//Cria um objeto Javacript
var objtoJS   = {agencia: "5678-9", tipo: "física", nome: "Maria José", numero: "222.222-22"};

//Converte o objeto Javascript em texto JSON
var textoJson = JSON.stringify(objtoJS);

//Armazenando os dados no navegador
localStorage.setItem("stringJSON", textoJson);
DICA
Para visualizar os dados armazenados no navegador com o método “localStorage”, após inserir o código acima em uma página HTML e executá-lo, com a página aberta no navegador, abra o inspecionador de elementos, navegue até a aba “Application” e, no menu à esquerda, opção “Storage”, vá até “Local Storage”. Nesse item, será possível ver as chaves e respectivos valores armazenados (em nosso caso, a chave será “stringJSON”).

Para recuperar os dados acima, armazenados com “localStorage”, utilize o código a seguir:

//Cria uma variável para receber o conteúdo armazenado com localStorage
var jsonText = localStorage.getItem("stringJSON");
//Converte em um objeto Javascript
jsOBJ = JSON.parse(jsonText);

//Exibe o conteúdo do objeto JS com o alert
alert('Agência: ' + jsOBJ.agencia + ' Tipo: ' + jsOBJ.tipo + ' Nome: ' + jsOBJ.nome + ' Número: ' + jsOBJ.numero);
O FORMATO YAML
YYAML, acrônimo original para “Yet Another Markup Language”, e atualmente um acrônimo recursivo para “YAML Ain´t Mark-up Language”, como o próprio nome diz, não é uma linguagem de marcação. Trata-se de uma linguagem para serialização e transmissão de dados cujo formato é amigável para humanos e de fácil entendimento para máquinas, podendo ser usada com a maioria das linguagens de programação. Assim como XML e JSON, essa linguagem, como já mencionada, é usada para a transmissão de dados na Internet. Em comparação com os outros dois formatos, sua sintaxe é parecida, em termos de estrutura, com JSON. É comum vermos esse formato sendo utilizado como arquivo de configuração ou arquivo de logs, embora não fique limitada a tais funções.

A SINTAXE YAML
Em termos de estrutura e sintaxe, a YAML tem por característica usar poucos caracteres estruturais a fim de permitir que os dados sejam exibidos de forma natural. Nesse sentido, a sintaxe de um arquivo YAML é composta por: 

Recuo/tabulação, usado como estrutura.
Sinal de dois pontos (“:”), usado como separador do par “chave: valor”.
Travessão, usado para a criação de listas de marcadores.
A seguir, podemos ver, como YAML, a mesma estrutura vista anteriormente como XML e posteriormente como JSON:

correntistas:
conta:
- agencia: 0123-4
tipo: física
nome: José Maria
numero: 000.000-00
- agencia: 5678-9
tipo: jurídica
nome: José Maria SA
numero: 111.111-11
A fim de destacar as diferenças de estrutura, abaixo podem ser vistas as notações XML, JSON e YAML que representam a estrutura de dados que armazena dados de correntistas e que vem sendo utilizada como exemplo ao longo deste tema.




Figura 4: Comparativo entre XML, JSON E YAML. Fonte: O Autor.
Como podemos ver, YAML utiliza menos tokens, ou sinais, em sua estrutura, se comparada a XML e JSON — da mesma forma que JSON o faz em relação a XML. Tal minimalismo faz com que YAML seja bastante leve. Além disso, ainda no âmbito de comparação com os outros formatos vistos, o formato YAML privilegia a leitura e compreensão por humanos, em detrimento da interpretação por linguagens de programação. Nesse ponto, ela tem comportamento inverso ao JSON, que ao custo de ser menos legível por humanos, é mais fácil de ser gerada e interpretada por linguagens de programação.

YAML NA PRÁTICA
Vejamos, de forma prática, como trabalhar com dados armazenados com o formato YAML. No primeiro código, será demonstrado como realizar a leitura de um arquivo YAML utilizando a linguagem Javascript e, no segundo, como gerar um arquivo YAML a partir de Javascript.

ATENÇÃO
Repare que, em ambos os exemplos, faz-se necessária a utilização de uma biblioteca de parser (a Standalone JavaScript YAML 1.1 Parser & Encoder, disponível em < https://github.com/jeremyfa/yaml.js >). Essa necessidade se deve ao fato de que, conforme mencionado, o processo de interpretação do formato em questão, por linguagem de programação, é mais complexo que o de outros formatos (como XML e JSON.).

<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>Parser YAML em Javascript</title>
<!-- Incorporando a biblioteca (de terceiros) que faz o parser yaml => javascript -->
<script type="text/javascript" src="yaml.js"></script>
</head>
<body>
<p id="resultado"></p>
<script type="text/javascript">

//Recuperando o conteúdo do arquivo yaml e, através do parser, transformando-o em um objeto JS
objJavascript = YAML.load('clientes.yml');

//console.dir(objJavascript);

//Armazenando a propriedade 'conta', do objeto JS, que é um array, em uma nova variável
var arrayContas = objJavascript.correntistas.conta;

//Percorrendo o array de contas, com a função nativa JS map e exibindo os valores no elemento HTML #resultado
arrayContas.map(function(conta) {
  document.getElementById("resultado").innerHTML += 'Agência: ' + conta.agencia + ' Tipo: ' + conta.tipo + ' Nome: ' + conta.nome + ' Número: ' + conta.numero + '<br/>';
});

</script>
</body>
</html>
Para executar o código, salve-o em uma pasta, em um servidor web, com o arquivo da biblioteca/parser (mencionada acima) e com o arquivo ‘clientes.yml’, cujo conteúdo pode ser visto na figura 4.

DICA
Leia com atenção os comentários inseridos no código. Através deles, é explicado o que acontece linha a linha.

<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>Parser YAML em Javascript</title>
<!-- Incorporando a biblioteca (de terceiros) que faz o parser yaml => javascript -->
<script type="text/javascript" src="yaml.js"></script>
</head>
<body>
<p id="resultado"></p>
<script type="text/javascript">

//Cria um objeto Javacript
var objtoJS  = {conta:{agencia: '5678-9', tipo: 'física', nome: 'Maria José', numero: '222.222-22'}};

//Converte, com o parser, o objeto Javascript em texto YAML
var yamlString = YAML.stringify(objtoJS);

//Chamda a função download que possibilita o download do arquivo no formato YAML
download(yamlString, 'cliente.yml', 'application/yaml');

function download(content, fileName, contentType) {
var a = document.createElement("a");
var file = new Blob([content], {type: contentType});
a.href = URL.createObjectURL(file);
a.download = fileName;
a.click();
}


</script>
</body>
</html>
ATENÇÃO
Todos os arquivos utilizados nesses exemplos podem ser encontrados na seção “Preparação”, dentro do arquivo compactado: “Códigos-fontes dos exercícios_Tecnologias de Transmissão de Dados em Sistemas Web”.


JSON E YAML NA PRÁTICA

Como vimos, se compararmos o processo de leitura e geração de conteúdo entre os três formatos descritos, o mais complexo deles diz respeito ao YAML. Além disso, a linguagem utilizada nos exemplos foi a Javascript. Entretanto, para cada linguagem de programação, o grau de dificuldade para manuseio desses formatos pode variar. Logo, não existe um formato melhor do que o outro. Na verdade, o melhor formato é o que melhor se adequa, em primeiro lugar, às necessidades de cada projeto e, em segundo lugar, às linguagens de programação utilizadas.

VERIFICANDO O APRENDIZADO
1. DENTRE AS AFIRMATIVAS ABAIXO, UMA NÃO DESCREVE A SINTAXE E ANATOMIA DE UMA STRING JSON. ASSINALE A ALTERNATIVA EM QUESTÃO.
Tags: Assim como em XML ou HTML, um arquivo JSON é composto por tags para nomear um atributo ou propriedade. Tal tag é seguida pelo sinal de dois pontos (“:”) e pelo seu valor.

Uma string JSON possui alguns tokens estruturais, como “[“, “{“, “:” e “,”.

Os tokens “[“ e “]” são usados para definir/englobar os dados de um array.

É possível ter, em um documento JSON, um par “chave:valor” cujo valor seja nulo (null).

2. ASSINALE A AFIRMATIVA QUE CORRESPONDA À SINTAXE DE UM DOCUMENTO NO FORMATO YAML.
No formato YAML, sendo esse derivado do formato JSON, estão disponíveis os mesmos tokens/sinais para a criação de um documento, como: “{“ , “[“ e “,”.

O formato YAML, como seu nome diz, é uma linguagem de marcação. Entretanto, um documento YAML pode ou não fazer uso de tags, como as vistas em documentos XML.

A sintaxe do formato YAML foi criada para privilegiar a sua leitura por máquinas/linguagens de programação. Logo, trata-se do formato mais fácil de ser interpretado por esses meios.

A estrutura de um documento escrito no formato YAML é caracterizada por utilizar poucos caracteres estruturais, fazendo com que os dados representados se pareçam com sua forma natural. Logo, um arquivo nesse formato é muito amigável a humanos.

GABARITO
1. Dentre as afirmativas abaixo, uma não descreve a sintaxe e anatomia de uma string JSON. Assinale a alternativa em questão.

A alternativa "A " está correta.


No formato JSON, diferentemente de linguagens de marcação, como XML, não temos tags para etiquetar os nossos dados. Em seu lugar, é usada uma estrutura composta por uma coleção de pares “nome:valor”, sendo o nome a etiqueta do dado, seguido pelo sinal de dois pontos “:” e pelo seu valor.

2. Assinale a afirmativa que corresponda à sintaxe de um documento no formato YAML.

A alternativa "D " está correta.


O formato YAML se difere de outros formatos como XML e JSON por não fazer uso de muitos elementos estruturais para a definição e estruturação de seus dados. Tal característica, embora dificulte sua leitura através de linguagens de programação, dada a sua simplicidade, a torna, por outro lado, muito amigável à leitura por humanos.

MÓDULO 3
Demonstrar como utilizar dados nos formatos XML, JSON e YAML em requisições AJAX

INTRODUÇÃO
Neste momento, todos os conceitos teóricos, além de parte dos exemplos práticos, vistos nos módulos anteriores, serão consolidados através da demonstração de como utilizar, na prática, os formatos de transmissão de dados XML, JSON e YAML em requisições AJAX. Dentro disso, cada código será repetido, a fim de evidenciar como trabalhar com essas tecnologias usando Javascript puro e com o framework Javascript jQuery.


Autor: PegasuStudio / Fonte: Shutterstock
XML E AJAX
Inicialmente, veremos como utilizar dados armazenados no formado XML através de requisições AJAX. Embora aqui representados por arquivos salvos com a extensão “.xml”, tais arquivos poderiam ser substituídos por conteúdo gerado por linguagens de programação server side — desde que, claro, estejam no formato em questão. Para isso, troque o endereço do arquivo local para o do recurso em questão.

ATENÇÃO
Aqui será demonstrado apenas o primeiro nó para entendimento da estrutura. Os demais dados estão no arquivo disponível para download.

Vamos ao código, começando com o arquivo XML, que será lido e, a seguir, pelo arquivo HTML e Javascript que consumirá os dados do XML e os exibirá na página (baixe o arquivo na seção “Preparação”).

PASSO 01
PASSO 02
<?xml version="1.0" encoding="UTF-8"?>
<Products>
<Product>
<Product_ID>7631</Product_ID>
<SKU>HEH-9133</SKU>
<Name>On Cloud Nine Pillow</Name>
<Product_URL>https://www.domain.com/product/heh-9133</Product_URL>
<Price>24.99</Price>
<Retail_Price>24.99</Retail_Price>
<Thumbnail_URL>https://www.domain.com/images/heh-9133_600x600.png</Thumbnail_URL>
<Search_Keywords>lorem, ipsum, dolor, ...</Search_Keywords>
<Description>Sociosqu facilisis duis ...</Description>
<Category>Home>Home Decor>Pillows|Back In Stock</Category>
<Category_ID>298|511</Category_ID>
<Brand>FabDecor</Brand>
<Child_SKU></Child_SKU>
<Child_Price></Child_Price>
<Color>White</Color>
<Color_Family>White</Color_Family>
<Color_Swatches></Color_Swatches>
<Size></Size>
<Shoe_Size></Shoe_Size>
<Pants_Size></Pants_Size>
<Occassion></Occassion>
<Season></Season>
<Badges></Badges>
<Rating_Avg>4.2</Rating_Avg>
<Rating_Count>8</Rating_Count>
<Inventory_Count>21</Inventory_Count>
<Date_Created>2018-03-03 17:41:13</Date_Created>
</Product>
<!-- No arquivo original há mais produtos no arquivo XML -->
</Products>
<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>Requisições AJAX com XML</title>
<style type="text/css">
table {border-collapse: collapse;}
th, td {padding: 15px;text-align: left;}
tr:nth-child(even) {background-color: #f2f2f2;}
</style>
</head>
<body>
<div id="resultado"></div>

<script type="text/javascript">
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
if (this.readyState == 4 && this.status == 200) { //Passando o resultado da requisição (o conteúdo em XML) para a função manipulaXML
manipulaXML(this);
}
};
xhttp.open("GET", "produto.xml", true);
xhttp.send();

/*
Esta função recebe o xml resultado da requisição AJAX.
Após ler o conteúdo, faz o parse e inclui o contéudo no elemento html de id #resultado
*/
function manipulaXML(xml) {
//o objeto responseXML trata o resultado de uma requisição AJAX no formato XML
var xmlDoc = xml.responseXML;

//Criando uma tabela para armazenar os dados e exibi-los na página
var table = "<table>";
table += '<tr>';

//Armazena o primeiro no Product
var primeiroNoProduct = xmlDoc.getElementsByTagName("Product")[0];
//Armazena os nós filhos do primeiro nó Product
var nosFilhosNoProduct = primeiroNoProduct.childNodes;

for (var j = 0; j < nosFilhosNoProduct.length; j++) {
var noFilho = nosFilhosNoProduct[j];
//Como os nós filhos também contém nós relacionados aos espaços em branco,
//  é preciso tratar esses nós para coletar apenas as tags válidas, com nos nomes dos filhos
if (noFilho.nodeType === 1){
//Armazenando os nomes dos nós para serem usados como cabeçalho da tabela HTML
table += '<th>'+noFilho.nodeName+'</th>';
}
}
table += '</tr>';

//Percorre todo o arquivo XML, coleta os valores dos nós
//  e os armazena como linhas e colunas da tabela HTML
//Armazena os nós Product
var nosProduct = xmlDoc.getElementsByTagName("Product");

for (var cont = 0; cont < nosProduct.length; cont++) {
var filhosNoProduct = nosProduct[cont].childNodes;
table += '<tr>';
for (var contFilhos = 0; contFilhos < filhosNoProduct.length; contFilhos++) {
if (filhosNoProduct[contFilhos].nodeType === 1){
table += (filhosNoProduct[contFilhos].firstChild) ? '<td>'+filhosNoProduct[contFilhos].firstChild.nodeValue+'</td>' : '<td>null</td>';
}
}
table += '</tr>';
}

table += "</table>";

document.getElementById("resultado").innerHTML = table;
}
</script>
</body>
</html>
Ao analisar o código anterior, perceba que é realizada uma verificação em relação ao tipo de nó, no ponto onde os nós filhos são coletados. Tal fragmento pode ser visto a seguir:

noFilho.nodeType === 1

Essa verificação é necessária, uma vez que os espaços em branco, no arquivo XML, também são considerados como nós. Veja na figura, uma parte dos nós filhos do elemento <Product> e repare que existem vários nós “#text” junto aos demais nós.


Figura 5: Fragmento dos nós do arquivo XML. Fonte: O Autor.
JSON E AJAX
Veremos agora como trabalhar com JSON e AJAX. Nesse contexto, o primeiro código contém um fragmento do arquivo JSON que será requisitado via AJAX. Vamos observar o código AJAX que recupera o conteúdo do arquivo JSON, o processa e utiliza para exibir, no formato de tabela, na página web.

{
"Products": {
"Product": [
{
"Product_ID": "7631",
"SKU": "HEH-9133",
"Name": "On Cloud Nine Pillow",
"Product_URL": "https://www.domain.com/product/heh-9133",
"Price": "24.99",
"Retail_Price": "24.99",
"Thumbnail_URL": "https://www.domain.com/images/heh-9133_600x600.png",
"Search_Keywords": "lorem, ipsum, dolor, ...",
"Description": "Sociosqu facilisis duis ...",
"Category": "Home>Home Decor>Pillows|Back In Stock",
"Category_ID": "298|511",
"Brand": "FabDecor",
"Child_SKU": "",
"Child_Price": "",
"Color": "White",
"Color_Family": "White",
"Color_Swatches": "",
"Size": "",
"Shoe_Size": "",
"Pants_Size": "",
"Occassion": "",
"Season": "",
"Badges": "",
"Rating_Avg": "4.2",
"Rating_Count": "8",
"Inventory_Count": "21",
"Date_Created": "2018-03-03 17:41:13"
}
]
}
}
Como visto, estamos trabalhando com a mesma estrutura de dados usada no primeiro exemplo, em XML, ou seja, uma lista de produtos. A seguir, o código para coletar e processar essa estrutura.

<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<title>Requisições AJAX com JSON</title>
<style type="text/css">
table {border-collapse: collapse;}
th, td {padding: 15px;text-align: left;}
tr:nth-child(even) {background-color: #f2f2f2;}
</style>
</head>
<body>
<div id="resultado"></div>

<script type="text/javascript">
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
if (this.readyState == 4 && this.status == 200) {
//Passando o resultado da requisição (o conteúdo em XML) para a função manipulaXML
manipulaJSON(this);
}
};
xhttp.open("GET", "produto.json", true);
xhttp.send();

/*
Esta função recebe o json resultado da requisição AJAX.
Após ler o conteúdo, faz o parse e inclui o contéudo no elemento html de id #resultado
*/
function manipulaJSON(json) {
//o objeto responseText trata o resultado de uma requisição AJAX no formato de texto.
//  com a função JSON.parse convertemos o formato texto em um objeto Javascript
var jsonDoc = JSON.parse(json.responseText);

//Criando uma tabela para armazenar os dados e exibi-los na página
var table = "<table>";
table += '<tr>';
//Percorre as chaves do array (no índice 0), dentro do objeto, para montar os títulos da tabela
for (let key in jsonDoc.Products.Product[0]){
table += '<th>'+key+'</th>';
}
table += '</tr>';

//Percorre o array, dentro do objeto, para montar, com seus valores, as linhas da tabela HTML
jsonDoc.Products.Product.forEach(function(item) {
table += '<tr>';
Object.keys(item).forEach(function(key) {
//console.log("key:" + key + "value:" + item[key]);
table += '<td>'+item[key]+'</td>'
});
table += '</tr>';
});
table += "</table>";

document.getElementById("resultado").innerHTML = table;
}
</script>
A exemplo do que foi feito com o arquivo XML, o código acima trata os dados recebidos da requisição AJAX — aqui no formato texto e posteriormente convertido em objeto JSON — e atribui as informações em uma tabela HTML.

Ao longo dos códigos, estão inseridos comentários explicando algumas de suas partes.

PRINCIPAIS DIFERENÇAS NO PROCESSAMENTO DE XML E JSON
Os códigos, acima, que tratam da requisição e manipulação dos dados nos formatos XML e JSON, contêm alguns comentários explicando cada passo do processo. Ainda assim, é importante destacar algumas das diferenças referentes à manipulação desses dois formatos de arquivos. Vamos a elas:

RESPONSEXML VS RESPONSETEXT
Através de requisições AJAX, é possível recuperar dados de recursos remotos em diferentes formatos, como XML, texto puro, HTML e JSON. Já no código Javascript — no objeto xmlHttpRequest —, há dois métodos disponíveis para tratar esses formatos: responseText e responseXML. Com o primeiro, tratamos os dados recebidos que não estejam no formato XML. Logo, com ele teremos os dados da resposta representados como texto. Daí a necessidade de, ao recuperar dados como JSON, realizar um parse desses dados a fim de poder manipulá-los como um objeto JS. Com isso, conseguimos acessar cada par “chave: valor” do arquivo JSON na notação de objeto.

Com o segundo método, responseXML, tratamos os dados no formato XML. Nesse caso, há métodos específicos para recuperar os dados através dos nós e valores do arquivo XML.

DADOS COMO OBJETOS JS
Quando estiver trabalhando com AJAX, e sempre que possível, converta o resultado obtido em objeto JS. Isso facilita o trabalho de interagir sobre os dados, pois teremos acesso diretamente aos métodos e objetos nativos da linguagem Javascript.

Uma dica para descobrir qual o formato dos dados recebidos é utilizar o método “console.dir” no resultado da requisição (seja ela responseXML ou responseText). Através desse método, podemos ver, no console do inspecionador de elementos, o formato desses dados. Veja, a seguir, o resultado desse método aplicado sobre o responseXML e responseText dos exemplos anteriores. Além disso, há também o resultado após ter sido realizado o “JSON.parser” sobre o responseText do segundo exemplo.


Figura 6 - Fragmentos de dados após aplicação do método “console.dir”. Paixão, 2020.
Repare na figura (que contém apenas parte dos resultados da aplicação do método “console.dir” sobre cada retorno), a diferença entre cada dado. 

Veja que, no primeiro, no formato XML, já na primeira linha, temos a informação “#document” e, a seguir, quando expandimos esse cabeçalho, temos disponíveis diversas propriedades como “childNodes”, “firstChild”, entre outros. 

Todas elas relacionadas especificamente ao formato em questão. Já na segunda, perceba que temos apenas um texto plano, na string JSON. Por fim, após aplicação do “JSON.parser” sobre a string JSON, na primeira linha temos o “Object”. Ao expandi-lo, temos a estrutura, no formato de objetos e arrays, dos dados.

YAML E AJAX
Trabalhar com dados transferidos no formato YAML é semelhante ao que vimos em relação ao JSON, uma vez que os dados também serão transferidos no formato de texto puro e que, através do método responseText, teremos acesso a eles. Então, de posse dos dados no formato YAML, teremos, nesse caso, um passo adicional, que é o de transformá-los no formato de objeto JS/JSON.

RECOMENDAÇÃO
Para essa tarefa, é recomendado utilizar um parser, uma biblioteca de terceiros — como vimos no módulo que tratou desse formato de dados. Após a conversão, todo o código restante será exatamente igual ao que utilizamos no último exemplo — por esse motivo, os passos relacionados à recuperação dos dados e exibição na página HTML não serão repetidos aqui.

Abaixo, podemos ver o fragmento do arquivo YAML contendo os dados dos produtos (trata-se do mesmo conteúdo dos exemplos anteriores).

Products:
Product:
- Product_ID: '7631'
SKU: HEH-9133
Name: On Cloud Nine Pillow
Product_URL: https://www.domain.com/product/heh-9133
Price: '24.99'
Retail_Price: '24.99'
Thumbnail_URL: https://www.domain.com/images/heh-9133_600x600.png
Search_Keywords: lorem, ipsum, dolor, ...
Description: Sociosqu facilisis duis ...
Category: Home>Home Decor>Pillows|Back In Stock
Category_ID: 298|511
Brand: FabDecor
Child_SKU: ''
Child_Price: ''
Color: White
Color_Family: White
Color_Swatches: ''
Size: ''
Shoe_Size: ''
Pants_Size: ''
Occassion: ''
Season: ''
Badges: ''
Rating_Avg: '4.2'
Rating_Count: '8'
Inventory_Count: '21'
Date_Created: '2018-03-03 17:41:13'

FORMATOS XML, JSON E YAML EM REQUISIÇÕES AJAX

VERIFICANDO O APRENDIZADO
1. ASSINALE QUAL A AFIRMATIVA EQUIVALE À SAÍDA DO PROGRAMA ABAIXO, NA INSTRUÇÃO “ALERT”.

<!DOCTYPE HTML>
<HTML>
<HEAD>
<META CHARSET="UTF-8">
</HEAD>
<BODY>
<SCRIPT TYPE="TEXT/JAVASCRIPT">
//CRIA UM XML NO FORMATO DE STRING JS
VAR XMLSTRING = '<?XML VERSION="1.0" ENCODING="UTF-8"?>
<NOTE TO="MULTIPLES">
<TO>TOVE</TO>
<FROM>JANI</FROM>
<HEADING>REMINDER</HEADING>
<BODY>DONT FORGET ME THIS WEEKEND!</BODY>
</NOTE>';

//CONVERTE A STRING ACIMA PARA UM DOCUMENTO XML VÁLIDO
VAR PARSER = NEW DOMPARSER();
VAR XMLDOC = PARSER.PARSEFROMSTRING(XMLSTRING, "TEXT/XML");

ALERT (XMLDOC.GETELEMENTSBYTAGNAME("TO")[0].CHILDNODES[0].NODEVALUE);
</SCRIPT>
</BODY>
</HTML>
“multiples”

“Tove”

“undefined

“multiples” e “Tove”

2. UMA REQUISIÇÃO AJAX PODE RETORNAR DADOS EM DIFERENTES FORMATOS. NESSE SENTIDO, É CORRETO AFIRMAR QUE:
Dados de diferentes tipos podem ser tratados através dos métodos responseXML e responseText, sendo o primeiro responsável por tratar dados no formato XML e o segundo por tratar dados em formato de texto, devendo então serem realizados os devidos tratamentos sobre eles, visando sua manipulação.

Há vários métodos disponíveis para o tratamento de dados, conforme o seu formato, como o responseXML, o responseJSON, o responseText, o responseHTML, entre outros.

Em linguagens como o Javascript, todos os dados retornados a partir de uma requisição AJAX, independentemente do seu formato original, são convertidos automaticamente em objetos Javascript.

Não é possível, apenas utilizando recursos nativos da linguagem Javascript, manipular dados em diferentes formatos. Logo, para todo formato de dado, incluindo XML e JSON, é preciso utilizar bibliotecas de terceiros para realizar a sua transformação em um formato entendido por JS.

GABARITO
1. Assinale qual a afirmativa equivale à saída do programa abaixo, na instrução “alert”.

<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
</head>
<body>
<script type="text/javascript">
//Cria um XML no formato de string JS
var xmlString = '<?xml version="1.0" encoding="UTF-8"?>
<note to="multiples">
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Dont forget me this weekend!</body>
</note>';

//Converte a string acima para um documento XML válido
var parser = new DOMParser();
var xmlDoc = parser.parseFromString(xmlString, "text/xml");

alert (xmlDoc.getElementsByTagName("to")[0].childNodes[0].nodeValue);
</script>
</body>
</html>
A alternativa "B " está correta.


Para manipular dados no formato XML, podemos fazer uso da XML DOM ou de outros recursos, como o XPATH, por exemplo. Em relação ao XML DOM, temos métodos e propriedades para tratar os nós, atributos e seus respectivos dados. No fragmento acima, temos um nó e um atributo que possuem o mesmo nome, “to”. Entretanto, a forma de acessá-los é diferente: Para o primeiro, temos o “getElementsByTagName”. Já para o segundo, o “getAttribute”. Além disso, é necessário ter atenção para os nós do tipo “#text”, que representam os espaços em branco de um documento XML, sobretudo ao fazer uso de índices para acessar os nós do documento.

2. Uma requisição AJAX pode retornar dados em diferentes formatos. Nesse sentido, é correto afirmar que:

A alternativa "A " está correta.


As requisições AJAX retornam dados em dois formatos: XML e Texto. Logo, qualquer formato que não o XML é visto como um texto puro. Nesse sentido, as devidas tratativas são necessárias a fim de converter esses dados em uma estrutura manipulável pela linguagem de programação utilizada, seja através de recursos nativos da própria linguagem, seja através de bibliotecas de terceiros.

CONCLUSÃO
CONSIDERAÇÕES FINAIS
Neste tema, descrevemos alguns dos principais formatos para transmissão de dados utilizados no desenvolvimento web — XML, JSON e YAML. Tais formatos foram apresentados de modo conceitual e prático, através de exemplos que demonstraram como recuperar e armazenar dados. 

Ao final do tema, vimos como usar esses dados, os quais foram recuperados através de requisições AJAX para popular uma página HTML. Além disso, a fim de facilitar a compreensão entre as similaridades e as diferenças, apresentamos algumas distinções entre os formatos em questão.


AVALIAÇÃO DO TEMA:
REFERÊNCIAS
W3C. Extensible Markup Language (XML). In: W3C. Consultado  em meio eletrônico em: 20 ago. 2020. 

W3C. XML DOM Tutorial. In: W3C schools. Consultado em meio eletrônico em: 20 ago. 2020. 

W3C. JSON Introduction. In: W3C schools. Consultado em meio eletrônico em: 20 ago. 2020.

EXPLORE+
Para saber mais sobre os assuntos tratados neste tema, pesquise na Internet: 

Arrow Functions: A especificação Javascript ES6 apresentou alguns importantes novos recursos. Embora não possua suporte em todos os navegadores, como nas versões do Internet Explorer anteriores à Edge, tal especificação deve ser estudada a fundo. Entre as novidades, destacam-se as arrow functions. Veja como o guia de referência Javascript da Fundação Mozilla aborda as arrow functions, introduzindo uma série de conceitos e diversos exemplos. 
CONTEUDISTA
Alexandre de Oliveira Paixão

CURRÍCULO LATTES
