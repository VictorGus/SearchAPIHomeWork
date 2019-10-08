Чтобы создать собственный бокс для выполнения заданий пройдите по ссылке: https://aidbox.app

Войдите с помощью Github или Google.

Далее нажмите кнопку **New Box** и появится следующее окно:

![alt text]()

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
Чтобы запустить Stresty, выполните следующую команду: 
```
$ java -jar stresty.jar <test-file>.yaml
```
По мере продвижения по заданиям заменяйте ```<test-file>``` на название файла с вашим текущим заданием.
