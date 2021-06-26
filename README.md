Bootstrap DatePicker Thai Buddhist-Era (B.E.) Widget for Yii2
====================================

[![Latest Version](https://img.shields.io/github/tag/karatae99/yii2-date-picker-thai-widget.svg?style=flat-square&label=release)](https://packagist.org/packages/karatae99/yii2-date-picker-thai-widget)
[![License](https://poser.pugx.org/karatae99/yii2-date-picker-thai-widget/license)](https://packagist.org/packages/karatae99/yii2-date-picker-thai-widget)
[![Total Downloads](https://poser.pugx.org/karatae99/yii2-date-picker-thai-widget/downloads)](https://packagist.org/packages/karatae99/yii2-date-picker-thai-widget)

This is thai buddhist calendar datepicker of Yii2 extension. 

modified from (https://github.com/2amigos/yii2-date-picker-widget).


Installation
------------
The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```bash
$ composer require karatae99/yii2-date-picker-thai-widget "~1.0"
```
or add

```json
"karatae99/yii2-date-picker-thai-widget" : "~1.0"
```

to the require section of your application's `composer.json` file.

Usage
-----

**DatePicker**

This widget renders a Bootstrap DatePicker input control. Best suitable for model with date string attribute.

***Example of use with a form***  
There are two ways of using it, with an `ActiveForm` instance or as a widget setting up its `model` and `attribute`.

```php
<?php

use karatae99\datepicker\DatePicker;

// as a widget
?>

<?= DatePicker::widget([
    'model' => $model,
    'attribute' => 'date',
    'template' => '{addon}{input}',
	'language' => 'th', 	     //<-- Thai B.E.
        'clientOptions' => [
            'autoclose' => true,
            'format' => 'dd/mm/yyyy' //<-- Thai B.E.
        ]
]);?>

<?php 
// with an ActiveForm instance 
?>
<?= $form->field($model, 'date')->widget(
    DatePicker::className(), [
        // inline too, not bad
        'inline' => true, 
        // modify template for custom rendering
        'template' => '<div class="well well-sm" style="background-color: #fff; width:250px">{input}</div>',
		'language' => 'th', 	//<-- Thai B.E.
        'clientOptions' => [
            'autoclose' => true,
            'format' => 'dd/mm/yyyy' 	//<-- Thai B.E.
        ]
]);?>
```  
***Example of use without a model***

```php
<?php
use karatae99\datepicker\DatePicker;
?>
<?= DatePicker::widget([
    'name' => 'Test',
    'value' => '20/03/2561',
    'template' => '{addon}{input}',
	'language' => 'th', 	      //<-- Thai B.E.
        'clientOptions' => [
            'autoclose' => true,
            'format' => 'dd/mm/yyyy'  //<-- Thai B.E.
        ]
]);?>
```

**DateRangePicker**  

This widget renders a Bootstrap DateRangePicker Input control. 

***Example of use with a form***  
The following example works with a model that has two attributes named `date_from` and `date_to`.

```php
<?php
use karatae99\datepicker\DateRangePicker;
?>
<?= $form->field($model, 'date_from')->widget(DateRangePicker::className(), [
    'attributeTo' => 'date_to', 
    'form' => $form, // best for correct client validation
    'language' => 'th', 			//<-- Thai B.E.
    'size' => 'lg',
		'clientOptions' => [
			'autoclose' => true,
			'format' => 'dd/mm/yyyy' //<-- Thai B.E.
		]
]);?>
```  
***Example of use without a model***

```php  
<?php
use dosamigos\datepicker\DateRangePicker;
?>
<?= DateRangePicker::widget([
    'name' => 'date_from',
    'value' => '02-16-2012',
    'nameTo' => 'name_to',
    'valueTo' => '02-20-2012'
]);?>
```


Further Information
-------------------
Please, check the [Bootstrap DatePicker site](http://bootstrap-datepicker.readthedocs.io) documentation for further information about its configuration options. 


License
-------
The BSD License (BSD). Please see [License File](LICENSE.md) for more information.
