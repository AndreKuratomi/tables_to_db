# tables_to_db

- [Traduções](#traduções)
- [Sobre](#sobre)
- [Instalação](#instalação)
- [Como utilizar este módulo](#como-utilizar-este-módulo)
- [Referências](#referências)

<br>

## Traduções

- [Inglês / English](./.multilingual_readmes/README_en-uk.md)
- [Português brasileiro / Brazilian portuguese](https://github.com/AndreKuratomi/tables_to_db/tree/pt_br)

<br>

## Sobre

<b>tables_to_db</b> é um módulo <strong>python</strong> que automatiza a inserção de tabelas <strong>csv</strong> em um banco de dados <strong>MySQL</strong> usando <strong>PyMySQL</strong> e <strong>Pandas</strong>, dispensando, assim, inserção manual via interface MySQL Workbench, por exemplo.

Este módulo pode ser acoplado a qualquer projeto maior que necessite desta funcionalidade.

<br>

## Instalação

<h4>0. Para a utilização deste módulo, primeiramente é necessário já ter instalado na própria máquina:</h4>

- O versionador de código <b>[Git](https://git-scm.com/downloads)</b>.

- A linguagem de programação <b>[Python](https://www.python.org/downloads/)</b>.

- <p> E versionar o diretório escolhido para receber o clone deste módulo:</p>

```
git init
```

<br>
<h4>1. Fazer o clone do reposítório <b>tables_to_db</b> na sua máquina pelo terminal do computador ou pelo do IDE:</h4>

```
git clone https://github.com/AndreKuratomi/tables_to_db.git
```

WINDOWS:

Obs: Caso apareca algum erro semelhante a este: 

```
unable to access 'https://github.com/AndreKuratomi/tables_to_db.git': SSL certificate problem: self-signed certificate in certificate chain
```

Configure o git para desabilitar a certificação SSL:

```
git config --global http.sslVerify "false"
```
<br>
<p>Entrar na pasta criada:</p>

```
cd tables_to_db
```
<br>

<h4>2. Após feito o clone do repositório, instalar:</h4>

<h5>O ambiente virtual* e atualizar suas dependências com o seguinte comando:</h5>

LINUX:
```
python3 -m venv venv --upgrade-deps
```

WINDOWS:
```
py -m venv venv --upgrade-deps
```

Caso seja retornado algum erro semelhante a este basta seguir as instruções:

```
The virtual environment was not created successfully because ensurepip is not
available.  On Debian/Ubuntu systems, you need to install the python3-venv
package using the following command.

    apt install python3.10-venv

You may need to use sudo with that command.  After installing the python3-venv
package, recreate your virtual environment.
```

*É interessante seguir esta prática porque diferentes projetos exigem diferentes dependências. Um ambiente virtual nada mais é do que um ambiente separado da sua máquina. Caso contrário, a máquina do usuário pode se encher de dependências que serão utilizadas apenas em um único projeto.

<h5>Ative o seu ambiente virtual com o comando:</h5>

LINUX:
```
source/venv/bin/activate
```

WINDOWS:

No sistema operacional Windows é necessário antes configurar o Execution Policy do PowerShell:

```
Get-ExecutionPolicy # para verificar o tipo de política de execução
Set-ExecutionPolicy RemoteSigned # para alterar o tipo de política se o comando acima mostrar 'Restricted'
```
Obs: Eventualmente, pode ser necessário abrir o PowerShell como administrador.

E enfim ativar o ambiente virtual com o comando abaixo:

```
.\env\Scripts\activate
```


<h5>Instalar suas dependências:</h5>

```
pip install -r requirements.txt
```

WINDOWS:

Caso seja retornado algum erro semelhante a este:

```
ERROR: Could not install packages due to an OSError: [Errno 2] No such file or directory: 'C:\\Users\\andre.kuratomi\\OneDrive - Empresa\\Área de Trabalho\\tables_to_db\\tables_to_db\\env\\Lib\\site-packages\\jedi\\third_party\\django-stubs\\django-stubs\\contrib\\contenttypes\\management\\commands\\remove_stale_contenttypes.pyi'
HINT: This error might have occurred since this system does not have Windows Long Path support enabled. You can find information on how to enable this at https://pip.pypa.io/warnings/enable-long-paths
```

Rode no <b>cmd</b> como adminstrador o seguinte comando:

```
reg.exe add HKLM\SYSTEM\CurrentControlSet\Control\FileSystem /v LongPathsEnabled /t REG_DWORD /d 1 /f
```
<br>

<h4>4. Criar o arquivo <b>.env</b> no diretório raiz:</h4>

```
touch .env
```

Dentro dele precisamos definir nossas variáveis de ambiente tendo como referência o arquivo <b>.env.example</b>:

```
MYSQL_USER=user
MYSQL_PASSWORD=password
```

Obs: As informações contidas no arquivo .env não devem ser compartilhadas. O arquivo já consta no <b>.gitignore</b> para não constar no repositório github.

<br>


<h4>3. Abrir o módulo no seu IDE:</h4>

```
code .
```

<br>

## Como utilizar este módulo

O módulo <b>tables_to_db.insert_tables_to_a_db()</b> tem dois parâmetros: 'db' e 'tables_path'.

Ele foi originalmente desenvolvido para um projeto que utilizava <b>MySQL</b> (db) e tabelas <b>CSV</b> localizadas numa determinada pasta (tables_path). Este módulo veio em substituição à inserção manual dessas tabelas no MySQL usando <b>MySQL Workbench</b>, economizando tempo.

Então num projeto este módulo pode ser simplesmente instanciado assim:

```
db = 'my_mysql_database'
tables_path = '/path/to/csv/tables'

insert_tables_to_a_db(db, tables_path)
```

<br>


## Referências

- [Git](https://git-scm.com/downloads)
- [MySQL](https://https://www.mysql.com/)
- [Pandas](https://pandas.pydata.org/docs/)
- [Python](https://www.python.org/downloads/)
- [PyMySQL](https://pypi.org/project/PyMySQL/)
  
