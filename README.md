# Desafios de Projeto

Aqui temos alguns desafios de projetos que foram realizados na plataforme GCP, abaixo o indice dos projetos que foram criados com o seu passo a passo.

## Índice

-   [Desafio - Criando Pipeline de CI/CD com Cloud Build e Terraform](#desafio---criando-pipeline-de-cicd-com-cloud-build-e-terraform)
    - [Acesse arquivo exclusivo desse desafio](/desafio_pipeline-cicd-cloud-build_terraform/README.md)
-   [Desafio - Utilizando Cloud Shell](#desafio---utilizando-cloud-shell)
    - [Acesse arquivo exclusivo desse desafio](/desafio_utilizando_cloud_shell/README.md)
-   [Desafio - Exportar Faturamento](#desafio---exportar-faturamento)
    - [Acesse arquivo exclusivo desse desafio](/desafio_exportacao_faturamento/README.md)


## Desafio - Criando Pipeline de CI/CD com Cloud Build e Terraform

1. Utilize o git https://github.com/digitalinnovationone/terraform-gcp/tree/main/terraform-exemplo2 para configurar a trigger do Cloud Build.
 - Realizando Fork do repositório GitHub da DIO para usá-lo no desafio.

   **fork do projeto do GitHub**

   ![Alt text](/desafio_pipeline-cicd-cloud-build_terraform/fork_repositorio_github.png)

 - Acessa o recurso **Cloud Build** e na opção do menu selecionar **Gatilhos (ou Triggers)** em seguinda clicar em **Criar um Gatilho**
   
   **Criar Gatilho**

   ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho.png)

 - Configura fonte do repositório do GitHub

   1. Criar Nome, Região, Descrição **Identificação Trigger**

   ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho.png)

   2. Conexão com repositório do GitHub 

      2.1 **Conectar novo Repositório**

      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte.png)

      2.2 **Selecionar Origem Desejada** (Ex. GitHub)

      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte2.png)

      2.3 **Selecionar repositório desejado**

      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte3.png)

      2.4 **Apresenta repositório selecionado**

      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte4.png)

    3. Gatilho criado com sucesso **gatilho criado**

    ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/gatilho_criado.png)
   
2. Edite o script para trocar o nome da máquina para cloudbbuildterraform.

  - Realizar alteração no script para alterar nome da máquina a ser instânciada e, também do projeto e bucket a ser utilizado para carregar o Terraform.

    1. **Alterações realizadas no script**
    
    ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Script/edita_script.png)

    2. **Confirmação das alterações**
    
    ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Script/edita_script2.png)

3. Salve os arquivos do Estado no Google Cloud Storage.
  
  - Para criar o Storage para arquivo o state do Terraform é preciso.

    1. Criar um Bucket para Google Cloud Storage

      **Nomear seu bucket** com um nome que seja fácil de vincular ao processo.
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage.png) 

      **Selecionar o Local** onde será criado o Bucket.
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Local.png)

      **Selecionar Classe de Armazenamento**
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Armazenamento.png)
      
      **Selecionar Controle e Acesso** ao bucket
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Acesso.png)
      
      **Selecionar forma de proteção**
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Protecao.png)
      
      **Criar o Bucket**
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Criar.png)
      
      **Bucket Criado com Sucesso**
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Criado.png)


    2. Será necessário criar um script para indicar ao Terraform o Bucket para guardar o Estado do Projeto. 

      **Arquivo gravação do Estado** a ser criado no projeto.
      
      ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/script_state_terraform.png)

    3. **Altera script do Backend "gcs"**
    
    ![Alt Text](/desafio_pipeline-cicd-cloud-build_terraform/Script/edita_script3.png)

Submeta o print de cada etapa de configuração do Pipeline .

## Desafio - Utilizando Cloud Shell

1. Clona repositório do GitHub para o Cloud Shell

    - Entra na repositório do GitHub e **copia o link HTTPS do repositório**
    
    ![Alt Text](/desafio_utilizando_cloud_shell/clone_repositorio/clonando_repositorio.png)

    - Executa comando *git clone <LINK REPOSITÓRIO>* para baixar **uma cópia de todo o projeto no Cloud shell**
    
    ![Alt Text](/desafio_utilizando_cloud_shell/clone_repositorio/clonando_repositorio2.png)
    - Clicar em **Abrir Editor** para acessar o **editor de código do cloud shell** abrir o diretório clonado.
    
    ![Alt Text](/desafio_utilizando_cloud_shell/clone_repositorio/editor_cloud_shell.png)

2. Rodar Aplicação Java

    - Abrir o **terminal do editor de código** e navegar até o diretório desejado
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run.png)

    - Rodar **comado mvn clean install** para inicio da **compilação do código**
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run2.png)
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run3.png)

    - **Código complilado com sucesso**
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run4.png)

    - Navegar até o diretório **target** criado após a compilação do código
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run5.png)

    - Rodar **comando de execução da aplicação java** *java -jar <NOME DO AREFATO DESEJADO>*
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run6.png)

    - Programa **executando com sucesso**
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run7.png)

    - **Abrir proxy** para execução local da aplicação
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run8.png)

    - **Aplicação rodando com sucesso**
    
    ![Alt Text](/desafio_utilizando_cloud_shell/rodando_java/java_run9.png)

    ## Desafio - Exportar Faturamento

    Neste desafio a idéia e realizar a exportação dos dados de Faturamento para o Ferramenta **Big Quer**

    1. Acessar o recurso de **Faturamento**

    ![Alt Text](/desafio_exportacao_faturamento/images/acesso_faturamento.png)

    2. Acesso no meu o recurso **Exportação de Faturamento**

    ![Alt Text](/desafio_exportacao_faturamento/images/acesso_faturamento_exportar.png)

    3. Com o projeto selecionado, no campo **Conjunto de dados**, caso não tenha um já criado, escolher a opção **CRIAR NOVO CONJUNTO DE DADOS**.

    ![Alt Text](/desafio_exportacao_faturamento/images/editar_configuracoes.png)

    4. Escolher **Local onde os dados ficarão armazenados** e **Idade máxima da tabela** tempo de permanencia do dado até o seu descarte.

    ![Alt Text](/desafio_exportacao_faturamento/images/editar_configuracoes2.png)

    4. Com o **Conjunto de dados** criado, seleciona-lo para configurar a exportação.

    ![Alt Text](/desafio_exportacao_faturamento/images/editar_configuracoes3.png)

    5. Configuração da exportação realizado com sucesso.

    ![Alt Text](/desafio_exportacao_faturamento/images/editar_configuracoes4.png)