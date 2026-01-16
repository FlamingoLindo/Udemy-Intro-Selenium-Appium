# Como instalar o Appium

Nesse módulos, nós vamos aprender a como se instalar o Appium, que diferemte da instalação do Selenium ele é um pouco mais complicado.

---

1. Baixar Node.js
   ![node](/images/Appium/Aula%20-%201/node.png)
   - Página de [download](https://nodejs.org/en/download) do Node.js

   **Extra.:** Eu recomendo também a instalação do NVM, que é uma ferramenta de versionamento do Node

   ![nvm](/images/Appium/Aula%20-%201/nvm.png)
   - Página de [download](https://github.com/nvm-sh/nvm?tab=readme-ov-file#installing-and-updating) do nvm

2. Instalar Appium globalmente

   Aqui nessa etapa nós iremos baixar o pacote Appium e instalar ele globalmente em nosso computador com o seguinte commando dentro do powershell:

   ```bash
   npm i --global appium
   ```

   ![app_pack](/images/Appium/Aula%20-%201/app_pack.png)

   Para verificar a instalação, basta digitar em seu termina `appium`

   ![appium_exec](/images/Appium/Aula%20-%201/appium_exec.png)

   Após relizar a verificação acionar as teclas `ctrl + c` para para a execução do appium

3. Baixar o Android Studio

   ![and](/images/Appium/Aula%20-%201/and.png)
   - Página de [download](https://developer.android.com/studio?hl=pt-br) do Android Studio

4. Relizar a instalação

   ![i1](/images/Appium/Aula%20-%201/i1.png)

   ![i2](/images/Appium/Aula%20-%201/i2.png)

   ![i3](/images/Appium/Aula%20-%201/i3.png)

   ![i4](/images/Appium/Aula%20-%201/i4.png)

   ![i5](/images/Appium/Aula%20-%201/i5.png)

   ![i6](/images/Appium/Aula%20-%201/i6.png)

5. Adicionando variaveis de ambiente
   - Com o Andriod Studio aberto, clique na opção `Customize`
     ![a1](/images/Appium/Aula%20-%201/a1.png)

   - Na aba `Customize` clique em `All settings...`
     ![a2](/images//Appium/Aula%20-%201/a2.png)

   - Na barra de pesquisa, pesquise por `SDK`, clique na opção `Android SDK` e copie o caminho que aparece em `Android SDK Location`
     ![a3](/images/Appium/Aula%20-%201/a3.png)

   - Na barra de pesquisa do windows, procure por `Editar as variáveis do ambiente do sistema` e clique em `Abrir`
     ![a4](/images/Appium/Aula%20-%201/a4.png)

   - Clique em `Variáveis de Ambientes…`
     ![a5](/images/Appium/Aula%20-%201/a5.png)

   - Clique em `Novo…` e no campo `Nome da variável` digite `ANDROID_HOME` e no `Valor da variável` cole o caminho do `SDK` e clique em `OK`
     ![a6](/images/Appium/Aula%20-%201/a6.png)

   **Obs.:** Os seguintes passos são apenas necessários caso você ainda não tenha a variavel de ambiente `JAVA_HOME` em seu sistema
   - Em seguida abra a [página de download do SDK do Java](https://jdk.java.net/25/) e clique e selecione a opção de acordo com o seu sistema operacional
     ![a9](/images/Appium/Aula%20-%201/a9.png)

   - Após o download ter finalizdo, extraia o conteúdo do arquivo em `Arquivos de Programas`
     ![a10](/images/Appium/Aula%20-%201/a10.png)

   - Copie caminho da pasta `jdk`
     ![a11](/images/Appium/Aula%20-%201/a11.png)

   - Clique em `Novo…` e no campo `Nome da variável` digite `JAVA_HOME` e no `Valor da variável` cole o caminho do `sdk` e clique em `OK`
     ![a12](/images/Appium/Aula%20-%201/a12.png)

6. Instalando SDK Platform-Tools
   - De volta do Android Studio, na aba `SDK Tools` procure pela opção `Android SDK Platform-Tools`
     ![a7](/images/Appium/Aula%20-%201/a7.png)

     **Obs.:** Caso esse pacote ainda não esteja instado, então selecione e clique em `Apply` para fazer o download

   - Para verifacar a instalação, abra o seu terminal e digite `adb`
     ![a8](/images/Appium/Aula%20-%201/a8.png)

7. Instalando o Appium Doctor
   - No terminal digite `npm install -g @appium/doctor`
     ![ad1](/images/Appium/Aula%20-%201/ad1.png)

   - Para confirmar a instalação utilize o comando `appium-doctor`
     ![ad2](/images/Appium/Aula%20-%201/ad2.png)

     **Obs.:** Caso na seção `### Diagnostic for necessary dependencies starting ###`, tenha algum item marcado com `✖` procure resolver esse erro.

8. Instalando o uiautomator2
   - No terminal digite `appium driver install uiautomator2`
     ![uiauto](/images/Appium/Aula%20-%201/uiato.png)

9. Instalando o Appium Python Client
   - No terminal digite `pip install Appium-Python-Client`
     ![appcli](/images/Appium/Aula%20-%201/appclient.png)

10. Inciando o Appium

- Apartir de agora, sempre que você for iniciar o Appium digite o seguinte comando no terminal `appium --allow-cors`
  ![server](/images/Appium/Aula%20-%201/server.png)
