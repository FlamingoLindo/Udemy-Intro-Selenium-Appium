# Como interagir com um elemento no Appium

Agora que o driver Appium já foi inicializado e o aplicativo foi aberto, o próximo passo é aprender **como localizar e interagir com elementos da interface mobile**, de forma semelhante ao que fazemos no Selenium, porém usando estratégias específicas para Android.

---

## 1. Importação dos módulos necessários para interação

Para interagir com elementos no Appium, utilizamos principalmente:

```py
from appium.webdriver import Remote
from appium.webdriver.common.appiumby import AppiumBy
from appium.options.android.uiautomator2.base import UiAutomator2Options
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

capabilities = {
    'noReset': True,
    'automationName': 'uiautomator2',
    'language': 'pt',
    'printPageSourceOnFindFailure': True,
    'appPackage': 'com.google.android.youtube',
    'appActivity': 'com.google.android.youtube.app.honeycomb.Shell$HomeActivity'
}

APPIUM_SERVER_URL = 'http://localhost:4723'
```

## 2. Inicialização do driver Appium

Antes de utilizar as esperas explícitas, é necessário criar a sessão com o Appium:

```py
driver = Remote(
    APPIUM_SERVER_URL,
    options=UiAutomator2Options().load_capabilities(capabilities)
)
```

## 3. Criando o objeto de espera

Com o driver inicializado, criamos o objeto responsável por aguardar os elementos:

```py
wait = WebDriverWait(driver, 5)
```

Isso significa que o Appium aguardará até 5 segundos para que a condição definida seja atendida antes de lançar uma exceção.

## 4. Esperando e interagindo com elementos

- Aguardando a presença de um elemento

  ```py
  search_icon = wait.until(
      EC.presence_of_element_located(
          (AppiumBy.ACCESSIBILITY_ID, 'Pesquisar')
      )
  )
  ```

- Aguardando o elemento ficar clicável

  ```py
  search_icon = wait.until(
      EC.element_to_be_clickable(
          (AppiumBy.ACCESSIBILITY_ID, 'Pesquisar')
      )
  )
  search_icon.click()
  ```

- Enviando texto para um campo de busca

  ```py
  search_bar = wait.until(
      EC.element_to_be_clickable(
          (AppiumBy.ID, 'com.google.android.youtube:id/search_edit_text')
      )
  )
  search_bar.send_keys('Velvet Revolver - Fall To Pieces')
  ```

- Selecionando um resultado com UiAutomator

  ```py
  result = wait.until(
      EC.element_to_be_clickable((
          AppiumBy.ANDROID_UIAUTOMATOR,
          'new UiSelector().resourceId("com.google.android.youtube:id/linearLayout").instance(0)'
      ))
  )
  result.click()
  ```

- Aguardando um elemento visível e clicando

  ```py
  video = wait.until(
      EC.visibility_of_element_located((
          AppiumBy.ACCESSIBILITY_ID,
          'Velvet Revolver - Fall To Pieces (Official Video) - 4 minutos e 30 '
          'segundos - Acessar o canal velvetrevolverVEVO - Velvet Revolver - 128 '
          'milhões de visualizações - há 16 anos - assistir o vídeo'
      ))
  )
  video.click()
  ```

- Finalizando a sessão

```py
driver.quit()
```

**Exemplo completo.:**

```py
from appium.webdriver import Remote
from appium.webdriver.common.appiumby import AppiumBy
from appium.options.android.uiautomator2.base import UiAutomator2Options
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC


capabilities = {
    'noReset': True,
    'automationName': 'uiautomator2',
    'language': 'pt',
    'printPageSourceOnFindFailure': True,
    'appPackage': 'com.google.android.youtube',
    'appActivity': 'com.google.android.youtube.app.honeycomb.Shell$HomeActivity'
}

APPIUM_SERVER_URL = 'http://localhost:4723'


driver = Remote(
    APPIUM_SERVER_URL, options=UiAutomator2Options().load_capabilities(capabilities))

wait = WebDriverWait(driver, 5)

search_icon = wait.until(EC.presence_of_element_located(
    (AppiumBy.ACCESSIBILITY_ID, 'Pesquisar')))
search_icon = wait.until(EC.element_to_be_clickable(
    (AppiumBy.ACCESSIBILITY_ID, 'Pesquisar')))
search_icon.click()

search_bar = wait.until(EC.element_to_be_clickable(
    (AppiumBy.ID, 'com.google.android.youtube:id/search_edit_text')))
search_bar.send_keys('Velvet Revolver - Fall To Pieces')

result = wait.until(EC.element_to_be_clickable((
    AppiumBy.ANDROID_UIAUTOMATOR,
    'new UiSelector().resourceId("com.google.android.youtube:id/linearLayout")'
    '.instance(0)'
)))
result.click()

video = wait.until(EC.visibility_of_element_located((
    AppiumBy.ACCESSIBILITY_ID,
    'Velvet Revolver - Fall To Pieces (Official Video) - 4 minutos e 30 '
    'segundos - Acessar o canal velvetrevolverVEVO - Velvet Revolver - 128 '
    'milhões de visualizações - há 16 anos - assistir o vídeo'
)))
video.click()

print('Vídeo aberto!')

driver.quit()
```
