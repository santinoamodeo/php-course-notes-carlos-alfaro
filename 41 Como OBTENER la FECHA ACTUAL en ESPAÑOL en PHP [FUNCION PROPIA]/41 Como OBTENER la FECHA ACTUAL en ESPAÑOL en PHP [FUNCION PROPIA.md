# 41 Como OBTENER la FECHA ACTUAL en ESPAÑOL en PHP [FUNCION PROPIA]
## 1. Definir zona horaria

[Zonas horarias - Manual PHP](https://www.php.net/manual/es/function.date-default-timezone-set.php)

```php
#Funcion base
date_default_timezone_set()
```
* Ingrsar a listado de zonas horarias
* Copiar la correspondiente y pegarla en la funcion, dentro de un string

```php
#Funcion con zona horaria
date_default_timezone_set('America/Argentina/Buenos_Aires')
```

## 2. Creacion de funcion propia
### Fecha larga
```php
<?php
date_default_timezone_set('America/Argentina/Buenos_Aires');

function fecha_espanol_larga(){
    $fecha_dia = date('d');
    $fecha_mes = date('m');
    $fecha_year = date('Y');

    $dia_semana=[
        'Monday' => 'Lunes',
        'Tuesday' => 'Martes',
        'Wednesday' => 'Miercoles',
        'Thursday' => 'Jueves', 
        'Friday' => 'Viernes',
        'Saturday' => 'Sabado',
        'Sunday' => 'Domingo'
    ];

    $meses_year=[
        '01'=>'Enero',
        '02'=>'Febrero',
        '03'=>'Marzo',
        '04'=>'Abril',
        '05'=>'Mayo',
        '06'=>'Junio',
        '07'=>'Julio',
        '08'=>'Agosto',
        '09'=>'Septiembre',
        '10'=>'Octubre',
        '11'=>'Noviembre',
        '12'=>'Diciembre'
    ];

    $fecha_final = $dia_semana[date('l')].' '.$fecha_dia.' de '.$meses_year[$fecha_mes].' de '.$fecha_year;

    return $fecha_final;
}

echo fecha_espanol_larga();
```

### Fecha corta
```php
<?php
date_default_timezone_set('America/Argentina/Buenos_Aires');

function fecha_espanol_corta($fecha=''){

    if($fecha == ''){
        $fecha = date('d-m-Y');
    }else{
        $fecha = date('d-m-Y', strtotime($fecha));
    }

    $fecha = explode('-', $fecha);

    $fecha_dia = $fecha[0];
    $fecha_mes = $fecha[1];
    $fecha_year = $fecha[2];

    $dia_semana=[
        'Monday' => 'Lunes',
        'Tuesday' => 'Martes',
        'Wednesday' => 'Miercoles',
        'Thursday' => 'Jueves', 
        'Friday' => 'Viernes',
        'Saturday' => 'Sabado',
        'Sunday' => 'Domingo'
    ];

    $meses_year=[
        '01'=>'Enero',
        '02'=>'Febrero',
        '03'=>'Marzo',
        '04'=>'Abril',
        '05'=>'Mayo',
        '06'=>'Junio',
        '07'=>'Julio',
        '08'=>'Agosto',
        '09'=>'Septiembre',
        '10'=>'Octubre',
        '11'=>'Noviembre',
        '12'=>'Diciembre'
    ];

    $fecha_final = $fecha_dia.' de '.$meses_year[$fecha_mes].' de '.$fecha_year;

    return $fecha_final;
}

echo fecha_espanol_corta('01-01-2020');
```