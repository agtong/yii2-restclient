Yii2 Rest Client
=====

**Инструменты для использования API, как ActiveRecord для Yii2**

Используйте свой API как ActiveRecord

## Установка

Предпочтительный способ установки расширения через [composer](http://getcomposer.org/download/).

Запустить

```sh
php composer.phar require "apexwire/yii2-restclient"
```

или добавить

```json
"apexwire/yii2-restclient": "*"
```

в разделе "require" вашего composer.json

## Конфигурация

Добавьте этот код в ваш файл конфигурации:

```php
    'components' => [
        'restclient' => [
            'class' => 'apexwire\restclient\Connection',
            'config' => [
                'base_uri' => 'https://api.site.com/',
            ],
        ],
    ],
```

## Применение

Определите свою модель

```php
class MyModel extends \apexwire\restclient\ActiveRecord
{
    public function attributes()
    {
        return ['id', 'name', 'status'];
    }
}
```

## Debug

Пример подключения debug панели

```php
$config['modules']['debug'] = [
    'class' => 'yii\debug\Module',
    'panels' => [
        'rest' => ['class' => 'apexwire\restclient\DebugPanel'],
    ],
];
```

## Возможности

- можно указать список полей, которые вернутся: `MyModel::find()->select(['id','name'])`
- можно указать лимит: `MyModel::find()->limit(2)`
- поддерживается пагинация
- поддерживается сортировка
- поддерживается поиск. Пример [тут](docs/find.md).

## Лицензия

Этот проект был выпущен под лицензией [BSD-3-Clause](LICENSE).
Подробнее [тут](http://choosealicense.com/licenses/bsd-3-clause).

Copyright © 2016, ApexWire

## Выражение признательности

- Проект основан на расширении [Yii2 HiArt](https://github.com/hiqdev/yii2-hiart).
