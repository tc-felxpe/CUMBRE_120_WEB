# Cumbre 120 · Página web

Página para mostrar la app Cumbre 120 y descargar el APK de Android.
Es un sitio estático (HTML y CSS, sin compilar) que se publica con Vercel.

- `index.html` y `estilos.css`: la página, con los colores y letras de la app.
- `descargas/`: los APK firmados (arm64 para casi todos los teléfonos; 32 bits para los antiguos).
- `vercel.json`: hace que los `.apk` se descarguen como app de Android.

## Publicar una versión nueva de la app

1. En el proyecto de la app: `./gradlew assembleRelease`.
2. Copia `app/build/outputs/apk/release/app-arm64-v8a-release.apk` a `descargas/cumbre120-android.apk`
   y `app-armeabi-v7a-release.apk` a `descargas/cumbre120-android-32bits.apk`.
3. Actualiza en `index.html` la versión, el tamaño y la huella SHA-256 (`sha256sum descargas/*.apk`).
4. Commit y push: Vercel publica solo.
