# Android Flutter Project

Este es un proyecto Flutter para Android con configuración estándar.

## 📋 Descripción

Aplicación Flutter nativa para Android con soporte para tema claro y oscuro, pantalla de inicio personalizable y configuración optimizada.

## 🚀 Características

- ✅ Soporte para Android
- 🌓 Tema claro y oscuro automático
- 🎨 Pantalla de inicio (splash screen) personalizable
- ⚡ Aceleración por hardware habilitada
- 📱 Configuración adaptativa de pantalla

## 📦 Estructura del Proyecto

```
android/
├── app/
│   └── src/
│       └── main/
│           ├── kotlin/com/example/android/
│           │   └── MainActivity.kt
│           ├── res/
│           │   ├── drawable/
│           │   │   └── launch_background.xml
│           │   ├── drawable-v21/
│           │   │   └── launch_background.xml
│           │   ├── values/
│           │   │   └── styles.xml
│           │   └── values-night/
│           │       └── styles.xml
│           └── AndroidManifest.xml
```

## 🛠️ Requisitos Previos

- Flutter SDK (última versión estable)
- Android Studio o VS Code con extensiones de Flutter
- JDK 11 o superior
- Android SDK (API level 21+)

## 📱 Instalación

1. **Clonar el repositorio**
   ```bash
   git clone <url-del-repositorio>
   cd android
   ```

2. **Instalar dependencias**
   ```bash
   flutter pub get
   ```

3. **Verificar dispositivos disponibles**
   ```bash
   flutter devices
   ```

4. **Ejecutar la aplicación**
   ```bash
   flutter run
   ```

## 🔧 Configuración

### Cambiar el nombre de la aplicación

Edita `AndroidManifest.xml`:
```xml
<application
    android:label="TuNombreAqui"
    ...>
```

### Cambiar el paquete

1. Renombra las carpetas en `src/main/kotlin/com/example/android/`
2. Actualiza el `package` en `MainActivity.kt`
3. Actualiza el `namespace` en `build.gradle`

### Personalizar Splash Screen

Edita `launch_background.xml` y descomenta la sección de imagen:
```xml
<item>
    <bitmap
        android:gravity="center"
        android:src="@mipmap/launch_image" />
</item>
```

### Cambiar el icono

Reemplaza los archivos en `res/mipmap/` con tus propios iconos o usa:
```bash
flutter pub run flutter_launcher_icons:main
```

## 🎨 Temas

La aplicación incluye soporte automático para tema claro y oscuro:

- **Tema Claro**: `values/styles.xml`
- **Tema Oscuro**: `values-night/styles.xml`

## 📝 Configuración del Manifest

### Permisos actuales
- Procesamiento de texto (PROCESS_TEXT)

### Para agregar más permisos:
```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.CAMERA"/>
```

## 🏗️ Build

### Debug
```bash
flutter build apk --debug
```

### Release
```bash
flutter build apk --release
```

### App Bundle (recomendado para Play Store)
```bash
flutter build appbundle --release
```

## 🔐 Firma de la Aplicación

1. Crea un keystore:
   ```bash
   keytool -genkey -v -keystore ~/key.jks -keyalg RSA -keysize 2048 -validity 10000 -alias key
   ```

2. Crea `android/key.properties`:
   ```properties
   storePassword=<password>
   keyPassword=<password>
   keyAlias=key
   storeFile=<ruta-al-keystore>
   ```

3. Configura en `app/build.gradle`

## 🧪 Testing

```bash
# Tests unitarios
flutter test

# Tests de integración
flutter drive --target=test_driver/app.dart
```

## 📊 Análisis de Código

```bash
flutter analyze
```

## 🐛 Debugging

```bash
# Modo debug con hot reload
flutter run

# Ver logs
flutter logs

# Inspeccionar el widget tree
flutter inspector
```

## 📚 Recursos Útiles

- [Documentación Flutter](https://flutter.dev/docs)
- [Cookbook Flutter](https://flutter.dev/docs/cookbook)
- [Documentación Android](https://developer.android.com)

## 🤝 Contribuir

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo `LICENSE` para más detalles.
