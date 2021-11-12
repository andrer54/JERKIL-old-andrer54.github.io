<img align="center" width="440" src="https://pngimg.com/uploads/github/github_PNG15.png" >

### ESSE MATERIAL VAI AJUDAR A INSTALAR GIT E PUBLICAR NO GITHUB UM PROJETO;  

Para checar se o Git já está instalado:

    git version
    
Amigo, Se não, ja instala via terminal 
  
    sudo apt install git
    
Se vc instalou agora, então configura ele assim:  
No terminal:


    git config --global user.name "seu-nome"
    git config --global user.email "seu-email"

Veja se está configurado:

    git config --list    
    

---------------------------------
    
## trabalhando com o git

não perde tempo, abre o terminal na pasta do teu projeto e já cria teu repositório local com o comando  

     git init
      
 Isso inicializa um repositório git no seu projeto  
 
Agora vai no teu github, cria um repositorio lá
No seu perfil do GitHub clique em “new repo” de um nome (exemplo: novo-repo), escolha a opção “público”, e clique em “Criar repositório”.


Agora para treino, vamos adicionar um arquivo pelo terminal com o comando: 

     touch README.MD

----------

## agora voltemos ao git
DIGITE: 
     
     git status

Isso irá listar todos os arquivos no seu diretório de trabalho.


Então digite:

     git add .

Isso adiciona todos os seus arquivos e alterações numa área temporária.

Então digite:

     git commit -m "primeiro commit"

Isso commita todos os seus arquivos, adicionando a mensagem “primeiro commit”

aGORA CHEGOU A HORA DE ENVIAR TUDO PARA O GITHUB, MAS ANTES VAMOS INFORMAR ONDE FICA O REPOSITÓRIO ONLINE, VEJA:

     git remote add origin https://github.com/teu_usuario/teu-repo.git

Isso cria um vinculo remoto, ou conexão chamado “origin” apontando para o seu repositório GitHub que você acabou de criar.

agora cheg9ou o momento mágico, Então digite:

     git push -u origin main

Isso envia seus commits para sua branch “main” no GitHub



Se quiser continuar fazendo alterações e as enviando para o GitHub, você precisará utilizar os três seguintes comandos:

     git add .
     git commit -m "sua mensagem sensata aqui"
     git push origin main

