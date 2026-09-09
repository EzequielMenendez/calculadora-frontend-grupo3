# Calculadora — Frontend

Interfaz web para consumir la API de la calculadora. Permite sumar, restar,
multiplicar y dividir dos valores, y muestra el historial cuando la API tiene
persistencia configurada.

## Ejecutar localmente

1. Iniciá la API en `http://127.0.0.1:8000`.
2. Desde esta carpeta, levantá un servidor estático:

   ```bash
   python -m http.server 5500
   ```

3. Abrí `http://127.0.0.1:5500` en el navegador.

La URL de la API se define en `config.js`. Para usar otra instancia, cambiá
`window.CONFIG.API_URL` antes de servir la página.

## Endpoints consumidos

- `POST /api/calcular`: realiza la operación elegida.
- `GET /api/salud`: informa si el historial está disponible.
- `GET /api/historial`: obtiene las últimas operaciones guardadas.

## Despliegue con Docker

La imagen admite la variable de entorno `API_URL`. Al iniciar, el contenedor
genera `config.js` con esa URL, por lo que el mismo `index.html` se puede usar
en desarrollo y producción.
