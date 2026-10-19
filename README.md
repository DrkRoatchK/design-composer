# Design Composer · abierto

Un editor de piezas gráficas (posts, stories, banners, carteles) que corre en **un solo archivo HTML**, sin servidor ni instalación.
Pinta con el **codec** ([DrkRoatchK/codec](https://github.com/DrkRoatchK/codec)): cada módulo de capa es una *palabra* de datos y un solo motor
la convierte en dibujo. Por eso un diseño hecho aquí lo puede leer, cambiar y volver a pintar **cualquier IA o programa**, sin abrir el editor.

**Úsalo:** abre `index.html` (o la página de GitHub Pages de este repo).

- Plantillas · lienzos · capas con caja, profundidad Z y orden · textos con tipografías tuyas · imágenes de tu compu · mockups en perspectiva.
- **Karen** revisa antes de exportar: un solo fondo, nada se encima sin querer, todo dentro de la pieza, el texto cabe.
- Exporta PNG en todos los formatos de la plantilla; **Guardar** baja el diseño como JSON (liviano o portátil).

## El diseño es un JSON (para IAs)

```
{"tipo":"lyon_spark.composer.diseno","version":1,"arbol":{"tag":"pieza","data":{"formato":{"id":"sq","w":1080,"h":1080},…},
 "children":[{"tag":"capa","nid":"c1","data":{"modulo":"MC-TEXTO","z":10,"caja":[0.1,0.1,0.8,0.2],"campos":{"texto":"Hola"}}}, …]}}
```

`caja` = [x, y, ancho, alto] en fracciones de la pieza (0–1) · `z` = orden · `modulo` = una palabra de `palabras/PINTURA.json` del codec.
Con el codec: `python ejemplos/pintar_pieza.py tu_diseno.json` lo pinta en HTML sin este editor. Ejemplo: `ejemplos/pieza.json`.

Hecho por **Lyon Spark** · Democratizando el marketing y la comunicación.
