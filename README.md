# 🎮 Spark • Splat Destroy (Click Radius)

Una experiencia interactiva 3D que combina Gaussian Splatting con física en tiempo real. Haz clic en los splats para crear explosiones con radio personalizable que desencadenan simulaciones físicas realistas.

![Splat Destroy Demo](https://img.shields.io/badge/Three.js-Interactive-blue?style=for-the-badge&logo=three.js)
![WebGL](https://img.shields.io/badge/WebGL-Enabled-green?style=for-the-badge)

## ✨ Características

- **Explosiones con Radio Interactivo**: Haz clic en cualquier splat para crear explosiones que afectan a todos los splats dentro de un radio configurable
- **Física Realista**: Simulación de gravedad, rebotes, fricción y amortiguamiento
- **Sistema de Impulsos Múltiples**: Hasta 128 explosiones simultáneas con efectos acumulativos
- **Depth Stacking**: Haz clic repetidamente en la misma área para alcanzar splats más profundos
- **Controles de Cámara Suaves**: Usa el mouse para explorar la escena 3D
- **GUI Interactiva**: Ajusta parámetros en tiempo real:
  - Fuerza de explosión (0.0 - 10.0)
  - Radio de explosión (0.1 - 1.0)
  - Gravedad (0.0 - 20.0)
- **Sistema de Reset**: Restaura el estado original del splat en cualquier momento

## 🚀 Tecnologías

- **Three.js**: Motor de renderizado 3D
- **Spark (@sparkjsdev/spark)**: Framework de Gaussian Splatting
- **lil-gui**: Interfaz de usuario para controles en tiempo real
- **WebGL**: Aceleración por hardware con shaders personalizados
- **Dyno Shaders**: Sistema de shaders dinámicos para efectos de física

## 🎯 Cómo Usar

1. **Exploración**: Mueve el mouse para mirar alrededor de la escena
2. **Destrucción**: Haz clic en cualquier splat visible para crear una explosión
3. **Depth Stacking**: Haz clic múltiples veces en el mismo lugar para penetrar capas más profundas
4. **Ajustes**: Usa el panel GUI (esquina superior derecha) para modificar:
   - **Explosion Strength**: Intensidad de la explosión
   - **Explosion Radius**: Área de efecto de la explosión
   - **Gravity**: Fuerza gravitacional aplicada
5. **Reset**: Haz clic en "Reset Splat" para restaurar todo al estado inicial

## 🔧 Instalación Local

```bash
# Clona el repositorio
git clone https://github.com/kali-shade/spark-splat-destroy.git

# Navega al directorio
cd spark-splat-destroy

# Sirve con un servidor HTTP local (ejemplo con Python)
python -m http.server 8000

# O con Node.js
npx http-server

# Abre en tu navegador
# http://localhost:8000
```

## 📦 Estructura del Proyecto

```
spark-splat-destroy/
├── index.html          # Aplicación principal con toda la lógica
└── README.md          # Este archivo
```

## 🎨 Características Técnicas

### Sistema de Física
- **Simulación de Caída**: Trayectorias balísticas con variación procedural
- **Rebote en el Suelo**: Sistema de rebotes múltiples con amortiguamiento
- **Fricción del Aire**: Desaceleración gradual de velocidades
- **Reducción de Escala**: Los splats se encogen antes de desaparecer

### Optimizaciones
- **Baking en CPU**: Las posiciones se actualizan en la CPU para raycasting preciso
- **Codificación Half-Float**: Compresión eficiente de datos de posición
- **Buffer Circular**: Gestión eficiente de hasta 128 impulsos simultáneos
- **Unión de Máscaras**: Múltiples explosiones se combinan de forma fluida

### Shaders Dinámicos
El proyecto utiliza el sistema Dyno para generar shaders en tiempo real que manejan:
- Detección de proximidad radial
- Simulación física por splat
- Interpolación de escalas
- Hash procedural para variación

## 🎮 Controles

| Acción | Control |
|--------|---------|
| Rotar cámara | Mover el mouse |
| Crear explosión | Click izquierdo |
| Depth stack | Clicks repetidos en el mismo lugar |
| Ajustar parámetros | Panel GUI (esquina superior derecha) |
| Resetear escena | Botón "Reset Splat" en GUI |

## 🌟 Asset Utilizado

El proyecto carga la escena **"painted-bedroom.spz"**, una habitación capturada con Gaussian Splatting que proporciona un entorno fotorealista para las simulaciones de física.

## 🐛 Solución de Problemas

**No detecta los clicks:**
- Aumenta el threshold del raycaster (actualmente configurado en 0.5)
- Asegúrate de hacer clic directamente sobre splats visibles
- Verifica la consola del navegador para mensajes de debug

**Rendimiento bajo:**
- Reduce el número de explosiones simultáneas
- Disminuye la resolución del pixel ratio
- Usa un navegador con buen soporte de WebGL 2.0

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Siéntete libre de:
- Reportar bugs
- Sugerir nuevas características
- Enviar pull requests

## 📄 Licencia

Este proyecto es de código abierto y está disponible bajo una licencia permisiva.

## 🔗 Enlaces Útiles

- [Three.js Documentation](https://threejs.org/docs/)
- [Gaussian Splatting](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)
- [WebGL Fundamentals](https://webglfundamentals.org/)

---

Desarrollado con ❤️ usando WebGL y Gaussian Splatting

