<h1>ПИЭ Диск</h1>
<p>Сервис хранения, редактирования и синхронизации файлов. Его функции включают хранение файлов в Интернете, общий доступ к ним и совместное редактирование.</p>
<p>Проект разработат на основе шаблона <b>Yii2-advanced</b></p>

<h4>Инструкции по разворачиванию проекта на хост машине через Docker:</h4>
<ol>
<li>Перед разворачиванием проекта убедитесь что на вашей хост-магине установлены "Docker" и "Docker-compose", "Git", "PHP", "Composer"</li>
<li>Клонируйте проект из GitHub</li>
<li>Загрузите зависимости vendor команда: <b>composer install</b></li>
<li>Перейдите в дирректорию проекта  и выполните: <b>docker-compose up --build -d</b></li>
<li>В дирректории с проектом выполните команду: <b>php init</b> и ответьте на вопросы для разворачивания проекта. Для продакшена выберите "1", затем "yes", и в конце "all".</li>
<li>Выполните миграции RBAC командой: <b>php yii migrate --migrationPath=@yii/rbac/migrations/</b> Выберите "yes".</li>
<li>Выполните миграции командой: <b>php yii migrate</b> Выберите "yes".</li>
<li>Для создания прав и правил выполните: <b>php yii default/index</b></li>
</ol>

<p>После выполнении всех вышеперечисленных действий Вы можете открыть приложение по адресу: <a href='http://127.0.0.1:81/'>http://127.0.0.1:81</a>.
Логин и Пароль для входа admin/123456. </p>

<p>После проведения тестового запуска необходимо зарегистрировать реального пользователя с правами администратора. Обязательно удалите тестового пользователя <b>admin</b></p>

<h1>Структура проекта</h1>

```


backend
    assets/              содержит ресурсы приложения, такие как JavaScript и CSS
    config/              содержит бэкэнд-конфигурации
    modules/             содержит модули проекта
        api                 модуль управения проектом через REST API
        base/               базовый модуль проекта
            assets/             содержит ресурсы приложения
            components/         содержит компоненты приложения (User,...)
            controllers/        содержит контроллеры (базовые команды приложения)
            models/             содержит классы моделей
            rbac/               содержит классы правил доступа 
            views/              содержит файлы просмотра для веб-приложения
            web/                содержит сценарий ввода и веб-ресурсы
        helpers/            модуль со вспомогательным функционалом
    runtime/             содержит файлы, созданные во время выполнения
    tests/               содержит тесты для внутреннего приложения    
    web/                 содержит сценарий ввода и веб-ресурсы
vendor/                  содержит зависимые сторонние пакеты
environments/            содержит переопределения на основе среды

console
    config/              содержит консольные-конфигурации
    controllers/         содержит контроллеры (команды)
    migrations/          содержит миграции базы данных
    models/              содержит классы моделей
    runtime/             содержит файлы, созданные во время выполнения
```
