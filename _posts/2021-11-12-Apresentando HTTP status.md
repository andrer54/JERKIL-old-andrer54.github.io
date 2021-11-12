Índice
1	Lista de códigos de status HTTP
2	1xx Informativa
2.1	100 Continuar
2.2	101 Mudando protocolos
2.3	102 Processamento (WebDAV) (RFC 2518)
2.4	122 Pedido-URI muito longo
3	2xx Sucesso
3.1	201 Criado
3.2	202 Aceito
3.3	203 não-autorizado (desde HTTP/1.1)
3.4	204 Nenhum conteúdo
3.5	205 Reset
3.6	206 Conteúdo parcial
3.7	207-Status Multi (WebDAV) (RFC 4918)
4	3xx Redirecionamento
4.1	300 Múltipla escolha
4.2	301 Movido
4.3	302 Encontrado
4.4	303 Consulte Outros
4.5	304 Não modificado
4.6	305 Use Proxy (desde HTTP/1.1)
4.7	306 Proxy Switch
4.8	307 Redirecionamento temporário (desde HTTP/1.1)
4.9	308 Redirecionamento permanente (RFC 7538[2])
5	4xx Erro de cliente
5.1	400 Requisição inválida
5.2	401 Não autorizado
5.3	402 Pagamento necessário
5.4	403 Proibido
5.5	404 Não encontrado
5.6	405 Método não permitido
5.7	406 Não Aceitável
5.8	407 Autenticação de proxy necessária
5.9	408 Tempo de requisição esgotou (Timeout)
5.10	409 Conflito geral
5.11	410 Gone
5.12	411 comprimento necessário
5.13	412 Pré-condição falhou
5.14	413 Entidade de solicitação muito grande
5.15	414 Pedido-URI Too Long
5.16	415 Tipo de mídia não suportado
5.17	416 Solicitada de Faixa Não Satisfatória
5.18	417 Falha na expectativa
5.19	418 Eu sou um bule de chá
5.20	422 Entidade improcessável (WebDAV) (RFC 4918)
5.21	423 Fechado (WebDAV) (RFC 4918)
5.22	424 Falha de Dependência (WebDAV) (RFC 4918)
5.23	425 coleção não ordenada (RFC 3648)
5.24	426 Upgrade Obrigatório (RFC 2817)
5.25	429 pedidos em excesso
5.26	450 bloqueados pelo Controle de Pais do Windows
5.27	499 cliente fechou Pedido (utilizado em ERPs/VPSA)
6	5xx outros erros
6.1	500 Erro interno do servidor (Internal Server Error)
6.2	501 Não implementado (Not implemented)
6.3	502 Bad Gateway
6.4	503 Serviço indisponível (Service Unavailable)
6.5	504 Gateway Time-Out
6.6	505 HTTP Version not supported
7	Referências
8	Ligações externas
Lista de códigos de status HTTP
A seguir, uma lista de códigos de resposta em HTTP (HyperText Transfer Protocol). Isso inclui os códigos padrões de internet da IETF, outras especificações e alguns ​​códigos adicionais usados. O primeiro dígito do código de status, indica uma das cinco classes de resposta, o mínimo necessário para um cliente HTTP, é que ele reconheça essas cinco classes. Microsoft IIS pode usar sub-códigos decimais adicionais, específicos para fornecer mais informações, mas estes não estão listados aqui. As frases utilizadas são os exemplos padrão, mas qualquer alternativa humana legível pode ser fornecida. Salvo disposição em contrário, o código de status é parte do padrão HTTP/1.1. (Joel, 2011)

1xx Informativa
Indica que a requisição foi recebida e entendida. Essa resposta é despachada provisoriamente, enquanto o processamento da requisição continua. Serve para alertar ao cliente, que espere pela resposta final. A mensagem constitui-se apenas do Status-Line e cabeçalhos opcionais, e é encerrado por uma linha vazia, dado que a versão HTTP/1.0, não definiu nenhum código de status 1xx, os servidores não devem enviar uma resposta 1xx para um cliente HTTP/1.0, exceto sob condições experimentais.

100 Continuar
Isso significa que o servidor recebeu os cabeçalhos da solicitação, e que o cliente deve proceder para enviar o corpo do pedido (no caso de haver um pedido, um corpo deve ser enviado, por exemplo, um POST pedido). Se o corpo do pedido é grande, enviando-o para um servidor, se o pedido já foi rejeitado, com base em cabeçalhos inadequados é ineficiente. Para ter um cheque do servidor se o pedido pode ser aceito com base no pedido de cabeçalhos sozinho, o cliente deve enviar: Esperar 100-continue, como um cabeçalho no seu pedido inicial e verificar se a 100 Continuar, código de status é recebido em resposta antes de permanente (ou receber 417 Falha na expectativa e não continuar).

101 Mudando protocolos
Isso significa que o solicitante pediu ao servidor para mudar os protocolos, e o servidor está reconhecendo que irá fazê-lo.

102 Processamento (WebDAV) (RFC 2518)
Como uma solicitação WebDAV pode conter muitos sub-pedidos que envolvam operações de arquivo, pode demorar muito tempo para concluir o pedido. Este código indica que o servidor recebeu e está processando o pedido, mas ainda nenhuma resposta está disponível. Isso impede que o cliente ultrapasse o tempo limite e assuma que a requisição tenha sido perdida.

122 Pedido-URI muito longo
Este é um padrão IE7. Somente código não significa que o URI é mais do que um máximo de 2083 caracteres. (Ver código 414).

2xx Sucesso
Esta classe de códigos de status indica a ação solicitada pelo cliente foi recebida, compreendida, aceita e processada com êxito.

 {
   "Id": 1,
   "Title": "Lista de códigos de estado HTTP"
   "Corpo": "A seguir está uma lista de códigos de resposta em HTTP (HyperText Transfer Protocol). Isso inclui os códigos padrões de internet da IETF, outras especificações e alguns ​​códigos adicionais usados."
 }
201 Criado
O pedido foi cumprido e resultou em um novo recurso que está sendo criado.

202 Aceito
O pedido foi aceito para processamento, mas o tratamento não foi concluído. O pedido poderá ou não vir a ser posta em prática, pois pode ser anulado quando o processamento ocorre realmente.

203 não-autorizado (desde HTTP/1.1)
O servidor processou a solicitação com sucesso, mas está retornando informações que podem ser de outra fonte.

204 Nenhum conteúdo
O servidor processou a solicitação com sucesso, mas não é necessário nenhuma resposta.

205 Reset
O servidor processou a solicitação com sucesso, mas não está retornando nenhum conteúdo. Ao contrário da 204, esta resposta exige que o solicitante redefinir a exibição de documento.

206 Conteúdo parcial
O servidor está entregando apenas parte do recurso devido a um cabeçalho intervalo enviados pelo cliente. O cabeçalho do intervalo é usado por ferramentas como wget para permitir retomada de downloads interrompidos, ou dividir um download em vários fluxos simultâneos.

207-Status Multi (WebDAV) (RFC 4918)
O corpo da mensagem que se segue é um XML da mensagem e pode conter um número de códigos de resposta individual, dependendo de quantas sub-pedidos foram feitos.

3xx Redirecionamento
O cliente deve tomar medidas adicionais para completar o pedido. Essa classe de código de status indica que a ação ainda precisa ser levado pelo agente do usuário, a fim de atender à solicitação. A ação necessária pode ser realizada pelo agente, sem interação com o usuário, se e somente se o método utilizado no segundo pedido é GET ou HEAD. Um agente do usuário não deve redirecionar automaticamente uma solicitação de mais de cinco vezes, uma vez que tais redirecionamentos geralmente indicam um loop infinito.

300 Múltipla escolha
Indica várias opções para o recurso que o cliente pode acompanhar. É, por exemplo, poderia ser usado para apresentar opções de formato diferente para o vídeo, arquivos de lista com diferentes extensões, ou desambiguação sentido da palavra.

301 Movido
Esta e todas as solicitações futuras devem ser direcionadas para o URI.

302 Encontrado
Este é um exemplo de boas práticas industriais contradizendo a norma. A especificação HTTP/1.0 (RFC 1945) exigia ao cliente executar um redirecionamento temporário (a frase original que descreve o método era "Movido Temporariamente"), mas os browsers populares executavam 302 com a funcionalidade de um "303 Consulte Outros". Por isso, o HTTP/1.1 acrescentou códigos de status 303 e 307 para distinguir entre os dois comportamentos. No entanto, a maioria das aplicações Web e os frameworks ainda usam o código de status 302 como se fosse o 303.

303 Consulte Outros
A resposta a esta requisição pode ser encontrada sob outro URI usando o método GET. Quando recebido em resposta a um POST (ou PUT/DELETE), o cliente deve presumir que o servidor recebeu os dados e deve enviar uma nova requisição GET para o URI dado.[1]

304 Não modificado
Indica que o recurso não foi modificado desde o último pedido. Normalmente, o cliente fornece um cabeçalho HTTP do tipo If-Modified-Since ou If-None-Match para proporcionar um tempo contra o qual para comparar. Usar este cabeçalho poupa largura de banda e reprocessamento no servidor e cliente, uma vez que apenas os dados do cabeçalho são enviados e recebidos, e são utilizados os dados armazenados em cache.

305 Use Proxy (desde HTTP/1.1)
Muitos clientes HTTP (como o Mozilla e Internet Explorer) podem não tratar corretamente as respostas com este código de status, principalmente por razões de segurança.

306 Proxy Switch
Mudança de proxy. Deixou de ser usado.

307 Redirecionamento temporário (desde HTTP/1.1)
Nesta ocasião, o pedido deve ser repetido com outro URI, mas futuras solicitações ainda pode usar o URI original. Em contraste com o 303, o método de pedido não deve ser mudado quando a reedição do pedido original. Por exemplo, uma solicitação POST deve ser repetido com outro pedido POST.

308 Redirecionamento permanente (RFC 7538[2])
Indica que o recurso foi movido para um novo URI permanente e todas as requisições futuras devem usar um dos URIs retornados. Os códigos 307 e 308 são similares ao comportamento dos códigos 302 e 301, mas não permitem que o método HTTP seja modificado.

4xx Erro de cliente
A classe 4xx de código de status é destinado para os casos em que o cliente parece ter cometido um erro. Exceto quando estiver respondendo a uma solicitação HEAD, o servidor deve incluir uma entidade que contém uma explicação sobre a situação de erro, e se é uma condição temporária ou permanente. Esses códigos de status são aplicáveis a qualquer método de solicitação. Os agentes do usuário devem exibir qualquer entidade incluída para o usuário. Estes são tipicamente os códigos de erro mais comuns encontrados durante online.

400 Requisição inválida
O pedido não pôde ser entregue devido à sintaxe incorreta.

401 Não autorizado
Semelhante ao 403 Proibido, mais especificamente para o uso quando a autenticação é possível, mas não conseguiu ou ainda não foram fornecidos. A resposta deve incluir um cabeçalho do campo www-authenticate contendo um desafio aplicável ao recurso solicitado. Veja Basic autenticação de acesso e autenticação Digest acesso.

402 Pagamento necessário
Reservado para uso futuro. A intenção original era que esse código pudesse ser usado como parte de alguma forma de dinheiro digital ou esquema de micro pagamento, mas isso não aconteceu, e esse código não é usado normalmente.

403 Proibido
O pedido é reconhecido pelo servidor mas este recusa-se a executá-lo. Ao contrário resposta "401 Não Autorizado", autenticação não fará diferença e o pedido não deve ser requisitado novamente.

404 Não encontrado
Ver artigo principal: HTTP 404
O recurso requisitado não foi encontrado, mas pode ser disponibilizado novamente no futuro. As solicitações subsequentes pelo cliente são permitidas.

405 Método não permitido
Foi feita uma solicitação de um recurso usando um método de pedido que não é compatível com esse recurso, por exemplo, usando GET em um formulário, que exige que os dados a serem apresentados via POST, PUT ou usar em um recurso somente de leitura.

406 Não Aceitável
O recurso solicitado é apenas capaz de gerar conteúdo não aceitáveis ​​de acordo com os cabeçalhos Accept enviados na solicitação.

407 Autenticação de proxy necessária
O acesso está vinculado a um túnel de proxy e deve ser autenticado por meio de credenciais. Este vínculo pode ter sido configurado pelos administradores do conteúdo ao qual o acesso foi solicitado pelo usuário, ou pelos administradoras da rede a qual o usuário está conectado. Este último exige a autenticação para acesso a todos os conteúdos listados pelos administradores da rede.

408 Tempo de requisição esgotou (Timeout)
O servidor sofreu timeout ao aguardar a solicitação. De acordo com as especificações HTTP W3: "O cliente não apresentou um pedido dentro do tempo que o servidor estava preparado para esperar. O cliente PODE repetir o pedido sem modificações a qualquer momento mais tarde."

409 Conflito geral
Indica que a solicitação não pôde ser processada por causa do conflito no pedido, como um conflito de edição.

410 Gone
Indica que o recurso solicitado não está mais disponível e não estará disponível novamente. Isto deve ser usado quando um recurso foi intencionalmente removido e os recursos devem ser removidos. Ao receber um código de estado 410, o cliente não deverá solicitar o recurso novamente no futuro. Clientes como motores de busca devem remover o recurso de seus índices. A maioria dos casos de uso não necessitam de clientes e motores de busca para purgar o recurso, e um "404 Not Found" pode ser utilizado.

411 comprimento necessário
O pedido não especifica o comprimento do seu conteúdo, o que é exigido pelo recurso solicitado.

412 Pré-condição falhou
O servidor não cumpre uma das condições que o solicitante coloca na solicitação.

413 Entidade de solicitação muito grande
A solicitação é maior do que o servidor está disposto ou capaz de processar.

414 Pedido-URI Too Long
O URI fornecido foi muito longo para ser processado pelo servidor.

415 Tipo de mídia não suportado
A entidade tem um pedido tipo de mídia que o servidor ou o recurso não tem suporte. Por exemplo, o cliente carrega uma imagem como image / svg + xml, mas o servidor requer que as imagens usem um formato diferente.

416 Solicitada de Faixa Não Satisfatória
O cliente solicitou uma parte do arquivo, mas o servidor não pode fornecer essa parte. Por exemplo, se o cliente pediu uma parte do arquivo que está para além do final do arquivo.

417 Falha na expectativa
O servidor não pode cumprir as exigências do campo de cabeçalho "Espere-pedido".

418 Eu sou um bule de chá
Este código foi definido em 1998 como uma das tradicionais brincadeiras de 1º de abril da IETF, na RFC 2324, Hyper Text Cafeteira Control Protocol, e não é esperado para ser implementado por servidores HTTP reais.

422 Entidade improcessável (WebDAV) (RFC 4918)
O pedido foi bem formado, mas era incapaz de ser seguido devido a erros de semântica.

423 Fechado (WebDAV) (RFC 4918)
O recurso que está sendo acessado está bloqueado.

424 Falha de Dependência (WebDAV) (RFC 4918)
A solicitação falhou devido à falha de uma solicitação anterior (por exemplo, um PROPPATCH).

425 coleção não ordenada (RFC 3648)
Definido em projectos de "WebDAV Avançada Coleções Protocolo", mas não está presente no "Web Distributed Authoring and Versioning (WebDAV) Ordenados Coleções protocolo".

426 Upgrade Obrigatório (RFC 2817)
O cliente deve mudar para um outro protocolo, como TLS/1.0. Resposta n º 444 Um Nginx extensão do servidor HTTP. O servidor retorna nenhuma informação para o cliente e fecha a conexão (útil como um impedimento para malware). Com 449 Repetir Uma extensão de Microsoft. O pedido deve ser repetida após a realização da ação apropriada.

429 pedidos em excesso
O usuário enviou muitas solicitações em um determinado período de tempo ("limitação de taxa").

450 bloqueados pelo Controle de Pais do Windows
Uma extensão de Microsoft. Este erro é dado quando Parental Controls do Windows estão ativadas e está bloqueando o acesso a determinada página da web.

499 cliente fechou Pedido (utilizado em ERPs/VPSA)
Um Nginx extensão do servidor HTTP. Este código é introduzido para registrar o caso quando a conexão é fechada pelo cliente ao servidor HTTP é o processamento de seu pedido, fazendo com que servidor não consiga enviar o cabeçalho HTTP de volta.

5xx outros erros
500 Erro interno do servidor (Internal Server Error)
Indica um erro do servidor ao processar a solicitação. Na grande maioria dos casos está relacionada as permissões dos arquivos ou pastas do software ou script que o usuário tenta acessar e não foram configuradas no momento da programação/construção do site ou da aplicação. Para corrigir, verifique o diretório em que o arquivo ou recurso que houve falha de acesso está localizado, e este arquivo (bem como todos os outros), obedeçam às regras seguintes:

Pastas — chmod 755 (não utilizar 777) Arquivos — chmod 644 (não utilizar o 777, só utilizar outro se for expressamente solicitado na instalação).

OBS.: algumas aplicações e ou sistemas requerem permissões diferenciadas, pelo qual é importante verificar com os criadores do scripts/sistema, qual seria a permissão correta a usar. O exemplo descreve como é realizado em sistemas operacionais Unix-like. Fazer analogia como é realizado em sistemas como Windows (Windows 7, 8, XP entre outros).

Este erro também pode ocorrer se o arquivo .htaccess do seu site estiver modificando os parâmetros ou tentando fazer o PHP utilizar comandos como: php_flag ou php_value. Remova qualquer entrada com esses comandos do arquivo .htaccess. Se for fazer modificações nos parâmetros do PHP, utilize o arquivo php.ini para fazer isso.

501 Não implementado (Not implemented)
O servidor ainda não suporta a funcionalidade ativada.

502 Bad Gateway
Em regra, o erro acontece quando há uma configuração imprecisa entre os computadores de back-end, possivelmente incluindo o servidor Web no site visitado. Antes de analisar este problema, é necessário limpar o cache do navegador, completamente.

Se estiver navegando na Web e observar este problema em todos os websites visitados, então 1) o seu provedor de serviço de Internet tem uma falha/sobrecarga em um equipamento principal ou 2) tem algo de errado com a sua conexão interna à Internet, por exemplo, o firewall não está funcionando corretamente. Se for o primeiro caso, somente o seu provedor pode ajudar. Se for o segundo, você precisa corrigir o que quer que esteja prevenindo que você acesse a Internet.

Se tiver este problema somente em alguns websites visitados, provavelmente existe um problema nos sites. Por exemplo, uma das peças dos equipamentos estão falhando ou estão sobrecarregadas. Entre em contato com os responsáveis destes sites.

503 Serviço indisponível (Service Unavailable)
O servidor está em manutenção ou não consegue dar conta dos processamentos de recursos devido à sobrecarga do sistema. Isto deve ser uma condição temporária.

504 Gateway Time-Out
É caracterizado por erros particulares do site em questão. Pode ser que o site esteja em manutenção ou não exista.

505 HTTP Version not supported
A maioria dos browsers assumem que os servidores de rede suportam versões 1.x do protocolo HTTP. Na prática, as versões muito antigas como a 0.9 são pouco utilizadas atualmente, não apenas porque eles fornecem pouca segurança e desempenho mais baixo do que as versões mais recentes do protocolo. Então, se acontecer esse erro no seu navegador de rede, a única opção é fazer o upgrade do software do servidor de rede. Se a versão da solicitação 1.x falhar, pode ser porque o servidor de rede está suportando versões incorretas do protocolo 1.x, em vez de não suportá-las.

Referências
 «303 See Other — httpstatuses.com». httpstatus.es (em inglês). Consultado em 13 de setembro de 2018
 «308 Permanent Redirect — httpstatuses.com». httpstatuses.com (em inglês). Consultado em 13 de setembro de 2018
