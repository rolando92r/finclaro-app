# ⚙️ SETUP PASO A PASO PARA WINDOWS

Sigue exactamente estos pasos. Son fáciles, lo prometo.

## PASO 1: Instalar Node.js (5 min)

1. Ve a: https://nodejs.org/
2. **Descarga**: LTS (versión con soporte)
3. Instala: siguiente → siguiente → FINISH
4. **Reinicia tu PC**

**Verifica que funcionó:**
- Abre PowerShell (click derecho en escritorio → Windows PowerShell)
- Escribe:
```powershell
node -v
npm -v
```
- Debería mostrar números (ej: v18.16.0)

## PASO 2: Descargar Este Proyecto

### OPCIÓN A: Git (lo fácil)
```powershell
# Abre PowerShell en C:\Users\TuNombre\Descargas (o donde quieras)
cd Descargas

# Clona el repo
git clone https://github.com/rolando92r/finclaro-app.git
cd finclaro-app
```

### OPCIÓN B: ZIP (si no tienes Git)
1. Ve a GitHub: https://github.com/rolando92r/finclaro-app
2. Botón verde "Code" → Download ZIP
3. Extrae en C:\Users\TuNombre\Descargas
4. Abre PowerShell ahí:
```powershell
cd finclaro-app
```

## PASO 3: Instalar Dependencias (3-5 min)

```powershell
npm install
```

Espera a que termine (verás muchas líneas). ☕

## PASO 4: Primera Sincronización con Android

```powershell
npx cap sync
```

Esto genera la carpeta `android/` automáticamente.

## PASO 5: Compilar APK

### OPCIÓN A: GitHub Actions (AUTOMÁTICO, RECOMENDADO)

**Si ya subiste a GitHub:**
```powershell
git add .
git commit -m "Setup inicial"
git push origin main
```

Luego:
- Ve a: https://github.com/rolando92r/finclaro-app/actions
- Espera 20-30 min a que compile
- Click en el build que dice "Build Android APK"
- Scroll abajo: "Artifacts" → descarga `FinClaro-APK`
- Dentro hay `app-release.apk` ← ESTA ES TU APP

### OPCIÓN B: Android Studio (MANUAL)

1. **Descarga Android Studio:**
   - https://developer.android.com/studio
   - Instala (siguiente-siguiente)
   - Instala SDK cuando lo pida

2. **Abre el proyecto:**
```powershell
npx cap open android
```

3. **En Android Studio:**
   - Build → Generate Signed Bundle/APK
   - APK
   - Next
   - Crea un archivo de "keystore" (click "Create new")
     - Password: algo seguro (ej: "MiPassword2024!")
     - Same password para key password: SÍ
     - Nombre de la empresa: Tu nombre
     - Finish
   - Selecciona release
   - Finish
   - Espera 10-15 min

4. **Busca el APK:**
   - Debería estar en: `android/app/release/app-release.apk`
   - ¡Ese es tu app!

## PASO 6: Instalar en tu Samsung

1. **Descargaste `app-release.apk`**
2. Copia a tu teléfono por cable USB:
   - Conecta cable
   - Windows te pregunta qué hacer
   - Click "Transfer files"
   - Copia el APK a Descargas de tu teléfono
   
   O envíate por Telegram (más fácil):
   - Descarga Telegram
   - Envíate el APK a ti mismo
   - Abre en el teléfono

3. **En tu Samsung:**
   - Abre Archivos → Descargas
   - Busca `app-release.apk`
   - Toca → "Instalar"
   - Si te pregunta sobre fuentes desconocidas: "Permitir"
   - Espera a que instale
   - "Abrir" → ¡LISTO!

## PASO 7: Usar FinClaro

1. **Abre FinClaro** desde tu pantalla de inicio
2. Toca 💊 **Salud** → Agrega tu primera medicina
3. ¡Las alertas se programarán automáticamente!

## 🐛 SI ALGO FALLA

### Error: "node: command not found"
- Node.js no se instaló bien
- Reinicia Windows completamente
- Intenta de nuevo

### Error: "Cannot find module"
```powershell
npm install
npx cap sync
```

### APK no se instala
- Desinstala cualquier versión anterior de FinClaro
- Intenta de nuevo
- Si sigue fallando, compila en Android Studio

### Las notificaciones no suenan
- En tu Samsung: Configuración → Aplicaciones → FinClaro → Notificaciones → Encendidas
- Reinicia el teléfono
- Intenta de nuevo

---

## ✅ Checklist Final

- [ ] Node.js instalado (verifica con `node -v`)
- [ ] Proyecto descargado
- [ ] `npm install` completó sin errores
- [ ] APK generado
- [ ] APK copiado a teléfono
- [ ] APK instalado en Samsung
- [ ] Puedes abrir FinClaro
- [ ] Agregaste una medicina
- [ ] Recibiste una notificación a la hora

**¡Si todo esto funciona, eres un campeón!** 🎉

---

**Preguntas frecuentes:**
- "¿Por qué tardan 20 minutos en compilar?" → Android Studio es lenta, es normal
- "¿Funciona sin internet?" → Sí, 100% offline
- "¿Mis datos se suben a la nube?" → No, todo está en tu teléfono
- "¿Puedo actualizar la app?" → Sí, haz cambios + `git push` y GitHub lo compila de nuevo

