# STRENGTHLAB Nutrición

Herramienta estática para elegir comidas, organizar una semana, registrar lo consumido y preparar un resumen para la asesoría.

## Funciones

- Inicio «Hoy», registro por fecha y registro de lo planificado con un toque.
- 18 comidas con ingredientes, estado del peso, preparación, porciones ajustables, favoritos y filtros.
- Menú semanal, repetición de días y lista de compras derivada de las porciones elegidas.
- Registros libres con notas y fotografías reducidas; edición y eliminación.
- Resumen semanal revisable, copiable, descargable o compartible mediante el navegador.
- Respaldo y recuperación en JSON. Validación del respaldo y aviso de fallos de almacenamiento.
- Navegación unificada en el menú hamburguesa: Hoy, Qué comer, Mi semana, Progreso y Calculadoras y guías.
- Herramientas originales agrupadas por pauta, calculadoras y guías prácticas, con botón para volver al catálogo.

## Datos y límites

Los registros se guardan en `localStorage` del navegador, con la clave `slab_companion_v1`. No hay cuenta, servidor de registros ni sincronización con el entrenador. El respaldo incluye las fotos y debe conservarse de forma privada. Un fallo de cuota muestra un aviso: los cambios no guardados permanecen temporalmente en memoria.

Las preferencias originales `sl_*` se conservan. Las comidas tienen valores nutricionales orientativos; no se generan prescripciones automáticas ni estimaciones desde fotografías. Los indicadores semanales miden registro, no cumplimiento nutricional. Las cantidades de compras conservan el estado de preparación indicado (cocido, seco, escurrido), no son conversiones a peso de compra crudo. Revisar valores y etiquetas antes de usar una receta como pauta individual.

Los textos educativos originales requieren una revisión nutricional independiente; esta actualización retira el bloque hormonal del inicio, las distribuciones genéricas que competían con la pauta individual y los «hacks» avanzados, pero no constituye una auditoría científica completa de la biblioteca anterior.

## Desarrollo y pruebas

Sin instalación ni compilación. Servir la carpeta con un servidor estático.

```sh
node --test tests/companion.test.cjs
```

Las pruebas cubren calendario, porciones, restricciones combinadas, validación del respaldo, escape de contenido, persistencia, registro duplicado, compras, copia de menús y fallos de almacenamiento. Los archivos `companion-data.js`, `companion.js` y `companion.css` implementan el acompañamiento diario; `index.html` conserva la guía original.
