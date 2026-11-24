# Big Data Analysis - Final Project

## Requerimentos

- Git
- Python 3.11
- Visual Studio Code, com as extensões **Python** e **Jupyter**

Eu tou a usar python 3.11.9 no meu venv, podemos usar essa versão ou mudar, se acharmos melhor outra!
(Na criação dos venvs que explico embaixo assumi o python 3.11.9, depois podemos mudar se quisermos outra versão)


## Preparar o ambiente (venv)

### Mac (Bash)

ctrl + c, ctrl + v para o terminal do VScode

```bash
python3.11 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Windows (PowerShell)

ctrl + c, ctrl + v para o terminal do VS code

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Se o PowerShell não deixar ativar o ambiente tentem instalar os pacotes diretamente:

```powershell
.\.venv\Scripts\python.exe -m pip install --upgrade pip
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

Por agora o `requirements.txt` contém o `ipykernel`, necessário para usar o ambiente nos notebooks. Quando decidirmos as versões do Spark e do PySpark, acrescentamos as dependências ao ficheiro! O Java necessário para correr Spark instala-se à parte, não vem incluído no venv.

## Usar a `.venv` nos notebooks

1. Abram a pasta do projeto no VS Code
2. Abram a paleta de comandos com `Ctrl+Shift+P` (no Mac `Cmd+Shift+P`) e escolhe **Python: Select Interpreter**
3. Selecionem o Python que está dentro da pasta `.venv`.
4. Criem ou abram um ficheiro `.ipynb` e escolham **Select Kernel** > `.venv`.
5. Para confirmarem que está tudo a apontar para o ambiente certo corram este código numa célula do notebook:

```python
import sys
print(sys.version)
print(sys.executable)
```

O caminho deve tar dentro da pasta `.venv`.

Quando alguém acrescentar uma dependência ao projeto deve atualizar o `requirements.txt` e avisar o grupo. Para instalar as dependências registadas nesse ficheiro (com a `.venv` ativa) corram:

```bash
python -m pip install -r requirements.txt
```

## Notas

1. **Não trabalhem diretamente na `main`**. Criem uma branch e só façam merge para a `main` depois de falarmos todos muchas gracias :)

Os comandos Git são iguais no Mac (Bash) e no Windows (PowerShell)
(troquem `feature/nome-da-tarefa` por um nome curto descritivo do que vão fazer)

### Começar uma tarefa

```bash
git switch main
git pull origin main
git switch -c feature/nome-da-tarefa
```

### Guardar e partilhar o trabalho

Depois de fazerem coisas:

```bash
git add .
git commit -m "Descreve as alterações"
git push -u origin feature/nome-da-tarefa
```

Para enviar mais alterações para a mesma branch fazem outro commit e depois:

```bash
git push
```

Para trazer as atualizações mais recentes da `main` para o branch, estando no branch:

```bash
git pull origin main
```

Quando terminares, partilhem a branch com o grupo. **Não façam merge para a `main` sem falarmos e concordarmos todos pleaseeeee**

## Notas rápidas

- O `requirements.txt` é a lista partilhada das bibliotecas Python do projeto, sempre que se vai usar algo de novo que seja importante tem de se pôr lá!
- Vão registando o que fizerem no `DEVELOPMENT.md` e as tarefas por fazer no `TODO.md`
