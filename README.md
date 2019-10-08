*Примечание: требуется Unix операционная система.*

## Настройка Aidbox

Чтобы создать собственный бокс для выполнения заданий пройдите по ссылке: https://aidbox.app

Войдите с помощью Github или Google.

Далее нажмите кнопку **New Box** и появится следующее окно:

![image](https://user-images.githubusercontent.com/18242717/66373087-72bcc300-e9b0-11e9-8aa4-efcdb59f3ec5.png)

Введите имя бокса и нажмите **Create**, после чего ваш созданный бокс появится в списке.

При переходе в бокс откроется следующая страница:

![image](https://user-images.githubusercontent.com/18242717/66373453-5a997380-e9b1-11e9-9d81-fe6f5d1f27d4.png)

После этого вам необходимо создать клиента и параметры безопасности для работы со stresty. Для создания клиента нажмите на вкладку Auth Clients в боковом меню и откроется следующее окно:

![image](https://user-images.githubusercontent.com/18242717/66373730-fcb95b80-e9b1-11e9-8ec4-8401c82a3766.png)

Нажмите кнопку **New**, вставьте данный ресурс в поле для ввода и нажмите кнопку **Save**:
```yaml
secret: secret
grant_types:
  - basic
id: user
resourceType: Client
```
Для задания параметров безопасности нажмите на вкладку Access Policy, откроется следующее окно:

![image](https://user-images.githubusercontent.com/18242717/66374057-cf20e200-e9b2-11e9-9d8a-e39b0c89251f.png)

Нажмите кнопку **New**, вставьте данный ресурс в поле для ввода и нажмите кнопку **Save**:
```yaml
engine: allow
id: user-policy
resourceType: AccessPolicy
```
## Stresty

Сначала вам нужно скачать stresty.jar, выполнив следующую команду:
```
$ curl -L -o stresty.jar https://github.com/Aidbox/stresty/releases/latest/download/stresty.jar
```
После этого необходимо экспортировать следующее:
```
$ export AIDBOX_URL=http://<box_name>.aidbox.app 
$ export AIDBOX_AUTH_TYPE=Basic
$ export AIDBOX_CLIENT_ID=<client-id>
$ export AIDBOX_CLIENT_SECRET=<client-secret>
```
Или можете воспользоваться скриптом setup.sh, предварительно изменив **значения переменных на ваши**
```
chmmod +x setup.sh
./setup.sh
```

Чтобы запустить Stresty, выполните следующую команду: 
```
$ java -jar stresty.jar <test-file>.yaml
```
По мере продвижения по заданиям заменяйте ```<test-file>``` на название файла с вашим текущим заданием.
