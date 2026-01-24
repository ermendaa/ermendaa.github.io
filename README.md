# ermendaa.github.io
Web para visualizar el kiosco del IES FUERTE DE CORTADURA

# Welcome to your Expo app 👋
# 📺 KioscoApp - Cartelería Digital Educativa (Android TV / Web)
 
+Sistema de **Cartelería Digital (Digital Signage)** diseñado para centros educativos. Permite rotar información relevante (guardias, ausencias, noticias, tiempo) en pantallas de TV (Android TV) o dispositivos móviles, gestionado dinámicamente desde **Google Sheets**.
 
-   ```
+### 🔄 Sistema de Rotación (Carrusel):
+La aplicación rota automáticamente entre diferentes pantallas informativas:
+ - **Guardias:** Profesores de guardia en el tramo actual.
+ - **Ausencias:** Listado diario de profesores ausentes.
+ - **Actividades:** Eventos y actividades extraescolares.
+ - **Resumen:** Vista consolidada del día.
+ - **Noticias (RSS):** Feed de noticias configurable (ej: El Mundo).
+ - **El Tiempo:** Pronóstico meteorológico local.
+ - **WebViews:** Capacidad para incrustar hasta 2 páginas web externas.
 
-2. Start the app
+### 🚨 Sistema de Alertas Globales (Marquesina)
+Ticker de noticias desplazable en la parte inferior para avisos urgentes.
+- **Filtrado Temporal:** Se muestran solo si están vigentes (Fecha/Hora inicio y fin).
+- **Tipos de Alerta:**
+  - 🔵 **Info**
+  - 🟠 **Aviso**
+  - 🔴 **Urgente**
+  - 🟢 **Éxito**
 

+### 🔔 Guardia Override (Cambio de Clase)
+Detecta automáticamente los cambios de tramo horario (según configuración del centro).
+- **Interrupción:** Detiene el carrusel cuando suena el timbre.
+- **Pantalla Fija:** Muestra las guardias durante un tiempo configurable (ej: 5 min).
+- **Aviso Sonoro:** Reproduce un sonido para llamar la atención.
+- **Cuenta Atrás:** Visualización del tiempo restante de la pausa.
 

+### 🛠️ Administración Remota (Google Sheets)
+No requiere backend complejo. Toda la información se gestiona editando hojas de cálculo de Google publicadas como CSV.
+- **Sincronización:** Actualización automática cada 60 segundos.
+- **Indicador de Salud:** Icono (Nube) que indica si los datos están actualizados o si hay error de conexión.
 
+## 🚀 Instalación y Puesta en Marcha

+ Por realizar
+ 
+## ⚙️ Configuración y Uso
 
+### 1. Preparar los Datos (Google Sheets)
+Crea 4 hojas de cálculo (o pestañas) y publícalas como CSV (`Archivo > Compartir > Publicar en la web > CSV`).

+**Formatos de Columnas Esperados (Flexible):**
+*   **Guardias:** `Día`, `Tramo`, `Profesor`, `Zona`.
+*   **Alertas:** `Activo` (SI/NO), `Fecha Inicio`, `Fecha Fin`, `Hora Inicio`, `Hora Fin`, `Mensaje`, `Tipo`.
+*   **Ausencias:** `Profesor`, `Hora`, `Grupo`, `Aula`.
+*   **Actividades:** `Fecha`, `Hora`, `Actividad`, `Lugar`.
 
+### 2. Configuración en la App
+1. Abre la aplicación.
+2. Haz clic en el botón de engranaje (⚙️) en la esquina inferior derecha (o navega con el mando de la TV).
+3. Introduce el PIN de administrador (Por defecto: `1234`).
+4. En el menú, configura:
+    - **URLs:** Pega los enlaces CSV de tus hojas de Google.
+    - **Tiempos:** Intervalo de rotación y frecuencia de actualización.
+    - **Horarios:** Define los tramos horarios de tu centro.
+    - **Módulos:** Activa/Desactiva pantallas (Tiempo, RSS, WebViews).
 

+## 📱 Controles (Android TV)
+La interfaz está optimizada para navegación con D-Pad (Mando a distancia).
+- **Navegación:** Usa las flechas para mover el foco.
+- **Configuración:** Mueve el foco al icono ⚙️ y pulsa OK/Enter.
+
+---
+
+## 📂 Estructura del Proyecto
+
+```
+/
+├── assets/             # Imágenes y sonidos
+├── components/         # Componentes UI (Reloj, Alertas, etc.)
+├── context/            # Estado global (AppContext) y lógica de datos
+├── navigation/         # Navegación (Stack Navigator)
+├── screens/            # Pantallas principales (Guardia, Ausencias, Config...)
+├── services/           # Lógica de fetch (dataService)
+└── App.js              # Punto de entrada
+```
+
+## 📄 Licencia
+Este proyecto está bajo la Licencia MIT.

