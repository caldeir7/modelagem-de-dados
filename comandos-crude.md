# Comandos CRUDE para maniular dados

## Resumo da sigla
    C -> (INSERT, inserir dados)
    R -> (SELECT    , leitura de dados)
    U -> (UPDATE, atualizar)
    D -> (DELETE, excluir dados)

## INSERT

### Fabricantes
INSERT INTO fabricantes(nome) VALUES ("Asus")
INSERT INTO fabricantes(nome) VALUES ("Dell");
INSERT INTO fabricantes(nome) VALUES ("Apple");
INSERT INTO fabricantes(nome) VALUES ("LG");

INSERT INTO fabricantes(nome) 
VALUES ("Samsung"), ("Microsoft"), ("Brastemp");

### Produtos
INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id)
    VALUES("TV Led", 2000, 5, "TV LED 45polegadas de ultima geração", 5);
INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id)
    VALUES("Iphone XYZ", 7000, 5, "Iphone 11", 3);


INSERT INTO produtos(nome, preco, quantidade, descricao, fabricante_id) VALUES
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    7
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.',
    3
),
(
    'Xbox',
    2500,
    6,
    'Console de última geração com acesso aos melhores jogos e bla bla',
    6
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',
    1
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    6
),
(
    'Tablet Android',
    4999,
    3,
    'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB.',
    5
);

## SELECT
SELECT nome,preco FROM produtos WHERE preco < 3000;
SELECT nome,preco FROM produtos 
WHERE preco < 3000 AND preco > 2000;

SELECT nome,quantidade FROM produtos 
WHERE fabricante_id = 3 OR fabricante_id = 1, quantidade < 5;

## Mostra produtos cuja quantidade for maior que 5 e o preco menor que 2000 AND Fabricante-id para trazer somento o id Desejado
SELECT nome,preco, quantidade FROM produtos
WHERE quantidade > 5 AND preco < 2000 AND fabricante_id = 3;

## Ordem alfabética
SELECT nome, descricao FROM produtos
ORDER BY nome; -- Crescente (padrão)


SELECT nome, descricao FROM produtos
ORDER BY nome DESC; -- Decrescente 

SELECT 
    produtos.nome AS Produto, 
    fabricantes.nome AS Fabricante, 
    produtos.preco, 
    produtos.quantidade
FROM produtos INNER JOIN fabricantes
ON produtos.fabricante_id = fabricantes.id;

-- INER JOIN: comando que permite juntar duas ou mais tabelas.

-- ON: Comando para indicar a maneira como as tabelas são juntadas

-- AS: comando que permite dar um apelido para as colunas

## UPDATE
UPDATE fabricantes SET nome = 'LG do Brasl'
WHERE id = 4;

## DELETE
DELETE FROM produtos WHERE id = 5;