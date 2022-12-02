## Desafio - Criando Pipeline de CI/CD com Cloud Build e Terraform

1. Utilize o git https://github.com/digitalinnovationone/terraform-gcp/tree/main/terraform-exemplo2 para configurar a trigger do Cloud Build.
 - Realizando Fork do repositório GitHub da DIO para usá-lo no desafio.
   [fork](/desafio_pipeline-cicd-cloud-build_terraform/fork_repositorio_github.png)

 - Acessa o recurso **Cloud Build** e na opção do menu selecionar **Gatilhos (ou Triggers)** em seguinda clicar em **Criar um Gatilho**
   [Criar Gatilho](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho.png)

 - Configura fonte do repositório do GitHub
   1. Criar Nome, Região, Descrição [Identificação Trigger](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho.png)
   2. Conexão com repositório do GitHub 
      2.1 [Conectar novo Repositório](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte.png)
      2.2 [Selecionar Origem Desejada (Ex. GitHub)](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte2.png)
      2.3 [Selecionar repositório desejado](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte3.png)
      2.4 [Apresenta repositório selecionado](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/criar_gatilho_Fonte4.png)
    3. Gatilho criado com sucesso [gatilho criado](/desafio_pipeline-cicd-cloud-build_terraform/Triggers/gatilho_criado.png)
   
2. Edite o script para trocar o nome da máquina para cloudbbuildterraform.
  - Realizar alteração no script para alterar nome da máquina a ser instânciada e, também do projeto e bucket a ser utilizado para carregar o Terraform.
    1. [Alterações realizadas no script](/desafio_pipeline-cicd-cloud-build_terraform/Script/edita_script.png)
    2. [Confirmação das alterações](/desafio_pipeline-cicd-cloud-build_terraform/Script/edita_script2.png)

3. Salve os arquivos do Estado no Google Cloud Storage.
  
  - Para criar o Storage para arquivo o state do Terraform é preciso.
    1. Criar um Bucket para Google Cloud Storage
      [Nomear seu bucket](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage.png) com um nome que seja fácil de vincular ao processo.
      [Selecionar o Local](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Local.png) onde será criado o Bucket.
      [Selecionar Classe de Armazenamento](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Armazenamento.png)
      [Selecionar Controle e Acesso](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Acesso.png) ao bucket
      [Selecionar forma de proteção](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Protecao.png)
      [Criar o Bucket](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Criar.png)
      [Bucket Criado com Sucesso](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/cria_cloud-storage_Criado.png)
    2. Será necessário criar um script para indicar ao Terraform o Bucket para guardar o Estado do Projeto. 
      [Arquivo gravação do Estado](/desafio_pipeline-cicd-cloud-build_terraform/Google_Cloud_Storage/script_state_terraform.png) a ser criado no projeto.
    3. [Altera script do Backend "gcs"](/desafio_pipeline-cicd-cloud-build_terraform/Script/edita_script3.png)

Submeta o print de cada etapa de configuração do Pipeline .