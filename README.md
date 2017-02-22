# App Tools Examples

[![Build Status](https://travis-ci.org/robsonbittencourt/app-tools-examples.svg?branch=master)](https://travis-ci.org/robsonbittencourt/app-tools-examples/)  [![Coverage Status](https://coveralls.io/repos/github/robsonbittencourt/app-tools-examples/badge.svg?branch=master)](https://coveralls.io/github/robsonbittencourt/app-tools-examples?branch=master)  [![codebeat badge](https://codebeat.co/badges/d9ae8b73-dc99-40ff-8108-2e29b2f1dc7d)](https://codebeat.co/projects/github-com-robsonbittencourt-app-tools-examples) [![Docker Stars](https://img.shields.io/docker/stars/robsonbittencourt/old-cars-api.svg)](https://hub.docker.com/r/robsonbittencourt/old-cars-api/)  [![Docker Pulls](https://img.shields.io/docker/pulls/robsonbittencourt/old-cars-api.svg)](https://hub.docker.com/r/robsonbittencourt/old-cars-api/) [![microbadger](https://images.microbadger.com/badges/image/robsonbittencourt/old-cars-api.svg)](https://microbadger.com/images/robsonbittencourt/old-cars-api)

> Some examples of tools that can be used in open source projects

##Travis CI

1 - Criar conta no Travis CI

2 - Ativar o build do repositório

3 - Criar o arquivo de configuração .travis.yml
    O arquivo informa que o build é de uma aplicação Java, e que a versão 8 do Java deve ser utilizada.
    Após ele informa o comando Maven que deve ser utilizado para rodar o build
    O último passo é só um adicional para que o Travis faça cache das depêndencias, tornando o build mais rápido.
    
4 - Commitar o arquivo e acompanhar o build

## Coveralls

1 - Criar conta no Coveralls

2 - Ativar o monitoramento do repositório

3 - Adicionar plugin do cobertura e do coveralls no pom.xml
    <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>cobertura-maven-plugin</artifactId>
        <version>2.7</version>
        <configuration>
            <instrumentation>
                <ignoreTrivial>true</ignoreTrivial>
            </instrumentation>
            <formats>
                <format>html</format>
                <format>xml</format>
            </formats>
        </configuration>
    </plugin>
    <plugin>
        <groupId>org.eluder.coveralls</groupId>
        <artifactId>coveralls-maven-plugin</artifactId>
        <version>4.3.0</version>
    </plugin>

Para outras linguagens verificar em: https://coveralls.zendesk.com/hc/en-us

3 - Adicionar um passo depois do build no arquivo de configuração do travis

4 - Adicionar token do coveralls nas configurações do build do travis

5 - Commitar e verificar a cobertura no coveralls

## Codebeat
https://codebeat.co


## Docker Hub

1 - Criar conta no Docker Hub

2 - Criar o repositório no Docker Hub

3 - Criar o Docker file

4 - Adicionar passo para subir imagem no arquivo de confiuração do Travis
    - Neste exemplo vamos subir a imagem com a tag igual o número da versão no arquivo pom.xml
    - Para recuperar a versão precisamos instalar o pacote xml2 para conseguir ler pom.xml e extrair a versão 
    - Também iremos subir com a tag latest

5 - Adicionar credencias do Docker Hub nas configuração do build no Travis


## Heroku

1 - Criar conta no Heroku

2 - Baixar a Heroku CLI - https://devcenter.heroku.com/articles/getting-started-with-java#set-up

3 - Fazer login no heroku - heroku login

4 - Criar um projeto no Heroku - heroku create

5 - Fazer o deploy no Heroku - git push heroku master

6 - Abrir a aplicação - heroku open

7 - Alterar o nome da aplicação nas configurações

8 - Como o nome foi alterado é necessário alterar o remote do Heroku   
    git remote rm heroku
    git remote add heroku https://git.heroku.com/old-cars-api.git - o repositório foi copiado do settings do Heroku