Padaria App
Um aplicativo web para gerenciar produtos de uma padaria.

Descrição
O Padaria App é um aplicativo web desenvolvido em Flask que permite gerenciar produtos de uma padaria. Com ele, você pode cadastrar, editar, deletar e listar produtos, além de realizar buscas por nome.

Funcionalidades
Cadastrar produtos com nome, descrição, ingredientes, origem e imagem
Editar produtos existentes
Deletar produtos
Listar todos os produtos
Realizar buscas por nome
Tecnologias Utilizadas
Flask
Flask-SQLAlchemy
SQLite
Instalação
Clone o repositório: git clone https://github.com/seu-usuario/padaria-app.git
Instale as dependências: poetry install
Inicie o aplicativo: poetry run python app.py
Uso
Acesse o aplicativo em http://localhost:5000
Clique em "Cadastrar Produto" para criar um novo produto
Clique em "Listar Produtos" para ver todos os produtos cadastrados
Clique em "Editar" para editar um produto existente
Clique em "Deletar" para deletar um produto


O código do arquivo app.py é um aplicativo web desenvolvido com o framework Flask, que utiliza o banco de dados SQLite para armazenar informações de produtos. Aqui está uma análise detalhada do código:

Importações

O código começa importando as bibliotecas necessárias:

Flask: o framework web Flask
render_template: uma função do Flask para renderizar templates HTML
SQLAlchemy: uma biblioteca para trabalhar com bancos de dados relacionais
request: uma função do Flask para lidar com requisições HTTP
os: uma biblioteca para trabalhar com o sistema operacional
redirect: uma função do Flask para redirecionar requisições
Configuração do aplicativo

O código configura o aplicativo Flask com o nome app e define a URI do banco de dados SQLite como sqlite:///padaria.db. Além disso, inicializa o objeto db da biblioteca SQLAlchemy.

Definição da classe Product

A classe Product é definida para representar um produto no banco de dados. Ela tem os seguintes atributos:

id: um identificador único para o produto (chave primária)
nome: o nome do produto
descricao: a descrição do produto
ingredientes: os ingredientes do produto
origem: a origem do produto
imagem: o nome da imagem do produto
A classe Product também tem um método __init__ para inicializar os atributos do produto.

Rotas do aplicativo

O código define várias rotas para o aplicativo:

/: a rota raiz, que renderiza o template index.html
/listar_produtos: uma rota para listar todos os produtos, que pode ser acessada via GET ou POST. Se for uma requisição POST, busca produtos com base no termo de pesquisa fornecido.
/cadastrar_produto: uma rota para cadastrar um novo produto, que pode ser acessada via GET ou POST. Se for uma requisição POST, salva o produto no banco de dados e redireciona para a rota /listar_produtos.
/editar_produtos/<int:id>: uma rota para editar um produto existente, que pode ser acessada via GET ou POST. Se for uma requisição POST, atualiza o produto no banco de dados e redireciona para a rota /listar_produtos.
/deletar_produto/<int:id>: uma rota para deletar um produto existente, que pode ser acessada via GET.
Funções auxiliares

O código define algumas funções auxiliares:

render_template: uma função para renderizar templates HTML
redirect: uma função para redirecionar requisições
db.create_all: uma função para criar as tabelas do banco de dados
Execução do aplicativo

O código executa o aplicativo Flask com o comando app.run(debug=True), que inicia o servidor de desenvolvimento do Flask em modo de depuração.

Em resumo, o código do arquivo app.py é um aplicativo web que permite cadastrar, listar, editar e deletar produtos em um banco de dados SQLite, utilizando o framework Flask e a biblioteca SQLAlchemy.
