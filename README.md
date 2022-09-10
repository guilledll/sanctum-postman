## (ES) Configurar laravel Sanctum en Postman!

Relizado por [Simply UY en youtube](https://www.youtube.com/c/SimplyUY)

Mira [mi video completo que presenta como confugurar Laravel Sanctum](https://www.youtube.com/watch?v=bOL2TdwQdPg) con SPA para ser utilizado desde Postman!

## Configuración en Laravel

-   Modificación de entorno en `.env`
-   Modificación de configuración `sanctum.php`

## Configuración en Postman

-   Agregar srcipt pre-request
-   Agregar cabeceras correspondientes
-   Agregar srcipt test

### Pre-Request script

```js
pm.sendRequest(
    {
        url: "http://127.0.0.1:8000/sanctum/csrf-cookie",
        method: "GET",
    },
    function (error, response, { cookies }) {
        if (!error) {
            // Guarda la cookie en la variable "token"
            pm.environment.set("token", cookies.get("XSRF-TOKEN"));
        }
    }
);
```

### Script test

```js
if (pm.cookies) {
    pm.environment.set("token", pm.cookies.get("XSRF-TOKEN"));
}
```

Mira [el vídeo en youtube](https://www.youtube.com/watch?v=bOL2TdwQdPg) para completar el tutorial y entender que sucede por dentro del Framework!

## (EN) Laravel Sanctum setup on Postman!

A project of [Simply UY from Youtube](https://www.youtube.com/c/SimplyUY)

Watch [my full video on how to setup Laravel Sanctum](https://www.youtube.com/watch?v=bOL2TdwQdPg) with a SPA an use it on Postman!

## Laravel setup

-   Modify your environment file `.env`
-   Modify your configuration `sanctum.php`

## Postman Setup

-   Add srcipt pre-request
-   Add request headers
-   Add test script

### Pre-Request script

```js
pm.sendRequest(
    {
        url: "http://127.0.0.1:8000/sanctum/csrf-cookie",
        method: "GET",
    },
    function (error, response, { cookies }) {
        if (!error) {
            // Save the cookie to "token" variable
            pm.environment.set("token", cookies.get("XSRF-TOKEN"));
        }
    }
);
```

### Script test

```js
if (pm.cookies) {
    pm.environment.set("token", pm.cookies.get("XSRF-TOKEN"));
}
```

Watch [my full video on Youtube](https://www.youtube.com/watch?v=bOL2TdwQdPg) to complete this tutorial and understand what happend inside the Framework!
