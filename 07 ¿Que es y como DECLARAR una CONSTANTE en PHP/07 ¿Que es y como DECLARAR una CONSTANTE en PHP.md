# 07 ¿Que es y como DECLARAR una CONSTANTE en PHP?

* Son constantes como en todo lenguaje de programacion, **NO se redefinen**
* Van siempre en **mayuscula**
```php
<?php
    // Definicion antigua
    define("NOMBRE", "Santino");
    echo NOMBRE;

    // Definicion nueva
    const APELLIDO = "Amodeo";
```

### Constantes magicas (no utilizar sus referencias)
* __FILE__
* __DIR__
* __LINE__
* __FUNCTION__
* __CLASS__
* __TRAIT__
* __METHOD__
* __NAMESPACE__