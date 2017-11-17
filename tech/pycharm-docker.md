# PyCharm и Docker

Прежде всего нужно настроить конфигурацию Docker (для Unix систем указать TCP сокет и данные для подключения к нему):
![alt text](images/pycharm-docker-build.png)

Далее необходимо выбрать интерпретатор нажав на шестеренку рядом с верхней строкой "Project Interpreter" и выбрав "Remote Interpreter":
![alt text](images/pycharm-remote-list.png)

В всплывающем окне выбрать сервер, путь к docker-compose файлу, выбать Service (которые соответствует Django серверу), указать переменные среды:
![alt text](images/pycharm-remote-settings.png)

В настроках Django framework включить поддержку и указать нужные пути к файлам и переменные среды:
![alt text](images/pycharm-django-framework.png)

Не забыть в настройках указать предпочтительный test runner, путь к зависимостям и формат docstring.
![alt text](images/pycharm-integrated-tools.png)

Для интеграции с CRM Taiga нажать на плюс и выбрать taiga. Далее ввести данные для входа и выбрать проект:
![alt text](images/pycharm-tasks-server.png)

На второй вкладке вписать шаблон сообщения коммита для автозакрытия задач при пуше:
![alt text](images/pycharm-tasks-commit.png)

Закрыть окно настроек. В выпадающем меню PyCharm выбрать Run -> Edit Configurations. Во всплывающем окне нажать на плюс и добавить во-первых Django со следующими настройками:
![alt text](images/pycharm-django-build.png)

Во всплывающем окне нажать на плюс и добавить во-вторых py.test (или Django test, если используете стандартный runner) со следующими настройками:
![alt text](images/pycharm-pytest-build.png)

Теперь можно в верхем выпадающем меню выбрать py.test и нажать кнопку зеленую Run (если выбрать Django, то запуститься dev сервер):
![alt text](images/pycharm-tests-run.png)
