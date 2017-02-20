# Tesis ![Licencia](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

Este proyecto nacio como un for de http://github.com/ncuesta/tesis contiene los
fuentes para la tesis de grado en Universidad Nacional de La Plata, titulada
*Propuesta de una solución de Monitoreo para sistemas del CeSPI*.

Este proyecto puede utilizarse como base para otros tesinistas que estén
interesados en realizar su informe documental con LaTeX, intentando facilitar el
proceso de aprendizaje inicial y el de organización del proyecto.

## Licencia

Este proyecto se encuentra licenciado bajo una [Licencia Creative Commons
Atribución-CompartirIgual 4.0 Internacional](http://creativecommons.org/licenses/by-sa/4.0/).

## Generación del PDF de salida

Al generar la salida, el resultado queda en el directorio `pdf/`.

### Con Docker

Primero, descargar la imagen del container para ejecutar Latex:

```console
$ docker pull ncuesta/latex
```

> La descarga de la imagen se hace sólo la primera vez.

Luego, cada vez que querramos ejecutar Latex para generar la salida en PDF:

```console
$ docker run --rm -v "`pwd`:/latex" -i ncuesta/latex
```
