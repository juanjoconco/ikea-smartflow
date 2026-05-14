# IKEA SmartFlow — Guía de despliegue paso a paso
## Para tenerlo listo en ~10 minutos y mostrarlo en clase

---

## ¿Qué tienes?
Dos archivos:
- `index.html` — toda la app
- `manifest.json` — configuración PWA (para que se vea como app en el celular)

---

## OPCIÓN A — Vercel (recomendado, más rápido)

### Paso 1: Crea una cuenta en Vercel
- Ve a https://vercel.com → Sign Up → continúa con GitHub o con email

### Paso 2: Sube los archivos
1. En el dashboard de Vercel, haz clic en **"Add New → Project"**
2. Selecciona **"Deploy from CLI"** o busca la opción **"Import Third-Party Git"**
   
   **Alternativa más fácil (sin Git):**
   - Ve a https://vercel.com/new
   - Arrastra la carpeta `ikea-smartflow` directamente al área de drop
   - Vercel detecta automáticamente que es un sitio estático
   - Clic en **Deploy**

3. En ~30 segundos tendrás un link tipo: `https://ikea-smartflow-xxxx.vercel.app`

### Paso 3: Comparte el link en clase
- Envía el link por WhatsApp a tus compañeros
- Ellos lo abren en su celular → se ve y funciona como una app real
- En iPhone: pueden tocar "Compartir → Agregar a pantalla de inicio" para instalarla como app

---

## OPCIÓN B — Netlify (igual de fácil)

1. Ve a https://app.netlify.com/drop
2. Arrastra la carpeta `ikea-smartflow`
3. En segundos tienes un link público
4. ¡Listo!

---

## OPCIÓN C — Ver localmente en tu celular (sin internet)

Si tienes Python instalado:
```bash
cd ikea-smartflow
python -m http.server 8080
```
Luego en tu celular (en la misma red WiFi): abre `http://TU-IP-LOCAL:8080`

Si tienes Node.js:
```bash
npx serve ikea-smartflow
```

---

## ¿Qué funciona en el MVP?

| Pantalla | Función |
|---|---|
| 🏠 Inicio | Explorar ambientes, buscar, ver productos recomendados |
| 📷 Escanear | Simula escaneo QR tocando productos → los agrega a la lista |
| ❤️ Mi lista | Ver productos, cambiar cantidades, ver total estimado |
| 📍 Mapa | Ruta inteligente en tienda, avanzar por paradas |
| 🎯 Reto IKEA | Smart Hunt — completa desafíos y acumula puntos |

### Para el demo en clase:
1. Abre la app en tu celular
2. Ve a **Escanear** → toca los productos para simular el QR
3. Ve a **Mi Lista** → muestra los productos guardados y el total
4. Toca **"Ver mi ruta en la tienda"** → muestra el mapa con paradas
5. Ve a **Reto IKEA** → toca los desafíos para completarlos y ganar puntos

---

## Personalización rápida (opcional)

Para cambiar precios o productos, abre `index.html` y edita el objeto `products` (línea ~215):
```javascript
const products = {
  sofa:{..., price:2199900, ...},
  mesa:{..., price:79900, ...},
  ...
};
```

---

## Próximos pasos (versión real)

1. **Backend**: Node.js + Firebase para datos reales
2. **Cámara QR real**: Librería `html5-qrcode` (1 línea de código)
3. **Mapa real**: Indoor navigation con BeaconInside o Mapbox
4. **Autenticación**: Firebase Auth
5. **Big Data**: Firebase Analytics + BigQuery

---
*IKEA SmartFlow MVP — Generado para presentación académica*
