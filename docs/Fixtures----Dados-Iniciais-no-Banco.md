# Fornecendo dados iniciais para modelos

<p align="justify">Com o decorrer do semestre o software que é desenvolvido na matéria de GPP/MDS vai criando corpo e ficando maior a cada dia. A cada ciclo de entrega do software são adcionadas novas funcionalidades, novos atributos ao que já tinha. E é necessário sempre ter um banco de dados populado para ajudar os desenvolvedores a  visuzlizar o que está sendo feito, ajudando-os a ver como ficará melhor e o que possívelmente está errado.</p>

<p align="justify">Por isso se viu a necessidade de popular o banco de dados com informações básicas para aplicação tomar um corpo mínimo e facilitar o trabalho dos desenvolvedores em realizar funcionalidade com esses dados. Como o grupo estava utilizando do framework Django este possibilita que seja gerado e jsons contendo as informações do banco de dados. Os jsons que foram gerados era carregado todas as vezes que o docker era construído, logo todas as vezes que a aplicação subia ela já possuia dados cadastrados.</p>

# Fixtures
<p align="justify">Uma fixture é uma coleção de dados que o Django sabe como importar para o banco de dados.</p> 

## Como criar uma fixture

<p align="justify">A maneira mais fácil de criar uma fixture se você já tem algum dado é usar o comando dumpdata que o Djanto disponibiliza para o memso. Ou, você pode escrever fixtures manualmente; “fixtures” podem ser escritas como documentos JSON, XML ou YAML (com PyYAML installed). O documentos de serialização tem mais detalhes sobre cada um destes formatos de serialização.</p>

<p align="justify">Através deste comando será possível gerar um json com dados salvo em todas classes da aplicação, esses dados serão salvo no arquivo data.json.</p>
```python 
python3 manage.py dumpdata > data.json
```
<p align="justify">Através deste comando será possível gerar um json com os dados da classe de um app espcífico , esses dados serão salvo no arquivo data.json.</p>
```python 
python3 manage.py dumpdata app > data.json
```
<p align="justify">Através deste comando será possível gerar um json com os dados de uma úncia classe de um app espcífico , esses dados serão salvo no arquivo data.json.</p>
```python 
python3 manage.py dumpdata app.classe > data.json
```


## Fixture com json
```json
[
  {
    "model": "app.class",
    "pk": 1,
    "fields": {
      "field1": "value 1",
      "field2": "value 2"
    }
  },
  {
    "model": "app.class",
    "pk": 2,
    "fields": {
      "field1": "value 3",
      "field2": "value 4"
    }
  },
]
```

## Fixture com YAML:
```YAML
- model: app.class
  pk: 1
  fields:
    field1: value1
    field2: value2
- model: app.class
  pk: 2
  fields:
    field1: value3
    field2: value4
```

## Como carregar uma fixture
<p align="justify">Para carregar os arquivos que contem os dados iniciais da aplicação é muito simples, pois o framework já disponibiliza o recurso de loaddata para isso. Por padrão o Django irá procurar dentro da pasta fixtures de cada app os arquivos para poder carregar quano se executa o loaddata.</p>

1. Criar uma pasta fixture dentro do app que deseja colocar o arquivo que contém os dados.

2. Executar o comando:
```python
python3 manage.py loaddata data.json
```
Obs: data é o nome do arquivo que foi dado a saída do comando de dumpdata.

