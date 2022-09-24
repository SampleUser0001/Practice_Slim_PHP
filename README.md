# Practice_Slim_PHP

## 実行

``` bash
composer install
composer run start
```

## URL

localhost:8080

## 構築

1. 下記実行
    ``` bash
    composer require slim/slim:"4.*"
    composer require slim/psr7
    ```
2. ```public/index.php```作成
3. ```public/index.php```に下記を貼り付け
    ```php
    <?php
    use Psr\Http\Message\ResponseInterface as Response;
    use Psr\Http\Message\ServerRequestInterface as Request;
    use Slim\Factory\AppFactory;

    require __DIR__ . '/../vendor/autoload.php';

    $app = AppFactory::create();

    $app->get('/', function (Request $request, Response $response, $args) {
        $response->getBody()->write("Hello world!");
        return $response;
    });

    $app->run();
    ```
4. 下記実行
    ``` bash
    php -S localhost:8080 -t public public/index.php
    ```

## 参考

- [Slim Framework](https://www.slimframework.com/)