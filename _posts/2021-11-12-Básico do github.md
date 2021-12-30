
<div>
<img align="center" width="300" src="https://pngimg.com/uploads/github/github_PNG15.png" >
 -  TUTORIAL PARA INSTALAR GIT E PUBLICAR NO GITHUB UM PROJETO;  
</div>

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
     git commit -m "sua mensagem aqui"
     git push origin main

-----------

## Agora vamos falar um pouco sobre BRANCH

Esse comando lista os branches do projeto

    git branch
    
Esse abaixo, cria um branch
    
    git branch umNovoBranch  
    
 
-----------------------------

agora que vc criou um novo branch, digite novamente
     
     git branch
          *main  
           umNovoBranch
 
observe que o * informa em  qual branch estamos utilizando(conectados)




    git checkout umNovoBranch

então novamente;
     
     git branches
                main
               *umNovoBranch
               
 
agora estamos trabalhando no branch umNovoBranch.


----------

## Merge
ex: o trabalho que fizemos no novo branch está pronto, então agora vou dar umas dicas e ensinar a "mergir" de maneira adequada.

dica 1:
face o merge do branch principal para o seu novo branch, para garantir que sua feature funcione quando vc mergir no ramo principal

     git checkout nova_feature #volte para o branch da feature
     git merge main #coloque o main dentro do teu branch novo

teste o app utilizando o seu branch, bem melhor que algo quebrar dentro do 'main'...
funcionou?
não -> debbuging
sim -> faça o merge para o ramo principal
      
       git checkout main
       git merge nova-feature
       
--------
## deletando branch
em algumas ocasiões a lista de branches pode ser grande, e algumas já inuteis... 

     git branch -d velho_branch
se mostrar algum erro, é o sistema te avisando que tem algumas modificações no velho-branch que não foram 'mergidas' no original...
então você pode , entrar no velho-branch, commitar, voltar ao branch atual e mergir... o simplesmente forçar o delete com o comando:

     git branch -D velho_branch # 
     
esse -D é um atalho para --delete --force


-------------------------
### Comentários sobre REBASE

    git rebase
    
esse comando, em um fluxo normal de git, vai juntar todos branches em um unico branch e uma única linha do tempo. 
Em algumas situações, tenho achado útil qndo o trabalho realizado por apenas um programador. Quando ele deseja simplificar a linha do tempo das modificações.  
  
Este comando não é recomendado para repositorios publicos, open source, com colaboração de terceiros...  
a menos que vc seja bem experiente (saiba realmente o que está fazendo...rs...)  
Pois, haverá potencial chances de experimentar uma grande confusão e problemas futuros


--------------------
## Trabalhando com branch no github
(em construção)

