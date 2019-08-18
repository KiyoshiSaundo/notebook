# Баг в orderView

Исправление бага в блоках при кастомизации просмотра заказа в админке

```
bitrix\modules\sale\admin\order_view.php:368
```

заменить

```php
$defaultBlocksOrder[] = $blockId;
```

на

```php
$blocksOrder[] = $blockId;
```