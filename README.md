# tables_to_db

- [Translations](#translations)
- [About](#about)
- [Instalation](#instalation)
- [References](#references)

<br>

## Translations

- [English](https://github.com/AndreKuratomi/tables_to_db)
- [Português brasileiro / Brazilian portuguese](/.multilingual_readmes/README.pt-br.md)

<br>

## About

<b>tables_to_db</b> is a <strong>python</strong> script that automatises <strong>csv</strong> tables insertion in a <strong>MySQL</strong> database using <strong>PyMySQL</strong> an <strong>Pandas</strong>. With this a manual insertion via some interface such as MySQL Workbench, for instance, is dispensable.

This script can be easily joined to any major project that may need its functionality.

<br>

## Instalation

<h4>0. Before using this script it is first necessary to have instaled the following devices:</h4>

- The code versioning <b>[Git](https://git-scm.com/downloads)</b>.

- A <b>code editor</b>, also known as <b>IDE</b>. For instance, <strong>[Visual Studio Code (VSCode)](https://code.visualstudio.com/)</strong>.

- <p> And versioning your directory to receive the aplication clone:</p>

```
git init
```

<br>
<h4>1. Clone the repository <b>tables_to_db</b> by your machine terminal or by the IDE:</h4>

```
git clone https://github.com/AndreKuratomi/tables_to_db.git
```

WINDOWS:

Obs: In case of any mistake similar to this one: 

```
unable to access 'https://github.com/AndreKuratomi/tables_to_db.git/': SSL certificate problem: self-signed certificate in certificate chain
```

Configure git to disable SSL certification:

```
git config --global http.sslVerify "false"
```

<p>Enter the directory:</p>

```
cd tables_to_db
```
<br>

<h4>2. After cloning the repository install:</h4>

<h5>Virtual enviroment* and update its dependencies with the following command:</h5>


LINUX:
```
python3 -m venv venv --upgrade-deps
```

WINDOWS:
```
py -m venv venv --upgrade-deps
```

In case an error like this one is returned just follow the command displayed:

```
The virtual environment was not created successfully because ensurepip is not
available.  On Debian/Ubuntu systems, you need to install the python3-venv
package using the following command.

    apt install python3.10-venv

You may need to use sudo with that command.  After installing the python3-venv
package, recreate your virtual environment.
```

*It is a good practice to work with virtual enviroments because different projects may need different dependencies. A virtual enviroment is only a separated enviroment from the user machine. If not used, the user's machine may have lots of dependencies intalled that may only be used in a single project.

<br>
<h5>Activate your virtual enviroment with the command:</h5>

LINUX:
```
source/venv/bin/activate
```

WINDOWS:

On Windows operational system it is necessary to configure the Execution Policy at PowerShell:

```
Get-ExecutionPolicy # to check the Execution policy type
Set-ExecutionPolicy RemoteSigned # to change the type of policy if the command above shows 'Restricted'
```
Obs: It may often be necessary to open PowerShell as administrador for that.

```
.\env\Scripts\activate
```
<br>
<h5>Install the script's dependencies:</h5>

```
pip install -r requirements.txt
```
<br>


WINDOWS:

In case any error similar to the one bellow be returned:

```
ERROR: Could not install packages due to an OSError: [Errno 2] No such file or directory: 'C:\\Users\\andre.kuratomi\\OneDrive - Company\\Área de Trabalho\\tables_to_db_mail_for_finances\\tables_to_db_and_mail_finances\\env\\Lib\\site-packages\\jedi\\third_party\\django-stubs\\django-stubs\\contrib\\contenttypes\\management\\commands\\remove_stale_contenttypes.pyi'
HINT: This error might have occurred since this system does not have Windows Long Path support enabled. You can find information on how to enable this at https://pip.pypa.io/warnings/enable-long-paths
```

Run cmd as adminstrador with the following command:

```
reg.exe add HKLM\SYSTEM\CurrentControlSet\Control\FileSystem /v LongPathsEnabled /t REG_DWORD /d 1 /f
```
<br>

<h4>3. Open the application on your IDE:</h4>

```
code .
```
<br>


<h4>4. Create <b>.env</b> file in the script's root directoy:</h4>

```
touch .env
```

Inside it we need to put our enviroment variables taking as reference the given file <b>.env.example</b>:

```
MYSQL_USER=user
MYSQL_PASSWORD=password
```

Obs: Do not share info from .env file. It is already mentioned in <b>.gitignore</b> for not being pushed to the repo.

<br>
<h5>4. And run the script:</h5>

LINUX:
```
python3 tables_to_db.py
```

WINDOWS:
```
py tables_to_db.py
```
<br>


## References

- [Git](https://git-scm.com/downloads)
- [MySQL](https://https://www.mysql.com/)
- [Pandas](https://pandas.pydata.org/docs/)
- [Python](https://www.python.org/downloads/)
- [PyMySQL](https://pypi.org/project/PyMySQL/)
  
