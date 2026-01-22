# Como utilizar o inspetor de elementos mobile

Toda vez que você for fazer algum teste utilizando o appium, é necessário iniciar o servidor antes de tudo.

Para iniciar o servidor basta digitar a seguinte linha no terminal `appium --allow-cors`

Antes de iniciar o servidor é necessário que o seu celular esteja conectado com o seu computador!

---

1. Abra o google e acesse o inspetor pela seguinte URL: https://inspector.appiumpro.com/

2. Dentro do Inspector clique uma vezes na opção para adicionar uma capacidade "capability"

3. Dentro de cada caixa digite os seguintes valores

| Nome                  | Tipo | Valor        |
| --------------------- | ---- | ------------ |
| platformName          | text | Android      |
| appium:automationName | text | uiautomator2 |

**Obs.:** Existem diversas capacidades com diversas funções, não vamos entrar muito a fundo nelas nesse curso, mas essas duas são as essenciais. Caso você queria conhecer mais sobre elas segue o [link para a página da documentação](https://appium.io/docs/en/latest/guides/caps/).

4. Após declarar as capacidades, clique em `Start Session`
   - Agora você pode usar o Inspector como se ele fosse a ferramenta do google para localizar elementos.

![inspector_configs](/Images/Appium/Aula%20-%2011/inspector_configs.png)

---

## Funções básicas do inspetor

![basic](/images/Appium/Aula%20-%2011/basic.png)

1. Área de visualização do aplicativo (Device Screen)
   Exibe a tela do dispositivo/emulador em tempo real. Permite:
   - Visualizar o estado atual da aplicação.

   - Selecionar elementos diretamente clicando sobre a tela.

2. App Source (Árvore de elementos da aplicação)
   Representa a hierarquia XML da UI Android.
   - Cada nó corresponde a um elemento da interface (View, ImageView, Button, etc.).

   - Ao selecionar um nó, ele é destacado na tela do dispositivo.

   - Útil para entender a estrutura, relações pai/filho e propriedades dos elementos.

3. Ações do elemento selecionado (Selected Element)
   Conjunto de ações que podem ser executadas diretamente no elemento selecionado:
   - `Tap`

   - `Enviar texto` (Send Keys)

   - `Limpar texto`

   - `Copiar seletor`

4. Localizadores (Find By / Selectors)
   Mostra as estratégias disponíveis para localizar o elemento no teste:
   - `Accessibility ID` (ex.: Pesquisar)

   - `UIAutomator` (ex.: new UiSelector().description("Pesquisar"))

   - `XPath`

5. Atributos do elemento (Attributes)
   Lista detalhada das propriedades do elemento selecionado:
   - `class`

   - `resource-id`

   - `content-desc`

   - `text`

   - `package`

   - `index`
