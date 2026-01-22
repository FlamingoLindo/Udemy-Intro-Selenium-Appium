# Como vincular o celular para a execução de scripts

Agora que temos todas as ferramentas instaladas e preparas, precisamos configurar o nosso dispositivo para a execução de nossos scripts.

Nesse curso eu estarei utilizando o meu próprio celular, Android, como dispositivo para os scripts por conta da facilidade mas também é possível automatizar dispositivos iOS e emuladores.

---

1. Conecte o seu celular por meio de um fio USB ao seu computador e abra as configurações do seu dispositivo
   ![config](/images/Appium/Aula%20-%2011/config.png)

2. Procure por `Sobre o telefone` e acesse à tela
   ![about](/images/Appium/Aula%20-%2011/about.png)

3. Encontre e selecione a opção `Informações do software`
   ![infos_select](/images/Appium/Aula%20-%2011/infos_select.png)

4. Agora fique clicando onde está escrito `Número de compilação`, até que aparece uma mensagem como `Você está a X toque de ser um desenvolvedor.`, confirme para ativar o modo de desenvolvedor
   ![dev_on](/images/Appium/Aula%20-%2011/dev_on.png)
   ![confirm_dev](/images/Appium/Aula%20-%2011/confirm_dev.png)

5. No menu de configurações pesquise por `Depuração USB` e ative a opção
   ![usb_dep](/images/Appium/Aula%20-%2011/usb_dep.png)
   ![usb_dep_conf](/images/Appium/Aula%20-%2011/usb_dep_conf.png)

6. Então conecte o seu celular por meio de um cabo USB ao seu computador, uma caixa de dialogo irá aparecer para `Permitir a depuração USB?` marque a opção `Sempre permitir a partir deste computador` para não precisar repetir esse processo novamente e por fim `Permitir`
   ![connect](/images/Appium/Aula%20-%2011/connect.png)

7. Abra o seu terminal e digite o seguinte comando `adb devices` para "conectar" o seu celular com o seu computador
   - O [`adb`, Android Debug Bridge](https://developer.android.com/tools/adb?hl=pt-br), é uma ferramenta de linha de comando criada pela Google que permite comunicar e controlar um dispositivo ou um emulador Android de um computador.
     ![adb_devices](/images/Appium/Aula%20-%2011/adb_devices.png)

8. Agora no seu celular, abra um aplicativo de sua preferencia como exemplo eu estarei utilizando o `YouTube` e no seu terminal digite `adb shell`
   ![shell](/images/Appium/Aula%20-%2011/shell.png)

9. Então digite `dumpsys window displays | grep -E 'mCurrentFocus'` esse comando retorna duas coisas muito importantes, chamadas de `appPackage` e `appActivity`
   - appPackage: é o identificador único de um aplicativo, `com.google.android.youtube`, como seu "nome técnico" no Android.
   - appActivity: é uma tela ou funcionalidade específica dentro dele, `com.google.android.youtube.app.honeycomb.Shell$HomeActivity`.

   ![package_activity](/images/Appium/Aula%20-%2011/pagkace_activity.png)
   - Guarde os valores desses appPackage e appActivity por enquanto em algum lugar, pois nas próximas aulas iremos utilizar eles.
