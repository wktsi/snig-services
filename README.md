# Serviço de Pesquisa utilizado no âmbito do SNIG

Módulo que adiciona ao GeoNetwork a funcionalidade de limitar as pesquisas rápidas ao catálogo (*autocomplete*) a determinados tipos de registos de metadados (*dataset* ou *series*, por exemplo). O catálogo do SNIG tem como lógica de funcionamento a pesquisa apenas a Conjuntos de Dados Geográficos e Séries de Conjuntos de Dados Geográficos, sendo a informação relativa aos respectivos serviços geográficos (visualização e/ou descarregamento) disponibilizada através da ficha de metadados de cada recurso. Este comportamente teve como objetivo reduzir o número de registos existente no catálogo, de forma a promover uma pesquisa mais fácil e rápida da informação. 

## Instalação do módulo

### Versão do GeoNetwork a utilizar com este módulo

A utilização deste módulo exige que seja utilizada a versão adaptada do GeoNetwork para o SNIG (https://github.com/ricardogsena/core-geonetwork.git). Esta adaptação foi desenvolvida com base no GeoNetwork 3.4.x.

### Adicionar o módulo ao código fonte

A versão adaptada do GeoNetwork para o SNIG adiciona automaticamente este módulo como um submódulo do projeto, pelo que apenas é necessário seguir as instruções de instalação dessa versão.

Apenas como informação complementar, descreve-se em seguida o modo como se procedeu à integração deste módulo na versão adaptada do GeoNetwork para o SNIG:

1. Mudar para a directoria raiz do projeto
```
cd core-geonetwork
```
2. Adicionar o módulo como submódulo do projeto 
```
git submodule add -b 3.4.x https://github.com/ricardogsena/snig-services.git snig-services
```
3. Adicionar o módulo ao ficheiro pom.xml (core-geonetwork/pom.xml)
```
<modules>
    ...
    <module>snig-services</module>
    ...
</modules>
```
4. Adicionar a dependência ao módulo *web* (core-geonetwork/web/pom.xml):
```
<dependency>
  <groupId>${project.groupId}</groupId>
  <artifactId>snig-services</artifactId>
  <version>${project.version}</version>
</dependency>
```
