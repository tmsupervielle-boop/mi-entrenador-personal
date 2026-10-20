# Mi entrenador personal — v0.6 OneDrive local

## Qué cambia
- Ya no intenta iniciar sesión en Microsoft Entra ni usa MSAL.
- En Microsoft Edge o Chrome de escritorio, el usuario elige la carpeta de pruebas que está dentro de su carpeta OneDrive sincronizada en Windows.
- Lee y escribe `app-sync.json` dentro de esa carpeta. La app combina datos por ID y conserva los registros; no elimina elementos ni modifica los CSV/MD oficiales.
- El permiso de carpeta se recuerda en el navegador cuando el navegador lo permite.
- Los registros se guardan primero en el navegador. Si la carpeta tiene permiso, se programa una sincronización tras guardar. También se puede sincronizar manualmente.
- Mantiene exportación/importación JSON y la interfaz de peso, alimentación y carreras.

## Puesta en marcha
1. Descomprime esta carpeta en tu PC.
2. Abre `index.html` en Edge o Chrome. Si el navegador no permite elegir carpetas desde `file://`, sirve esta carpeta desde `localhost` o publícala en HTTPS; la API de acceso a archivos exige un contexto seguro.
3. En Historial, pulsa **Elegir carpeta de OneDrive**.
4. Selecciona `OneDrive\Documentos\Entrenador personal\APP_Mi_entrenador_personal_pruebas` (la ruta puede variar según tu configuración de OneDrive).
5. Pulsa **Sincronizar ahora**. Debe crearse/actualizarse `app-sync.json` en esa carpeta.

## Importante
- Esta solución aprovecha el cliente de sincronización de OneDrive para Windows; no requiere registro de aplicación ni credenciales.
- La sincronización automática es local a ese navegador/PC. En otro dispositivo hay que usar una copia de la app que pueda acceder a su carpeta local de OneDrive y seleccionar esa carpeta también.
- Los CSV y Markdown originales se dejan intactos; el archivo de datos de la app es independiente.
- No es una sincronización multiusuario ni resuelve conflictos simultáneos entre dos navegadores.
- Para sincronizar desde móvil sin tener una carpeta OneDrive local accesible, hará falta otro mecanismo; este paquete no promete sincronización móvil directa.
