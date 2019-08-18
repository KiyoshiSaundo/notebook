# Настройка SSL

Ключ:

![alt](/images/key.png)

Список файлов сертификатов:

![alt](/images/certificates.png)

Последний для домена. Остальные в очередности снизу вверху склеиваются (`cat 1.crt 2.crt 3.crt`) в один файл `*.ca-bundle` (цепочка сертификатов)

На ubuntu включается модуль в консоли:
```
a2enmod ssl
```

В настройках хоста дублируется блок для хоста и меняется порт на 443 + добавляются строки

```
SSLEngine on
SSLCertificateFile /var/www/certificate.crt
SSLCertificateChainFile /var/www/bundle.ca-bundle
SSLCertificateKeyFile /var/www/privatekey.key
```

<https://1cloud.ru/help/ssl/installsslapache>