# Finanzas Vida Nueva Internacional

Aplicación web para llevar las finanzas de la **Iglesia Cristiana Vida Nueva Internacional**: eventos de venta, cuentas por cobrar, ofrendas, gastos y saldo disponible.

Es un solo archivo HTML sin dependencias ni proceso de compilación. Funciona en computador y celular.

## Funciones

- **Panel:** saldo disponible, ingresos, egresos y lo que falta por cobrar, con filtro por periodo (todo, este año, este mes), gráfica de los últimos 6 meses, saldo por método de pago, últimos movimientos y próximos eventos.
- **Eventos de venta:** cada evento tiene clientes con producto o servicio, cantidad y valor por unidad. La app calcula el total por cliente y el total del evento. Cada cliente queda como *Pagado*, *Abono parcial* o *No pagado*, y cada pago guarda su fecha y método.
- **Calendario:** días de evento resaltados, más pagos recibidos, ofrendas y gastos de cada día.
- **Ofrendas:** quién dio, tipo (ofrenda, diezmo, primicia, pro-templo, misiones…), valor y método.
- **Gastos:** concepto, categoría, valor y método de pago.
- **Ajustes:** métodos de pago editables (vienen Nequi, Banco Caja Social y Efectivo) y copia de seguridad en JSON.

## Estructura

```
index.html        La aplicación completa (HTML, CSS y JavaScript)
assets/logo.jpg   Logo de la iglesia
```

## Cómo usarla

**En tu computador:** abre `index.html` con doble clic.

**Publicada con GitHub Pages:**

1. Sube estos archivos a un repositorio en GitHub.
2. Ve a **Settings → Pages**.
3. En *Source* elige **Deploy from a branch**, la rama `main` y la carpeta `/ (root)`.
4. En uno o dos minutos la app queda en `https://<tu-usuario>.github.io/<nombre-del-repo>/`.

También funciona en Netlify, Vercel o cualquier hosting de archivos estáticos.

## Dónde se guardan los datos

Los datos se guardan en el **almacenamiento local del navegador** (`localStorage`). Eso significa que:

- Cada navegador y cada dispositivo tiene sus propios datos. No se comparten entre personas.
- Si borras los datos de navegación o usas una ventana privada, se pierden.
- Subir el código al repositorio **no** sube los datos.

Por eso conviene ir a **Ajustes → Descargar copia** con frecuencia. Con **Restaurar copia** cargas ese archivo en otro navegador o dispositivo.

> Si varias personas van a registrar movimientos a la vez, hace falta una base de datos compartida (por ejemplo Firebase o Supabase). Las funciones `persist`, `saveMetodos`, `loadLocal` y `saveLocal` de `index.html` son el único punto que hay que cambiar para eso.

## Personalizar

Al inicio del `<script>` en `index.html` están las listas que puedes editar:

- `DEFAULT_METODOS`: métodos de pago iniciales.
- `TIPOS_OFRENDA`: tipos de ofrenda.
- `CATS_GASTO`: categorías de gasto.

Los colores están como variables CSS en `:root` (tema claro) y en los bloques de tema oscuro.
