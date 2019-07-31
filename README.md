Derby
=====

Apache Derby é um sistema de gerenciamento de banco de dados relacional Java que pode ser embutido em programas Java e usado para processamento de transações online.

Instalação
----------

Toda a instalação é feita em **root**

### Debian

Instale o pacote derby-tools com o comando:

`apt-get install derby-tools`

### CentOS

Instale o wget com o comando:

`yum install wget`

Baixe o db-derby-10.12.1.1-bin.tar.gz com o comando:

 ```
wget http://ftp.unicamp.br/pub/apache//db/derby/db-derby-10.12.1.1/db-derby-10.12.1.1-bin.tar.gz -O db-derby-10.12.1.1-bin.tar.gz
```

Crie o diretório Apache dentro de opt com o comando:

`mkdir /opt/Apache`

Copie o db-derby-10.12.1.1-bin.tar.gz para o diretório /opt/Apache com o comando:

`cp db-derby-10.12.1.1-bin.tar.gz /opt/Apache cd /opt/Apache`

Estando no diretório /opt/Apache extraia o conteúdo do db-derby-10.12.1.1-bin.tar.gz com o comando:

`tar -xvzf db-derby-10.12.1.1-bin.tar.gz`

Baixe o java com o comando:

 ```
wget http://javadl.oracle.com/webapps/download/AutoDL?BundleId=207218 -O java32.rpm
wget http://javadl.oracle.com/webapps/download/AutoDL?BundleId=207220 -O java64.rpm
```

Instale o java com o comando:

`rpm -i arquivo.rpm`

Exporte as variáveis com os comandos:

 ```
export DERBY_INSTALL=/opt/Apache/db-derby-10.12.1.1-bin
export DERBY_HOME=/opt/Apache/db-derby-10.12.1.1-bin
export CLASSPATH=$DERBY_INSTALL/lib/derby.jar:$DERBY_INSTALL/lib/derbytools.jar:.
```

Configure o derby com os comandos:

 ```
cd $DERBY_INSTALL/bin
. setEmbeddedCP
```

Testes
------

Chame os comandos:

### Debian

`ij`

### CentOS

`java org.apache.derby.tools.ij`

 ```
CONNECT 'jdbc:derby:firstdb;create=true';
CREATE TABLE FIRSTTABLE (ID INT PRIMARY KEY, NAME VARCHAR(12));
INSERT INTO FIRSTTABLE VALUES (10,'TEN'),(20,'TWENTY'),(30,'THIRTY');
```