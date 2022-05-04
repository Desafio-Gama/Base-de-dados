# Base-de-dados

```sql
CREATE TABLE cliente (
	id serial PRIMARY KEY,
	name VARCHAR ( 50 ) NOT NULL,
	email VARCHAR ( 255 ) UNIQUE NOT NULL
);


CREATE TABLE produto (
	id serial PRIMARY KEY,
	nome VARCHAR ( 50 ) NOT NULL,
	descricao TEXT NOT NULL,
	quantidade INTEGER NOT NULL,
	data_cadastro DATE,
	preco DECIMAL NOT NULL
);

CREATE TABLE pedido (
	id serial PRIMARY KEY,
	id_cliente INTEGER,
	data_pedido DATE,
	preco DECIMAL NOT NULL,
	FOREIGN KEY(id_cliente) REFERENCES cliente(id)
);


CREATE TABLE pedido_produto (
	id serial PRIMARY KEY,
	id_pedido INTEGER,
	id_produto INTEGER,
	quantidade INTEGER,
	FOREIGN KEY (id_pedido) REFERENCES pedido(id),
	FOREIGN KEY (id_produto)	REFERENCES produto(id)
);
```
