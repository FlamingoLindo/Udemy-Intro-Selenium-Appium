# Como interagir com um elemento

Agora que já sabemos como iniciar um driver e especificar qual site queremos que ele vá, apenas resta saber como interagir com a página

1. Temos que import o módulo `By`que é utilizado para especificar qual tipo de localizador estamos utilizando

    ```PY
    from selenium.webdriver.common.by import By
    ```

2. Então criamos um objeto que terá um elemento atribuído a ele

    ```py
    elemento = driver.find_element(By.NAME, 'q')
    ```

    Nesse exemplo, estamos utilizando a função `find_element` para localizar um elemento pelo localizador de valor `q` do tipo `NAME`

    ![q](/images/Aula%20-%206/q.png)

3. Por últimos nós temos as [ações que poder ser realizadas com o elemento](https://www.selenium.dev/documentation/webdriver/elements/interactions/) como

    ```py
    elemento.click()    # Emula o clique do mouse
    
    elemento.send_keys('Teste') # Digita um texto no elemento

    elemento.clear()    # Limpa o texto do elemento
    
    elemento.submit()   # Emula o "Enter" do teclado, geralmente 
                        # utilizado quando o elemento está em algum tipo de formulário ou barra de pesquisa
    ```

**Exemplo completo.:**

```py
import time
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

driver.get('https://www.google.com')

elemento = driver.find_element(By.NAME, 'q')

elemento.click()
elemento.send_keys('Teste')
elemento.submit()

time.sleep(5)
driver.quit()
```
