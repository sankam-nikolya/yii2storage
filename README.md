Storage and Upload file widget

PLS!
This is non-stable alpha version. It's not recommended to go in production with it for now.
Any contributions are welcome

The plans:
* Widjet Upload analog XUpload Yii.1
* Storage files to directory categories ( `images`, `baners`, `videos`.. or `custom derictory`)
* Store to Amason Server
* Store upload to remote server

============
file upload/resize/crop file move storage

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist kak/storage "*"
```

or add

```
"kak/storage": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?= \kak\storage\Upload::widget([
    'model' => $model,
    'name'  => 'attr_file'
]); ?>
```

 example use controller this uploading
```php
    public function actions()
    {
        return [
            'upload' => [
                'class' => 'kak\storage\actions\UploadAction',
                'form_name' => 'kak\storage\models\UploadForm',
                'path'  => Yii::$app->getBasePath() . '/../uploads/',
                'public_path' => '/uploads/',
            ],
        ];
    }
```

Custom run action
```php
    $action = new \kak\storage\actions\UploadAction($this->id, $this, [
        'form_name' => 'kak\storage\models\UploadForm',
        'path'  => Yii::$app->getBasePath() . '/web/uploads/',
        'public_path' => '/uploads/'
    ]);
    return $action->run();
```