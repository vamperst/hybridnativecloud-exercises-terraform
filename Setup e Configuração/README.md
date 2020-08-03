# Setup e Configuração de ambiente


 1. Abra o console da AWS e va para o serviço `Cloud 9`.
   ![img/acharcloud9.png](img/acharcloud9.png)
1. garanta que a região que esta utilizando é `us-east-1/ Norte da Virgínia`. Você consegue ver isso no canto superior direiro da tela.
    ![img/regiao.png](img/regiao.png)
 2. Clique em `create environment`.
 3. Coloque o nome `lab-fiap` e avance.
 ![img/nomelab.png](img/nomelab.png)
 5. Deixe as configurações como na imagem a seguir:
![img/config.png](img/config.png)
 6. Caso os parametros estejam como na imagem a seguir clique em `Create Environment`
   ![img/review.png](img/review.png)
 7. A criação do ambiente pode levar alguns minutos.
![img/criando.png](img/criando.png)
 8. Após a criação clique em `abrir IDE`, caso o IDE não tenha aberto automaticamente.
   ![img/abriride.png](img/abriride.png)
9. Para os próximos comandos utilize o console bash que fica no canto inferior do seu IDE.
   ![img/bash.png](img/bash.png)
10. Execute o comando `npm install -g serverless` para instalar o serverless framework.
    ![img/installserverless.png](img/installserverless.png)
11. Execute o comando `sudo apt  install jq -y` para instalar o software que irá nos ajudar a ler e manipular Jsons no terminal
12. Execute o comando `git clone https://github.com/vamperst/hybridnativecloud-exercises-terraform.git` para clonar o repositório com os exercicios.
13. Execute o comando `cd ~/environment/hybridnativecloud-exercises-terraform/` para entrar na pasta criada pelo git
14. Execute o comando `cd Setup\ e\ Configuração/` para entrar na pasta com os scripts de Configuração.
15. Para instalar o terraform execute o comando `sh installTerraform.sh`
   ![img/terraformInstall](img/terraformInstall.png)
16. Caso queira ver o script que acabou de executar você pode navegar utilizando o IDE até o arquivo como na imagem:
   ![img/navegarArquivo.png](img/navegarArquivo.png)
17. Execute o comando `python3 -m pip install --user virtualenv` para instalar o ambiente virtual python.
18. Execute o comando para criar a chave ssh que será utilizada em todos os exercicios e já coloca-la no lugar correto.
   ```
    aws --region us-east-1 ec2 \
    create-key-pair \
    --key-name "fiap-lab" \
    | \
    jq -r ".KeyMaterial" > ~/.ssh/fiap-lab.pem   
   ```
19. Execute o comando `chmod 400 ~/.ssh/fiap-lab.pem` para que a chave tenha a permissão correta.

## >>> As etapas a seguir devem ser executadas a cada 3 horas pois as chaves sofrem alteração <<<
19. No seu navegador vá a pagina do labs.vocareum.com por onde você entrou na sua conta. 
   ![](img/vocareum.png)
20. Clique em 'Account Details'
21. Clique em 'Show' e copie o conteudo que aparece em destaque
   ![](img/clishow.png)
22.  Devolta a tela do IDE do Cloud9 clique em 'AWS Cloud9' no canto superior esquerdo e escolha 'Preferences'
   ![](img/preferencescloud9.png)
23. Escolha 'AWS SETTINGS' no menu lateral e desabilite a função 'AWS managed temporary credentials'
    ![](img/credentialsDisable.png)
24. De volta ao terminal do Cloud9 utilize o comando `rm -f ~/.aws/credentials` 
25. Utilize o comando `nano ~/.aws/credentials` para atribuir valores ao arquivo
26. Cole o conteudo da credential que copiou do vocareum
27. Salve com pressionando as teclas 'Control(CTRL) + X' e após 'Y' + enter


    

    
