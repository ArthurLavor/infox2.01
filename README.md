
# ☕ Java MySQL - Sistema OS
Sistema OS é um sistema desktop(Windows, Linux ou MAC) para gestão de ordem de serviços de uma assistência técnica de computadores, notebooks e periféricos.

## Instruções para instalação e uso do aplicativo

### Instalação do banco
1) Iniciar os serviços Apache e MySQL no XAMPP.

2) No navegador de internet digite: **localhost/dashboard** e selecione no menu: **phpMyAdmin** conforme indicado na imagem.

3) Crie um novo banco de dados de nome **dbinfox** 

4) Na aba SQL, copie e cole o código abaixo e execute. (Passos 1,2 e 3)

~~~sql
create table tbusuarios(iduser int primary key,usuario varchar(15) not null,fone varchar(15),login varchar(15) not null unique,senha varchar(250) not null,perfil varchar(20) not null);
insert into tbusuarios(iduser,usuario,login,senha,perfil) values(1,'Administrador','admin',md5('admin'),'admin');
create table tbclientes(idcli int primary key auto_increment,nomecli varchar(50) not null,endcli varchar(100),fonecli varchar(15) not null,emailcli varchar(50) unique);
create table tbos(os int primary key auto_increment,data_os timestamp default current_timestamp,tipo varchar(15) not null,situacao varchar(20) not null,equipamento varchar(150) not null,defeito varchar(150),servico varchar(150),tecnico varchar(30),valor decimal(10,2),idcli int not null,foreign key(idcli) references tbclientes(idcli));
~~~

### Instalação do aplicativo
1) Em Releases faça o download do arquivo **dist.zip**
2) Descompactar e executar o arquivo **prjinfoX.jar** Verifique na tela de login o ícone que representa o banco de dados conectado. Se estiver com erro (conforme indicado na figura) verifique o XAMPP e revise novamente os passos 1 a 4 da instalação do banco.
3) Se tudo estiver OK você pode iniciar fazendo o login com o usuário **admin** e a senha **admin** (esta senha pode ser alterada posteriormente). Ao logar o sistema direciona para tela principal onde podem ser cadastrados novos usuários, clientes e OS. O sistema permite também a emissão de relatórios.

## Tutorial passo a passo para desenvolver este projeto do "zero"
Tecnologias que são abordadas neste tutorial:
- Criação de banco de dados e tabelas no MySQL
- CRUD (Create Read Update e Delete)
- IDE Netbeans
- Java SE
- JDBC (Java Database Connectivity)
- Validação de dados
- Uso do framework iReport para gerar relatórios

### Bibliotecas
[atxy2k](http://atxy2k.github.io/RestrictedTextField/)

[driver MySQL](https://dev.mysql.com/downloads/connector/j/)

[rs2xml](https://sourceforge.net/projects/finalangelsanddemons/files/rs2xml.jar/download)
### Ferramentas
[openJDK 8 (LTS)](https://adoptopenjdk.net/)

[NetBeans IDE 8.2](https://filehippo.com/download_netbeans/8.2/)

[iReport-5.6.0](https://sourceforge.net/projects/ireport/)

[Inno Setup](https://jrsoftware.org/isinfo.php)

