# Esperando elementos carregarem

Nos exemplos vistos até agora nós apenas estamos apenas iniciando o driver e congelando a execução dele com o uso da biblioteca `time` para esperar um elemento aparecer, mas isso não é considerado uma boa prática pois o Selenium já oferece uma forma nativa de esperar um determinado elemento aparecer utilizando o que é chamado de `explicit await`.

---

1. Primeiro termos que importar dois novos módulos

    ```py
    from selenium.webdriver.support import expected_conditions as EC
    from selenium.webdriver.support.ui import WebDriverWait
    ```

    - `EC` é utilizado para passar uma regra que se espera de um elemento
    - `WebDriverWait` é o responsável por "saber" se o elemento já está visível na página

2. Então nos precisamos iniciar o objeto de "espera" por um elemento

    ```py
    wait = WebDriverWait(driver, 5)
    ```

    Aqui nos criamos o objeto de espera e passamos o driver e a quantidade de segundo máxima que o driver irá esperar até que o elemento apareça

3. Agora quando formos localizar um elemento, precisa ser feito dessa forma

    ```py
    elemento = wait.until(EC.presence_of_element_located(
    (By.NAME, 'q')))
    ```

    Ou seja, aqui estamos esperando até que a presença do elemento seja localizada para que o script possa prosseguir

**Exemplo completo.:**

```py
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()

wait = WebDriverWait(driver, 5)

driver.get('https://www.google.com')

elemento = wait.until(EC.presence_of_element_located(
    (By.NAME, 'q')))

print('\nElemento encontrado":\n', elemento)

driver.quit()
```
