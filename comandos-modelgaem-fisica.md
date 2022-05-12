# comando SQL para modelagem física

## Criar banco de dados
CREATE DATABASE  vendas_guilhermes CHARACTER SET utf8mb4;

## Entrar no banco de dados criado
US DATABASE vendas_guilhermes;

## Cria Tabela fabricantes
CREATE TABLE fabricantes(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY , 
    nome VARCHAR(45) NOT NULL

);

## Cria Tabela Produtos
CREATE TABLE produtos(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
    preco DECIMAL(8,2) NOT NULL,
    quantidade SMALLINT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricante_id INT NOT NULL
);
## Alterando a tabela para criar relacionamento por meio da chave estrangeira (Modificação da tabela)
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricantes(id);


# Crud Create(INSERT), READ ler dados (select), UPDATE atualizar dados(update), Delete 


## Comando para inserir dados em uma tabela
INSERT INTO nome_tabela
    (campo1, campo2, campo3,)
    VALUES(valor1, valor2, valor3);


## Select utilizado para taferas de consulta de dados no banco.
SELECT lista_de_campos FROM lista_de_tabela
    WHERE condições: 


## UPDATE responsavel por fazer alterações nos valores dos registros de uma tabela
 UPDATE nome_tabela
    SET campo1=valor1 WHERE condições

