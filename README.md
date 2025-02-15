# Docker
Criando um container docker para laravel

# Criando o container e instanado o laravel
### 1 - Criando um container instalando o laravel

```sudo docker run -it --name php php:7.4-cli bash```

OBS: Caso a imagem não existir será criada a partir do download da mesma.

```apt-get update```

### 2 - Instalando o laravel dentro do diretório www

```mkdir /var/www```

```cd /var/www```

```php -v```

Versão PHP 7.4.33

#### Composer 

```php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"```

```php composer-setup.php```

```php -r "unlink('composer-setup.php');"```

```ls```

Vai aparece o composer.phar

#### Laravel 

```apt-get update && apt-get install -y zlib1g-dev libzip-dev unzip```

```docker-php-ext-install zip```

```php composer.phar create-project --prefer-dist laravel/laravel:^7.0 laravel```

```docker build -t develope/laravel:latest ```

```docker run --rm -d --name laravel -p 8000:8000 develope/laravel```

Passando parametro de outra porta para o CMD
```docker run --rm -d --name laravel -p 8001:8001 develope/laravel --host=0.0.0.0 --port=8001```