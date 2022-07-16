# Carfinder - API

## URL do Projeto:
[Clique aqui](https://carfinder-api.herokuapp.com/)

## Para acessar o swagger:
[Clique aqui](https://carfinder-api.herokuapp.com/swagger/)

## Collections Insomnia:
[Clique aqui](Insomnia_2022-07-04.yaml)

### Projeto exclusivo Icarros <> GamaAcademy

### Publicar no Azure
---------------------

Passo 1 Criar um fork do projeto para dominio do mesmo, uso <br>
Passo 2 Provisionar dentro da Azure (App Services) <br>
	- devemos informar: resource group, nome da app (único), runtime, tamanho/config/hw/ <br>
Passo 3 Abrir repositório para a edição <br>
Passo 4 Criar pastas/arquivo para gerenciamento da pipe (.github/workflows/prod.yml) <br>

### Pipeline template
---------------------

...
name: Pipeline Ci/CD - Prod

on:
  push:
    branches:
      - main
  workflow_dispatch:


on:
  push:
    branches:
      - main
  workflow_dispatch:

  jobs:
    build-and-deploy:
      name: Iniciando build e deploy
      runs-on: ubuntu-latest
      environments: production
            steps:
      - uses: actions/checkout@master
      
      - name: Configurando a versão do NodeJS
        uses: actions/setup-node@v1
        with:
          node-version: '16.x'
      
      - name: Instalando dependências e buildando o projeto
        run: |
          npm install
          npm run build --if-preset

      - name: Publicando na Azure
        uses: azure/webapps-deploy@v2
        with:
          app-name: ${{ env.AZURE_WEBAPP_NAME }}
          publish-profile: ${{ secrets.AZURE_WEBAPP_PUBLISH_PROFILE }}
          package: .
...

### Professor Douglas Morais
#### Desenvolvido com NodeJS | GamaAcademy
