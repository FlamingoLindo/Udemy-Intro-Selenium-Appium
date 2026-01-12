# Como interagir com guias e abas

Em muitos casos alguns scripts precisam que fique alterando entre abas ou janelas do seu navegador, então agora vamos aprender como fazer isso

---

1. Pra abrir uma nova aba, utilizamos `driver.switch_to.new_window('tab')`

    ```py
    driver.switch_to.new_window('tab')
    janela_selenium = driver.current_window_handle
    ```

    **Obs.:** É importante salvar a aba atual em um objeto, para facilitar a troca entre abas

2. Para abrir uma nova janela utilizamos `driver.switch_to.new_window('window')`

    ```py
    driver.switch_to.new_window('window')
    driver.get('https://www.google.com/')
    janela_google = driver.current_window_handle
    ```

3. Para alterar entre janelas e abas basta fazer o seguinte

    ```py
    # Alternar de volta para a primeira aba (Python.org)
    driver.switch_to.window(janela_original)
    print(f"Título atual: {driver.title}")  # Python.org
    time.sleep(2)

    # Alternar para a aba do Selenium
    driver.switch_to.window(janela_selenium)
    print(f"Título atual: {driver.title}")  # Selenium
    time.sleep(2)

    # Alternar para a janela do Google
    driver.switch_to.window(janela_google)
    print(f"Título atual: {driver.title}")  # Google
    time.sleep(2)
    ```

4. E por último, caso quira fechar uma aba basta utilizar o `driver.close()`

    ```py
    driver.close()  # Fecha a aba atual
    ```

**Exemplo completo.:**

```py
import time
from selenium import webdriver

driver = webdriver.Chrome()
driver.get('https://www.python.org/')

# Salvar o identificador da janela original
janela_original = driver.current_window_handle

# Criar nova aba
driver.switch_to.new_window('tab')
driver.get('https://www.selenium.dev/')
janela_selenium = driver.current_window_handle

# Criar nova janela
driver.switch_to.new_window('window')
driver.get('https://www.google.com/')
janela_google = driver.current_window_handle

time.sleep(2)

# Alternar de volta para a primeira aba (Python.org)
driver.switch_to.window(janela_original)
print(f"Título atual: {driver.title}")  # Python.org
time.sleep(2)

# Alternar para a aba do Selenium
driver.switch_to.window(janela_selenium)
print(f"Título atual: {driver.title}")  # Selenium
time.sleep(2)

# Alternar para a janela do Google
driver.switch_to.window(janela_google)
print(f"Título atual: {driver.title}")  # Google
time.sleep(2)

driver.close()  # Fecha a aba atual
time.sleep(2)

driver.quit()
```
