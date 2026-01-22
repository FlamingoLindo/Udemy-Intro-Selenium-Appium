# Imports, Capacidades e Inicialização no Appium

Assim como no Selenium, para iniciar um script de automação mobile com Appium é necessário importar as bibliotecas corretas, definir as **capabilities** e informar onde o servidor Appium está rodando.

---

## 1. Importação das bibliotecas

Crie um arquivo, por exemplo `driver_appium.py`, e comece importando os módulos necessários:

```py
from appium import webdriver
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from appium.options.android import UiAutomator2Options
from appium.webdriver.common.appiumby import AppiumBy
```

- `webdriver`: responsável por criar a sessão de automação com o Appium.

- `WebDriverWait` e `expected_conditions` (EC): usados para esperas explícitas, garantindo que elementos estejam disponíveis antes da interação.

- `UiAutomator2Options`: classe moderna para configurar opções específicas do Android.

- `AppiumBy`: fornece estratégias de localização de elementos (accessibility id, xpath, etc.).

## 2. Definição das capabilities

No Appium, as capabilities informam ao servidor como o script deve ser executado. Elas normalmente são copiadas ou adaptadas diretamente do Appium Inspector.

```py
capabilities = dict(
    noReset=True,
    automationName='uiautomator2',
    language='pt',
    printPageSourceOnFindFailure=True,
    appPackage='com.google.android.youtube',
    appActivity='com.google.android.youtube.app.honeycomb.Shell$HomeActivity'
)
```

- `noReset`
  Evita que o aplicativo seja reiniciado do zero entre execuções.
  Mantém login, preferências e estado do app.

- `automationName`
  Define o motor de automação.
  UiAutomator2 é o padrão recomendado para Android moderno.

- `language`
  Força o idioma da aplicação para português (pt), quando suportado.

- `printPageSourceOnFindFailure`
  Imprime a árvore XML da tela quando um elemento não é encontrado.
  Muito útil para depuração.

- `appPackage`
  Identifica unicamente o aplicativo no Android.
  Neste caso, o pacote do YouTube.

- `appActivity`
  Define qual tela (Activity) será aberta ao iniciar o app.

## 3. Endereço do servidor Appium

Por fim, precisamos informar ao Appium onde o servidor está em execução:

```py
appium_server_url = 'http://localhost:4723'
```
