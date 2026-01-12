# Imports e Drivers

Para iniciarmos um script de automatização com selenium, o primeiro passo é importar e inicializar um [webdriver](https://www.selenium.dev/documentation/webdriver/), é uma API que faz realiza a manipulação do navegador automaticamente.

---

1. Criar um arquivo como `driver.py`

2. Dentro dele inserir esse linha de código:

    ```py
    from selenium import webdriver
    ```

    Aqui nós estamos importando da biblioteca `selenium` o módulo `webdriver`

3. Em seguida nós criamos um objeto para representar o navegador :

    ```py
    driver_chrome = webdriver.Chrome()  # Cria o objeto para o navegador Chrome
    driver_firefox = webdriver.Firefox()    # Cria o objeto para o navegador Firefox
    driver_edge = webdriver.Edge()  # Cria o objeto para o navegador Edge
    ```

4. E por último adicionamos a seguinte linha no final de todos os scripts:

    ```py
    driver_chrome.quit()    # Fecha o navegador Chrome
    driver_firefox.quit()   # Fecha o navegador Firefox
    driver_edge.quit()      # Fecha o navegador Edge
    ```

    É sempre uma boa prática, usar a função "quit" para que o após o script termine de executar o driver fechado e que ele não fique aberto para sempre.

- **Extra.:** É possível adicionar configurações de inicialização dos drivers como no seguinte exemplo:

    ```py
    from selenium import webdriver

    options = webdriver.ChromeOptions()
    options.add_argument("--headless=new")

    driver_chrome = webdriver.Chrome(options=options)
    driver_chrome.quit()
    ```

    Nesse caso estamos criando um objeto `options` que é atribuído às configurações do Chrome, e essa [configuração](https://www.selenium.dev/blog/2023/headless-is-going-away/) `--headless=new` serve para rodar os scripts sem a que utilize a interface gráfica do navegador, reduzindo o uso de memória e tempo de execução.
