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

name: Pipeline Ci/CD - Prod

on:
  push:
    branches:
      - main
  workflow_dispatch:

### Professor Douglas Morais
#### Desenvolvido com NodeJS | GamaAcademy
