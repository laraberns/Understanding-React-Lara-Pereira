# Git e GitHub
~~~
- Software para controle de versionamento de código;
- Existem dois tipos de Software de Controle de Versão (VCS): 
   - Centralizado
   -  Distribuído (Ex: Git)
- Algumas das vantagens de utilizar VCS são: segurança e facilita no trabalho em equipe.
~~~

## Comandos do Git
- Verificar a versão do Git e se está instalado:
   - git --version
- Configurar usuário e e-mail cadastrado (para máquina toda):
   - git config --global user.email you@example.com
   - git config --global user.name "Your Name"  
- Verificar as configurações:
   - git config user.name
   - git config user.email
- Verificar as configurações:
   - git config user.name
   - git config user.email
- Iniciar repositório:
   - git init 
- Verificar status:
   - git status 
- Adicionar arquivos na área de staged:
   - git add nome_arquivo
   - git add . 
- Commitar arquivos:
   - git commit -m "comentário"
- Mapear repositório remoto:
   - git remote add origin "http://...url do rep remoto..." 
- Enviar alterações para o rep. remoto:
   - git push -u origin master
   - git push 
- Atualizar rep. local de acordo com rep. remoto:
   - git pull
- Renomear branch:
   - git branch -M main 
- Clonar rep. remoto:
   - git clone "http://...url do rep remoto...
- Removendo arquivos:
   - git rm --> remove do repositório (<mark>DELETA</mark> arquivo)
   - git rm --cached <file> --> arquivo deixa de ser monitorado (untracked)
- Utilizar Add junto com Commit (stage e commita):
   - git commit -am "criando commit"
- Verificar alterações:
   - git log
   - git log --oneline --> forma mais resumida
- Para ignorar arquivos:
   - Crie arquivo ".gitignore"
   - Arquivos dentro do ".gitignore" o Git ignora e não rasteria
- Verificar diferenças entre commits:
   - git diff <cod. do commit> <cod. do commit2>
- Descatar alterações antes de Add:
   - git checkout <file>


<p style="text-align: center;">
<a href="https://www.entra21.com.br/"> 
<img src= "https://cdn.sonicadigital.com.br/entra21/storage/header/257/original-61f8610472d4f.png"
</a>
</p>