# 📐 MeepSlice - CAD Radial Profile Analyzer & Serial Control

**MeepSlice** es una aplicación de escritorio desarrollada en Python con **CustomTkinter**. Permite cargar archivos DXF de diseño asistido por computadora (CAD), calcular su perfil radial dinámico desde un centro geométrico predeterminado o detectado, y enviar estos comandos junto con instrucciones de control CNC/G-code a través de comunicación serie (UART/Arduino).

---

## 🛠️ Requisitos previos

Asegúrate de tener instalado **Python 3.8** o superior en tu sistema.

### Dependencias requeridas

El programa utiliza las siguientes librerías de Python:

* `customtkinter` (Interfaz gráfica moderna)
* `ezdxf` (Lectura y procesamiento de archivos CAD DXF)
* `numpy` (Cálculos numéricos e interpolación)
* `pyserial` (Comunicación por puerto serie)

---

## 🚀 Instalación y Ejecución

1. **Clonar el repositorio** (o descargar el código fuente):
   ```bash
   git clone [https://github.com/tu-usuario/meepslice.git](https://github.com/tu-usuario/meepslice.git)
   cd mipslice
   pip install customtkinter ezdxf numpy pyserial
   python analizador_radial_v4.py

📖 Guía de Uso Básica
La interfaz se divide en dos secciones principales organizadas en pestañas:

1. Pestaña: Análisis CAD
   Cargar DXF: Haz clic en el botón Cargar DXF y selecciona tu archivo .dxf.

   Centro y Referencia:
   Haz clic en Detectar centro para encontrar automáticamente la entidad CIRCLE más grande dentro del archivo.
   Si no hay un círculo de referencia, puedes ingresar las coordenadas X e Y manualmente.
   
   Configurar el Análisis:
   Selecciona la Resolución angular deseada (p. ej., 1.0°).
   Elige el sentido de barrido (Antihorario u Horario).
   Ejecutar: Haz clic en ANALIZAR 360°.
   La tabla se llenará con los pares de Ángulo (°) y Distancia (mm).
   
   Enviar G99: Una vez completado el análisis, se habilitará el botón ENVIAR G99. Al presionarlo, el vector de distancias se enviará    por la conexión serie activa y te redirigirá a la pestaña de control.

2. Pestaña: Control y Terminal
   Conexión Serie:
   Selecciona el Puerto COM de tu dispositivo (ej. Arduino). (Usa el botón Actualizar si no aparece).
   Selecciona el Baudrate (por defecto 115200).
   Presiona CONECTAR.
   
   Panel de Control Manual:
   Configura las magnitudes de paso para los ejes lineales (X/Z) y rotacional (Y).
   Utiliza la cruceta de botones para mover los ejes, ejecutar giros o volver a la posición de origen (HOME).
   Controla el Motor Auxiliar (ON / OFF).
   
   Inicio de Trabajo:
   El botón INICIO se habilitará automáticamente cuando el sistema reciba la confirmación del comando G99 desde el microcontrolador.
   
   Terminal Serie:
   Monitoriza las respuestas recibidas en tiempo real (<<).
   Envía comandos en G-Code de forma manual mediante el cuadro de texto inferior (>>).

🎨 Opciones de Apariencia
Puedes cambiar en cualquier momento entre Modo Oscuro y Modo Claro utilizando el interruptor ubicado en la esquina superior   derecha de la aplicación. La interfaz y las tablas adaptarán sus colores dinámicamente.
