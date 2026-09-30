# atividades-BCD
Material desenvolvido em sala de aula

#ATIVIDADE 1

## Compra de Produtos

Projeto de banco de dados em MySQL para cadastro de clientes, produtos e vendas.

## Banco de Dados

sql
CREATE DATABASE compra_produtos;

USE compra_produtos;


 ## Tabela Cliente

```
CREATE TABLE cliente (
    id_cliente INT PRIMARY KEY AUTO_INCREMENT,
    nome_cliente VARCHAR(100),
    email VARCHAR(100),
    telefone INT
);
```

 ## Tabela Produto

```
CREATE TABLE produto (
    id_produto INT PRIMARY KEY AUTO_INCREMENT,
    produto VARCHAR(100),
    preco DECIMAL(10,2),
    qtd_vendida INT
);
```

 ## Tabela Venda

```
CREATE TABLE venda (
    id_venda INT PRIMARY KEY AUTO_INCREMENT,
    id_cliente INT NOT NULL,
    id_produto INT NOT NULL,
    data DATE,

    FOREIGN KEY (id_cliente) REFERENCES cliente(id_cliente),
    FOREIGN KEY (id_produto) REFERENCES produto(id_produto)
);
```

 ## Inserindo Clientes

```
INSERT INTO cliente(nome_cliente, email, telefone)
VALUES ("Michael Jackson", "m.jackson@gmail.com", "19908456");

INSERT INTO cliente(nome_cliente, email, telefone)
VALUES ("Loud Coringa", "l.deloude@gmail.com", "19926627");

INSERT INTO cliente(nome_cliente, email, telefone)
VALUES ("Peter Parker", "aranha@gmail.com", "19943154");

SELECT * FROM cliente;
```

 ## Inserindo Produtos

```
INSERT INTO produto(produto, preco, qtd_vendida)
VALUES ("Violao", 300.00, 5);

INSERT INTO produto(produto, preco, qtd_vendida)
VALUES ("PC Gamer", 5000.00, 10);

INSERT INTO produto(produto, preco, qtd_vendida)
VALUES ("Bolsa antifurto", 100.00, 7);

SELECT * FROM produto;
```

 ## Inserindo Vendas

```
INSERT INTO venda(id_cliente, id_produto, data)
VALUES (1, 1, "2026-09-25");

INSERT INTO venda(id_cliente, id_produto, data)
VALUES (3, 2, "2022-07-25");

INSERT INTO venda(id_cliente, id_produto, data)
VALUES (2, 3, "2000-12-25");

SELECT * FROM venda;
```

 ## Alteração

```
UPDATE produto
SET produto = "Teia"
WHERE id_produto = 3;

SELECT * FROM produto;
```

 ## Chave Única

```
ALTER TABLE produto
ADD CONSTRAINT uk_produto_unico UNIQUE (produto);

ALTER TABLE cliente
ADD CONSTRAINT uk_email_unico UNIQUE (email);
```

 ## Deletar Tabela

```
DROP TABLE produto;
```
![print 1](ativi1-bcd.drawio.png)
 ## Tecnologias

 - MySQL
- SQL


# ATIVIDADE 2
