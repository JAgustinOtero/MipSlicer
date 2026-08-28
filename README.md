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
   cd meepslice
