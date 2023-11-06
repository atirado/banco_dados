## comandos de banco de dados

### criar database
* local para criar as tabelas do sistema
```
create database NOME_DATABASE;
```
### executar o comando
```
Ctrl + enter
```
### selecionar database 
```
use NOME_DATABASE
```
<hr>

## projeto site Ecomerce
* tabela de usuarios
* tabela de produtos 
* tabela de carrinho de compras

### Criar tabela de usuários 
```
Create table usuarios (
  id int not null auto_increment,
  nome varchar(120) not null,
  email varchar(120) not null,
  senha varchar(120) not null,
  primary key(id) 
);
```
* id: idetificador de cada registro 
* not null: campo obrigatorio, não pode ser nulo
* auto_increment: soma +1 no ulimo registro de id 
* varchar(120): campo de texto com 120 caracteres

### criar tabela de produtos 
```
crate table produtos(
    id int not null auto_increment,
    modelo varchar(120),
    nome varchar(120) not null,
    valor first not null
    primary key(id)
);
```

### criar tabela de carrinho
```
create table carrinho(
    id int not null auto_increment,
    id_usuario int not null,
    id_produto int not null,
    primary key(id),
    foreign key (id_usuario) references usuarios(id),
    foreign key(in_produto) references protudo(id)
);
``` 
* foreign key: chave estrangeiro que recebe a referencia de outra tabela 
* references: atributo para dfinir a tabela e o campo estrangeiro 

### inserir usuarios
```
insert into usuarios(nome, email, senha) values('Renato Gaucho', 'teste@teste.com', 'secret');
```

### inserir produtos 
```
insert into produtos(modelo, nome, valor ) values('nike', 'camiseta', 129,90);
```

### inserir carrinho 
```
insert into carinho(id_usuario, id_produtos) values(43,234)
insert into carinho(id_usuario, id_produtos) values(43,120)
insert into carinho(id_usuario, id_produtos) values(43,6)
insert into carinho(id_usuario, id_produtos) values(43,234)
insert into carinho(id_usuario, id_produtos) values(43,234)
```

### listar todas as clunas de usuarios
```
select * from usuarios;
```

### listar os nomes e email dos usuarios 
```
select nome, email from usuarios;
```

### listar usuarios pelo id
```
select * from usuario where id = 23;
```

### verificar produtos no carriho pelo id do usuario 
```
select p. nome 
from produtos, carrinho c
where c.id_usuario = 23 AND p.id = c.id_produto;
```