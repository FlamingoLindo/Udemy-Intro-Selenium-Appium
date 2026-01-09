# Como instalar o Selenium

Nesse curso nós vamos utilizar o [Python](https://www.python.org/) como linguagem de programação pela sua facilidade de criar scripts, então caso você ainda não tenha ele instalado essa é a hora!

---

1. Abrir o terminal do VS Code
    - Para abrir um terminal, no menu de opções `Terminal` clique na opção `New Terminal`.
    - Também é possível abrir um terminal com as seguintes combinações de teclas: `Ctrl+Shift+'` ou `Ctrl+j`.
    ![abrir_terminal](/images/Aula%20-%202/abrir_terminal.png)

2. Verificar a instalação do [pip](https://pypi.org/project/pip/)
    - No seu terminal digite `pip`, caso aparece alguma mensagem de erro, instale o pip para prosseguir.
    - Obs.: O seu terminal pode ter um "estilo" diferente do meu, mas isso não afetará em nada nesse curso é apenas uma mudança cosmética que eu uso.
    ![pip](/images/Aula%20-%202/pip.png)

3. Iniciar um [ambiente virtual](https://docs.python.org/pt-br/3/library/venv.html)
    - Nós vamos utilizar um ambiente virtual por ser uma boa prática em qualquer projeto python, pois ele é um diretório isolado que contém uma instalação específica do Python e suas bibliotecas, permitindo que diferentes projetos usem versões distintas de pacotes sem conflitos.
    - Primeiro use a combinação de teclas `Ctrl+Shipt+P`
    - Depois pesquise por `Python: Create Environment...` e selecione essa opção
    ![venv1](/images/Aula%20-%202/venv1.png)
    - Em seguida selecione a opção `Venv`
    ![venv2](/images/Aula%20-%202/venv2.png)
    - E por ultimo selecione a versão de Python que você tem instalada e espere a criação terminar
    ![venv3](/images/Aula%20-%202/venv3.png)
4. Baixar o Selenium:
    - Digite `pip install selenium` no terminal
    ![pip_selenium](/images/Aula%20-%202/pip_selenium.png)

5. Verificar a instalação do Selenium:
    - Digite `pip show selenium` no terminal
    ![pip_show](/images/Aula%20-%202/pip_show.png)
