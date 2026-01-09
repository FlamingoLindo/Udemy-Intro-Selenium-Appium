# Como localizar um elemento em uma página web

Como exemplo, vou utilizar a página inicial do google para ser mais fácil.

1. Abra o seu navegador Google

2. Aperte a tecla `F12` em seu teclado, que irá abrir a aba de `DevTools`
    ![dev_tools](/images/Aula%20-%203/dev_tools.png)

3. Na aba `Elements` é possível visualizar o [DOM (Document Object Model)](https://pt.wikipedia.org/wiki/Modelo_de_Objeto_de_Documentos) da página que se assimilha ao HTML da página

4. No canto superior esquerdo DevTools selecione a opção `Select an element in the page to inspect it - Ctrl + Shift + C`
    - Com essa opção ativada é possível passar o mouse por cima de qualquer elemento da página e encontrar ele no DOM

    ![select_element](/images/Aula%20-%203/select_element.png)

5. Selecione o campo de pesquisa principal da página
    - Ao selecionar um elemento ele ficará destacado dentro do DevTools, mostrando todas as informações disponíveis desse elemento no DOM

    ![elemento](/images/Aula%20-%203/elemento.png)

---

## Localizadores

### O que são localizadores?

Localizadores são utilizados para identificar algum elemento em uma página.

### Quais são os tipos de localizadores?

|Tipo|Descrição|
|------|-----------|
|class name|Localiza elementos cujo nome de classe contém o valor de pesquisa (nomes de classes compostos não são permitidos)|
|css selector|Localiza elementos que correspondem a um seletor CSS|
|id|Localiza elementos cujo atributo ID corresponde ao valor de pesquisa|
|name|Localiza elementos cujo atributo NAME corresponde ao valor pesquisado|
|link text|Localiza elementos âncora cujo texto visível corresponde ao valor de pesquisa|
|partial link text|Localiza elementos âncora cujo texto visível contém o valor de pesquisa. Se vários elementos corresponderem, apenas o primeiro será selecionado|
|tag name|Localiza elementos cujo nome da tag corresponde ao valor de pesquisa|
|xpath|Localiza elementos que correspondem a uma expressão XPath|

Essa tabela foi retirada do site do [Selenium][0].

[0]:https://www.selenium.dev/documentation/webdriver/elements/locators/

### Qual tipo de seletor usar?

**1. CSS Selector:**

- É geralmente mais rápido e confiável quando possível, especialmente em navegadores modernos.

- Ideal para selecionar elementos com base em classes, IDs ou atributos específicos.

- Útil para identificar elementos de forma precisa e concisa, especialmente quando a estrutura da página é estável.

**2. XPath:**

- Permite maior flexibilidade, pois pode navegar por estruturas complexas e hierarquias.

- Recomendado quando há necessidade de localizar elementos relativos, como "o segundo elemento após um título específico".

- É útil quando os elementos não têm identificadores únicos.

**3. Full XPath:**

- Utiliza o caminho completo até o elemento na árvore do DOM, indo desde o nó raiz.

- É mais suscetível a mudanças na estrutura da página, pois qualquer alteração no layout pode quebrar o seletor.

- Use-o apenas em última instância, caso os outros métodos não consigam localizar o elemento, e o layout seja estável.

---

## Voltando ao exemplo do Google

No DevTools com a barra de pesquisa selecionada é possível ver que esse elemento é do tipo `input` e possui um localizador do tipo `id` com o valor de `input`

![id](/images/Aula%20-%203/id.png)
