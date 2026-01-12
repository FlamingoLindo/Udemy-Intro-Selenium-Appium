# Abrindo páginas web

Bem agora que nós já sabemos como iniciar um navegador em nossos scripts vamos agora aprender a como abrir uma determinada página no script

Para fazer com que o driver abra uma página, utiliza-se a função `get` e dentro dos parenteses se passa URL do site em que estamos tentando acessar.

É importante dizer que é necessário adicionar o `https://` no começo da URL dentro do `get`.

```py
import time

from selenium import webdriver

driver = webdriver.Chrome()

driver.get('https://www.selenium.dev/pt-br/')

time.sleep(10)

driver.quit()
```

- Obs.: nesse trecho de código também estou utilizando a biblioteca `time` apenas para "congelar" a execução do código por 10 segundo, `time.sleep(10)`, para que seja possível ver o resultado
