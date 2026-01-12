# Como enviar arquivos

Agora nós vamos ver como que se faz para enviar arquivos em scripts

1. Primeiro temos que importar a biblioteca `os`

    ```py
    import os
    ```

2. Em seguida nós temos que carregar a imagem em nosso script

    ```py
    upload_file = os.path.abspath(
        os.path.join(os.path.dirname(__file__), "../../../images", "selenium.png"))

    print(upload_file)
    ```

    **Obs.:** `"../../../images"` é onde o arquivo está localizado e `"selenium.png"` é o nome do arquivo

3. Depois nós temos que localizar o input de arquivos

    ```py
    file_input = wait.until(EC.presence_of_element_located(
    (By.CSS_SELECTOR, "input[type='file']")))
    ```

4. E por último, para enviar o arquivo basta utilizar o `send_keys()`

    ```py
    file_input.send_keys(upload_file)
    ```

**Exemplo completo.:**

```py
import time
import os
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.support.ui import WebDriverWait

driver = webdriver.Chrome()
wait = WebDriverWait(driver, 5)

upload_file = os.path.abspath(
    os.path.join(os.path.dirname(__file__), "../../../images", "selenium.png"))

print(upload_file)

driver.get('https://images.google.com/?hl=pt-br')

image_btn = wait.until(EC.element_to_be_clickable(
    (By.CLASS_NAME, 'Gdd5U')))
image_btn.click()

file_input = wait.until(EC.presence_of_element_located(
    (By.CSS_SELECTOR, "input[type='file']")))

file_input.send_keys(upload_file)

time.sleep(3)

driver.quit()
```
