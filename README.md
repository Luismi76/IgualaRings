# IgualaRings 🕯️

**Dispositivo wearable para capataces de pasos**  
Sistema electrónico para ayudar a igualar las trabajaderas de un paso, mediante dos anillos inteligentes que miden la altura de apoyo de los costaleros y ofrecen una señal visual/háptica al capataz.

---

## 🎯 Objetivo
Tradicionalmente, el capataz iguala los costaleros comparando la altura con sus pulgares.  
IgualaRings moderniza este proceso con tecnología:

- Dos anillos en los pulgares del capataz.
- Sensores de distancia (ToF) miden la altura respecto al suelo.
- Comunicación BLE entre anillos.
- LED RGB indica la diferencia de altura:  
  - 🟢 Verde: igualados (≤ 5 mm)  
  - 🟡 Amarillo: diferencia leve (5–12 mm)  
  - 🔴 Rojo: diferencia clara (> 12 mm)  
- Vibración opcional para feedback discreto.  

---

## 📂 Estructura del repositorio

```
IgualaRings/
├── firmware/        # Código Arduino/ESP-IDF
│   ├── ring_minimal.ino
│   └── ring_ble_sync/
├── hardware/        # KiCad
│   ├── netlist.xml
│   ├── footprints.csv
│   ├── igualitasymbols.kicad_sym
│   └── pcb_outline.dxf
├── mechanical/      # Modelos 3D STL/STEP
│   └── ring_case_v1.stl
├── docs/            # Manuales, imágenes y esquemas
│   ├── schematic.pdf
│   └── renders/
└── README.md        # Este archivo
```

---

## 🛠️ Hardware (versión prototipo V1)
- **MCU BLE:** ESP32-C3 SuperMini  
- **Sensor ToF:** VL53L1X (0.2–4 m)  
- **LED RGB:** WS2812B Mini  
- **Switch contacto:** micro-switch SMD  
- **Motor vibrador:** coin 10 mm (opcional)  
- **Alimentación:** USB-C (V1) o LiPo + TP4056 + LDO 3.3V (V2)  

---

## ⚙️ Firmware
- Lectura de altura con VL53L1X.
- Corrección de inclinación (IMU opcional en V2).
- Comunicación BLE entre anillos.
- Indicación visual (LED) y háptica (motor) según diferencia.

---

## 📐 Mecánica
- Carcasa impresa en 3D (PLA/TPU).
- Plataforma sobre la uña → LED visible para el capataz.
- Yema libre para contacto natural con el costalero.
- Ventana para el sensor ToF mirando hacia abajo.

---

## 🚀 Roadmap
- [x] Definir arquitectura electrónica.  
- [x] Esquemático inicial y BOM.  
- [ ] Prototipo en breadboard.  
- [ ] Diseño de carcasa y primer STL.  
- [ ] PCB compacta V1.  
- [ ] Ensayos con capataz en trabajadera real.  

---

## 📜 Licencia
Este proyecto se distribuye bajo licencia **MIT** para software y **CERN OHL** para hardware.  
El objetivo es que pueda ser libremente usado y mejorado por la comunidad.

---

## 🤝 Contribuciones
¡Todas las ideas y mejoras son bienvenidas!  
Abre un **Issue** para sugerencias o un **Pull Request** si quieres colaborar con código, hardware o diseño mecánico.
