# Validation
Валидация входящих данных

Создаем объект
```php
   $Validate = new Validation();
```

Передаем данные методу check(),
Метод check() принемает 
- Данные для проверки в виде array
- И параметры виде array

Список параметров 
- require
- min
- max
- email

Случаи удачной проверки метод passed()  return true
А в случай ошибки данные хранятся в методе error()



Пример 
==========
```php
   $Validate = new Validation();
   
   $Validate->check($_POST, [
      'title' => [
         'require' => true, 
         'min' => 2,
         'max' => 40
      ],
   ]);

  if ($Validate->passed()) {
    echo 'Ok';
  }else {
     foreach ($Validate->error() as $key => $value) {
        echo $value . '<br>';
     }
  }
  
  ```
