# FinClaro 💚

**App de Control Financiero con Alertas de Medicinas Nativas de Android**

Control completo de tus gastos, ingresos, servicios y medicinas — TODO EN UN SOLO LUGAR. Con notificaciones nativas que funcionan **incluso con la app cerrada**.

## 🎯 Características

- ✅ **Gastos e Ingresos** — registra todo con método de pago
- ✅ **Me Deben** — seguimiento de dinero pendiente
- ✅ **Mis Servicios** — cobra a tus clientes
- ✅ **💊 MEDICINAS CON ALERTAS NATIVAS** — suena a la hora, todos los días, ¡con app cerrada!
- ✅ **Notas y Recordatorios**
- ✅ **Análisis** — reportes de gastos por categoría
- ✅ **Respaldo** — exporta/importa JSON
- ✅ **Tema Claro/Oscuro**

## 🚀 Instalación Rápida

### Requisitos
- Node.js 18+ ([descargar](https://nodejs.org/))
- Cuenta GitHub (gratis)
- Android 8+ en tu teléfono

### Paso 1: Clonar y Configurar

```bash
# Clona este repo (o descargar como ZIP)
git clone https://github.com/TU-USUARIO/finclaro-app.git
cd finclaro-app

# Instala dependencias (primera vez, ~5 min)
npm install

# Sincroniza con Android
npx cap sync

# Abre en Android Studio (opcional, para compilar manualmente)
npx cap open android
```

### Paso 2: Compilar APK

**OPCIÓN A: GitHub Actions (AUTOMÁTICO)** ⭐
```bash
# Solo sube cambios a GitHub
git add .
git commit -m "Actualización"
git push origin main

# GitHub compila automáticamente en ~20 min
# Ve a: https://github.com/TU-USUARIO/finclaro-app/actions
# Descarga el APK en "Artifacts"
```

**OPCIÓN B: Android Studio (manual)**
```bash
# Abre en Android Studio
npx cap open android

# Build → Generate Signed Bundle/APK
# Selecciona APK, crea key, genera
# APK aparece en: android/app/release/
```

### Paso 3: Instalar en tu Samsung

1. Descarga `app-release.apk`
2. Copia a tu teléfono (por cable o Telegram)
3. Abre el archivo con "Instalador de apps"
4. Instala (permite fuentes desconocidas)
5. ¡Abre FinClaro desde tu pantalla de inicio!

## 💊 Alertas de Medicinas (Lo MÁS IMPORTANTE)

Cuando guardas una medicina:
1. **Elige horas** (ej: 8:00 AM, 8:00 PM)
2. **FinClaro programa alertas nativas** en Android
3. **A esa hora suena, vibra y notifica** — ¡incluso con app cerrada!
4. Toca "Marcar como tomada" y se registra el inventario

**Notas críticas:**
- Las alertas se repiten TODOS LOS DÍAS a esa hora
- No necesitas tener la app abierta
- Funciona en Modo Avión, sin internet
- Medicinas del corazón: úsalo como recordatorio principal + alarma del reloj como backup

## 📝 Primeros Pasos en la App

### 1. Medicinas (PRIMERO)
```
💊 Salud → ➕ Agregar medicina
- Nombre: Losartán
- Para qué: ❤️ Corazón
- Horas: 8:00 AM, 8:00 PM
- Guardar
✅ Alertas programadas automáticamente cada día
```

### 2. Gastos
```
📝 Gastos → Registra compras
- Categoría: Comida
- Monto: $50
- Pagué con: PayPal
- Guardar
```

### 3. Ingresos
```
💵 Ingresos → Cuando te paguen
- Tipo: Trabajo Independiente
- Monto: $200
- Me pagaron por: Zelle
- ¿Quién pagó?: Cliente XYZ
- Guardar
```

### 4. Análisis
```
📊 Análisis → Ve tus totales
- Gráficos por categoría
- Balance del mes
- Descargar PDF
```

## 🔧 Estructura del Proyecto

```
finclaro-app/
├── www/
│   └── index.html          # Tu app completa
├── android/                # Generado por Capacitor
├── package.json            # Dependencias
├── capacitor.config.json   # Config de Capacitor
├── .github/workflows/
│   └── build-android.yml   # GitHub Actions (compila solo)
└── README.md               # Esto
```

## 📱 Tecnología

- **Frontend:** HTML + CSS + JavaScript Vanilla
- **Nativo:** Capacitor + LocalNotifications (Android)
- **Almacenamiento:** SQLite (local en teléfono)
- **Compilación:** Gradle + GitHub Actions

## 🛠️ Desarrollo Local

```bash
# Instalar dependencias nuevas
npm install @capacitor/TU-PLUGIN

# Sincronizar cambios
npx cap sync

# Abrir en Android Studio
npx cap open android

# Compilar APK
cd android && ./gradlew assembleRelease
# APK en: android/app/build/outputs/apk/release/app-release.apk
```

## ⚠️ Problemas Comunes

### "Cannot find module '@capacitor/...'"
```bash
npm install
npx cap sync
```

### "Gradle build failed"
```bash
cd android
./gradlew clean
./gradlew assembleRelease
```

### "Notificaciones no funcionan"
- Verifica permisos en Settings → Apps → FinClaro → Notifications (encendido)
- Reinicia el teléfono
- Borra caché: Settings → Apps → FinClaro → Storage → Clear Cache

### "APK no se instala"
- Desinstala versión anterior
- Verifica que sea arquitectura compatible (descarga x86_64)

## 📞 Soporte

Para problemas:
1. Revisa Console en Android Studio: `npx cap open android`
2. Busca en GitHub Issues
3. Abre un Issue nuevo con:
   - Tu SO (Android version)
   - Qué intentaste
   - Mensaje de error exacto

## 📄 Licencia

MIT - Usa, modifica, distribuye libremente.

## 🎉 ¡Listo!

Ahora tienes:
- ✅ App de finanzas en tu teléfono
- ✅ Alertas de medicinas nativas (¡nunca olvides!)
- ✅ Todo offline (sin internet)
- ✅ Datos 100% privados (no suben a la nube)
- ✅ APK actualizándose automáticamente en GitHub

**¡Descarga, instala, y controla tus medicinas sin estrés!** 💊🎯

---

Hecho con ❤️ para Augusto Rolando
