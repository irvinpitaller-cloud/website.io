📋 Catálogo Técnico Euroalum 4000 — Base de Datos Paramétrica

A continuación te presento la información extraída y estructurada en tablas normalizadas listas para importar a una base de datos, junto con lógica paramétrica, representación vectorial y casos de uso.

---

1. 🗂️ ESTRUCTURA DE BASE DE DATOS (Esquema Relacional)

1.1 Tabla: perfiles (Catálogo de extrusión)

codigo nombre tipo ancho_mm alto_mm espesor_pared_mm aleacion temple acabado requiere_pintura
2297 Hoja Ventana Perfil 35.85 23.30 — 6063 T5 Natural No
2298 Hoja Ventana Duo Perfil — — — 6063 T5 Natural No
2301 Hoja Ventana Ap. Ext. Perfil 52.80 — — 6063 T5 Natural No
2302 Marco Perfil 52.80 — — 6063 T5 Natural No
2314 Riel Doble Perfil 69.61 41.39 — 6063 T5 Natural No
2316 Hoja Puerta Perfil — — — 6063 T5 Natural No
2319 Hoja Puerta Duo Perfil — — — 6063 T5 Natural No
2333 Junquillo Redondo Perfil 16.45 23.30 — 6063 T5 Natural No
2334 Hoja Ventana Ap. Ext. Perfil 52.80 — — 6063 T5 Natural No
2344 Adaptador Traslape Puerta Perfil 46.82 — — 6063 T5 Natural No
2346 Perfil (ensamble) Perfil — — — 6063 T5 Natural No
2349 Junquillo Redondo Duo Perfil 16.45 23.30 — 6063 T5 Natural No
2361 Perfil (ensamble) Perfil — — — 6063 T5 Natural No
12009 Perfil Fijo Perfil 69.10 — — 6063 T5 Natural No
12010 Junquillo Redondo Duo Perfil 32.46 13.05 — 6063 T5 Natural No
12012 Junquillo Redondo Perfil 32.46 13.05 — 6063 T5 Natural No
12013 Fijo Perfil 69.10 — — 6063 T5 Natural No
12015 Intermedio Perfil 69.10 52.51 — 6063 T5 Natural No
12016 Refuerzo Perfil 30.13 50.80 — 6063 T5 Natural No
2188 Tapa Refuerzo Perfil 50.80 19.94 — 6063 T5 Natural No
2214 Guía de Refuerzo Perfil — — — 6063 T5 Natural Sí
2218 Perfil de Refuerzo Perfil — — — 6063 T5 Natural No
2219 Pletina Perfil 26.41 — — 6063 T5 Natural No
2236 Intermedio Perfil 71.42 43.54 — 6063 T5 Natural No
2251 Guía de Refuerzo Perfil — — — 6063 T5 Natural No
2276 Adaptador Traslape Perfil 65.40 — — 6063 T5 Natural No
2059 Mosquitero Perfil 28.34 — — 6063 T5 Natural No

Nota: Medidas en pulgadas → mm. Ej: 2.740" = 69.61 mm, 1.630" = 41.39 mm.

---

1.2 Tabla: sistemas (Tipologías de ventana/puerta)

id nombre descripcion perfiles_principales vidrio_tipo vidrio_formula
SYS-01 Ventana Corrediza 2 hojas, mosquitero 2314, 2297, 2276 6mm 2 × ((H-206)/2) × (V-166)
SYS-02 Puerta Corrediza Duo 2 hojas, vidrio duo 2314, 2319, 2344 Duo 6+1/4+6 2 × ((H-266)/2) × (V-205)
SYS-03 Ventana Oscilobatiente con Mosquitero 1 hoja + mosquitero 2302, 2301, 2349, 2059, 2219 Duo 6+3/8+6 2 × (H-178) × (V-178)
SYS-04 Ventana Proyectante 1 hoja 2302, 2334, 2349 Duo 6+3/8+6 1 × (H-178) × (V-178)
SYS-05 Fijo Sin apertura 12009, 12013, 2314 6mm / Duo —

---

1.3 Tabla: formulas_corte (Lógica paramétrica)

sistema clave descripcion cantidad corte formula
SYS-01 2314 Riel Doble 2 45° H H
SYS-01 2314 Riel Doble 2 45° V V
SYS-01 2297 Hoja Ventana 4 45° (H+2)/2
SYS-01 2297 Hoja Ventana 4 45° V V-62
SYS-01 2276 Adaptador Traslape 2 90° V V-65
SYS-02 2314 Riel Doble 2 45° H H
SYS-02 2314 Riel Doble 2 45° V V
SYS-02 2319 Hoja Puerta Duo 4 45° (H+22)/2
SYS-02 2319 Hoja Puerta Duo 4 V V-62
SYS-02 2344 Adaptador Traslape Puerta 2 90° V V-65
SYS-03 2302 Marco 2 45° H H
SYS-03 2302 Marco 2 45° V V
SYS-03 2301 Hoja Ventana Ap. Ext. 2 45° H H-66
SYS-03 2301 Hoja Ventana Ap. Ext. 4 5° V V-66
SYS-03 2349 Junquillo Redondo Duo 2 45° H H-156
SYS-03 2349 Junquillo Redondo Duo 4 5° V V-156
SYS-03 2059 Mosquitero 2 45° H H-98
SYS-03 2059 Mosquitero 2 45° V V-98
SYS-03 2219 Pletina 1 90° Según Herraje
SYS-03 2219 Pletina 2 90° Según Herraje
SYS-04 2302 Marco 2 45° H H
SYS-04 2302 Marco 2 45° V V
SYS-04 2334 Hoja Ventana Ap. Ext. 2 45° H H-66
SYS-04 2334 Hoja Ventana Ap. Ext. 2 45° V V-66
SYS-04 2349 Junquillo Redondo Duo 2 45° H H-156
SYS-04 2349 Junquillo Redondo Duo 2 45° V V-156

Variables: H = Ancho total del vano (mm), V = Alto total del vano (mm).

---

1.4 Tabla: herrajes (Hardware por sistema)

sistema clave descripcion cantidad unidad notas
SYS-01 A-4001 Carretilla 4 PZA 
SYS-01 A-4002 Contra y Gancho 2 PZA 
SYS-01 A-4003 Cortavientos 2 PZA 
SYS-01 A-4004 Candado de Hoja 4 PZA 
SYS-01 A-4005 Tapa Traslape 4 PZA 
SYS-01 A-4006 Escuadra de Botón 4000 C 12 PZA 
SYS-01 A-5000 Broche Embutido 2 PZA 
SYS-01 A-5020 Tapa Dren 2 PZA 
SYS-01 A-5021 Tapón Desagüe 2 PZA 
SYS-01 A-5022 Tapón Cubre Pija 6 PZA 
SYS-01 A-5023 Escuadra de Alineación 4000-4500 16 PZA 
SYS-01 A-5028 Felpa Especial 6H+8V ML 
SYS-01 A-5032 Calza para Vidrio 4 PZA 
SYS-01 A-5047 Empaque Cuña 2H+4V ML 
SYS-01 A-5079 Pija Fijadora 10"x2" 6 PZA 
SYS-01 A-5090 Taquete de 1/4 6 PZA 
SYS-01 A-5091 Sellador Perimetral 4H+4V ML 
SYS-02 A-4001 Carretilla 4 PZA 
SYS-02 A-4002 Contra y Gancho 2 PZA 
SYS-02 A-4003 Cortavientos 2 PZA 
SYS-02 A-4004 Candado de Hoja 4 PZA 
SYS-02 A-4005 Tapa Traslape 4 PZA 
SYS-02 A-4006 Escuadra de Botón 4000 C 12 PZA 
SYS-02 A-5000 Broche Embutido 2 PZA 
SYS-02 A-5002 Uñero 2 PZA 
SYS-02 A-5020 Tapa Dren 2 PZA 
SYS-02 A-5021 Tapón Desagüe 2 PZA 
SYS-02 A-5022 Tapón Cubre Pija 8 PZA 
SYS-02 A-5023 Escuadra de Alineación 4000-4500 16 PZA 
SYS-02 A-5028 Felpa Especial 6H+8V ML 
SYS-02 A-5032 Calza para Vidrio 4 PZA 
SYS-02 A-5042 Empaque Cuña 2H+4V ML 
SYS-02 A-5079 Pija Fijadora 10"x2" 8 PZA 
SYS-02 A-5090 Taquete de 1/4 8 PZA 
SYS-02 A-5091 Sellador Perimetral 4H+4V ML 
SYS-03 A-4051 Escuadra de Botón 4000-B 8 PZA 
SYS-03 A-4052 Escuadra de Alineación 8 PZA 
SYS-03 A-4067 Kit Oscilobatiente 1 PZA 
SYS-03 A-4068 Compás OB 1 PZA 
SYS-03 A-4069 Cremona OB 1 PZA 
SYS-03 A-5022 Tapón Cubre Pija 6 PZA 
SYS-03 A-5024 Escuadra p/Mosquitero 4 PZA 
SYS-03 A-5031 Tela Mosquitero HxV PZA 
SYS-03 A-5032 Calza para Vidrio 2 M2 
SYS-03 A-5040 Empaque Cuña 2H+2V ML 
SYS-03 A-5053 Empaque Bi-Extraudo Respaldo 2H+2V ML 
SYS-03 A-5054 Empaque Bi-Extraudo Descentrado 2H+2V ML 
SYS-03 A-5055 Empaque Junta Central 2H+2V ML 
SYS-03 A-5060 Empaque Cola de Rata 2H+2V ML 
SYS-03 A-5079 Pija Fijadora 10"x2" 6 PZA 
SYS-03 A-5090 Taquete de 1/4 6 PZA 
SYS-03 A-5091 Sellador Perimetral 4H+4V ML 
SYS-04 A-2519 Cierre de Presión 1 PZA 
SYS-04 A-4051 Escuadra de Botón 8 PZA 
SYS-04 A-4052 Escuadra de Alineación 8 PZA 
SYS-04 A-4057 Compás de Proyección 2 PZA 
SYS-04 A-5022 Tapón Cubre Pija 6 PZA 
SYS-04 A-5032 Calza para Vidrio 2 PZA 
SYS-04 A-5040 Empaque Cuña 2H+2V ML 
SYS-04 A-5053 Empaque Bi-Extraudo Respaldo 2H+2V ML 
SYS-04 A-5054 Empaque Bi-Extraudo Descentrado 2H+2V ML 
SYS-04 A-5055 Empaque Junta Central 2H+2V ML 
SYS-04 A-5079 Pija Fijadora 10"x2" 6 PZA 
SYS-04 A-5090 Taquete de 1/4 6 PZA 
SYS-04 A-5091 Sellador Perimetral 4H+4V ML 

---

1.5 Tabla: vidrios (Cálculo de cristales)

sistema descripcion cantidad ancho_formula alto_formula
SYS-01 Vidrio 6mm 2 (H-206)/2 V-166
SYS-02 Vidrio Duo 6+1/4+6 2 (H-266)/2 V-205
SYS-03 Vidrio Duo 6+3/8+6 2 H-178 V-178
SYS-04 Vidrio Duo 6+3/8+6 1 H-178 V-178

---

1.6 Tabla: rendimiento_viento (Gráficas de desempeño)

curva presion_diseno_kg_m2 velocidad_viento_km_h zona
A 45 80 Centro de grandes ciudades
B 50 90 Barrios residenciales
C 65 120 Campo abierto
D 110 160 Costera
E 150 200 Zona de huracanes
F 220 230 Zona de huracanes

Aplicable a: Aleación 6063 Temple T5. Los límites de fabricación son los que se encuentran debajo de las curvas.

---

2. 🧠 MOTOR PARAMÉTRICO (Pseudocódigo)

```python
# ============================================
# MOTOR PARAMÉTRICO EUROALUM 4000
# ============================================

class SistemaEuroalum:
    def __init__(self, tipo, H, V):
        self.tipo = tipo          # SYS-01, SYS-02, etc.
        self.H = H                # Ancho total (mm)
        self.V = V                # Alto total (mm)
        self.perfiles = []
        self.herrajes = []
        self.vidrios = []
        self.validar()

    def validar(self):
        """Verifica que H y V estén dentro de los límites de las curvas"""
        limites = {
            'SYS-01': {'A': (H<=1600, V<=2300), 'B': (H<=1600, V<=2250), ...},
            'SYS-02': {'C': (H<=1600, V<=3050), 'D': (H<=1600, V<=2700), ...},
        }
        # Lógica de validación según tabla de viento
        pass

    def calcular_perfiles(self):
        """Genera lista de cortes según fórmulas"""
        formulas = {
            'SYS-01': [
                {'clave': '2314', 'cant': 2, 'corte': '45° H', 'formula': lambda H,V: H},
                {'clave': '2314', 'cant': 2, 'corte': '45° V', 'formula': lambda H,V: V},
                {'clave': '2297', 'cant': 4, 'corte': '45°',   'formula': lambda H,V: (H+2)/2},
                {'clave': '2297', 'cant': 4, 'corte': '45° V', 'formula': lambda H,V: V-62},
                {'clave': '2276', 'cant': 2, 'corte': '90° V', 'formula': lambda H,V: V-65},
            ],
            # ... otros sistemas
        }
        for f in formulas[self.tipo]:
            medida = f['formula'](self.H, self.V)
            self.perfiles.append({
                'clave': f['clave'],
                'cantidad': f['cant'],
                'corte': f['corte'],
                'medida_mm': round(medida, 2)
            })

    def calcular_herrajes(self):
        """Genera lista de herrajes según sistema"""
        # Similar a perfiles, con cantidades fijas o fórmulas H/V
        pass

    def calcular_vidrios(self):
        """Genera lista de vidrios según fórmulas"""
        pass

    def generar_orden_produccion(self):
        """Salida final: lista de materiales + instrucciones de corte"""
        return {
            'sistema': self.tipo,
            'dimensiones': {'H': self.H, 'V': self.V},
            'perfiles': self.perfiles,
            'herrajes': self.herrajes,
            'vidrios': self.vidrios,
            'validacion_viento': self.validar()
        }

# Ejemplo de uso:
# ventana = SistemaEuroalum('SYS-01', H=1200, V=1500)
# orden = ventana.generar_orden_produccion()
```

---

3. 📐 REPRESENTACIÓN VECTORIAL (SVG Paramétrico)

3.1 Sección transversal — Perfil 2314 (Riel Doble)

```svg
<svg viewBox="0 0 300 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Perfil 2314: Riel Doble 2.740" x 1.630" -->
  <rect x="20" y="80" width="260" height="40" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="20" y="40" width="260" height="15" fill="none" stroke="#333" stroke-width="1.5"/>
  <rect x="20" y="140" width="260" height="15" fill="none" stroke="#333" stroke-width="1.5"/>
  <!-- Rieles -->
  <rect x="40" y="30" width="8" height="15" fill="#666"/>
  <rect x="120" y="30" width="8" height="15" fill="#666"/>
  <rect x="200" y="30" width="8" height="15" fill="#666"/>
  <!-- Cotas -->
  <line x1="20" y1="170" x2="280" y2="170" stroke="red" stroke-width="1"/>
  <text x="150" y="185" text-anchor="middle" fill="red" font-size="12">2.740" [69.61]</text>
  <line x1="10" y1="40" x2="10" y2="155" stroke="blue" stroke-width="1"/>
  <text x="5" y="100" text-anchor="middle" fill="blue" font-size="12" transform="rotate(-90 5 100)">1.630" [41.39]</text>
</svg>
```

3.2 Diagrama de sistema — Ventana Corrediza (SYS-01)

```svg
<svg viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg">
  <!-- Marco exterior -->
  <rect x="20" y="20" width="360" height="260" fill="none" stroke="#333" stroke-width="3"/>
  <!-- Riel superior -->
  <rect x="20" y="20" width="360" height="15" fill="#e0e0e0" stroke="#333" stroke-width="1"/>
  <!-- Riel inferior -->
  <rect x="20" y="265" width="360" height="15" fill="#e0e0e0" stroke="#333" stroke-width="1"/>
  <!-- Hoja izquierda -->
  <rect x="40" y="50" width="150" height="200" fill="#cce5ff" stroke="#0066cc" stroke-width="2"/>
  <text x="115" y="155" text-anchor="middle" fill="#0066cc" font-size="12">Hoja 2297</text>
  <!-- Hoja derecha -->
  <rect x="210" y="50" width="150" height="200" fill="#cce5ff" stroke="#0066cc" stroke-width="2"/>
  <text x="285" y="155" text-anchor="middle" fill="#0066cc" font-size="12">Hoja 2297</text>
  <!-- Adaptador traslape -->
  <rect x="190" y="50" width="20" height="200" fill="#ffcc00" stroke="#cc9900" stroke-width="1"/>
  <text x="200" y="155" text-anchor="middle" fill="#cc9900" font-size="8" transform="rotate(-90 200 155)">2276</text>
  <!-- Cotas -->
  <line x1="20" y1="295" x2="380" y2="295" stroke="red" stroke-width="1"/>
  <text x="200" y="310" text-anchor="middle" fill="red" font-size="14">H</text>
  <line x1="5" y1="20" x2="5" y2="280" stroke="blue" stroke-width="1"/>
  <text x="5" y="150" text-anchor="middle" fill="blue" font-size="14" transform="rotate(-90 5 150)">V</text>
  <!-- Flechas de apertura -->
  <line x1="150" y1="150" x2="100" y2="150" stroke="#ff6600" stroke-width="2" marker-end="url(#arrow)"/>
  <line x1="250" y1="150" x2="300" y2="150" stroke="#ff6600" stroke-width="2" marker-end="url(#arrow)"/>
  <defs>
    <marker id="arrow" markerWidth="10" markerHeight="7" refX="10" refY="3.5" orient="auto">
      <polygon points="0 0, 10 3.5, 0 7" fill="#ff6600"/>
    </marker>
  </defs>
</svg>
```

3.3 Iconos vectoriales para base de datos

```svg
<!-- Icono Ventana Corrediza -->
<svg viewBox="0 0 64 64" width="64" height="64">
  <rect x="8" y="8" width="48" height="48" fill="none" stroke="#333" stroke-width="2"/>
  <line x1="32" y1="8" x2="32" y2="56" stroke="#333" stroke-width="1.5"/>
  <rect x="12" y="12" width="18" height="40" fill="#e6f2ff"/>
  <rect x="34" y="12" width="18" height="40" fill="#e6f2ff"/>
  <path d="M28 32 L20 32 M36 32 L44 32" stroke="#ff6600" stroke-width="2"/>
</svg>

<!-- Icono Puerta Corrediza Duo -->
<svg viewBox="0 0 64 64" width="64" height="64">
  <rect x="8" y="8" width="48" height="48" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="12" y="12" width="18" height="40" fill="#ccffcc"/>
  <rect x="34" y="12" width="18" height="40" fill="#ccffcc"/>
  <path d="M30 32 L22 32 M42 32 L34 32" stroke="#ff6600" stroke-width="2"/>
</svg>

<!-- Icono Oscilobatiente -->
<svg viewBox="0 0 64 64" width="64" height="64">
  <rect x="8" y="8" width="48" height="48" fill="none" stroke="#333" stroke-width="2"/>
  <rect x="12" y="12" width="40" height="40" fill="#fff0cc"/>
  <path d="M16 20 L48 48 M48 20 L16 48" stroke="#ff6600" stroke-width="1.5"/>
  <circle cx="32" cy="32" r="3" fill="#ff6600"/>
</svg>
```

---

4. 🔧 USOS Y APLICACIONES

4.1 Cotizador Automático

```javascript
// Entrada: tipo, H, V, cantidad, zona_viento
// Salida: costo estimado + lista de materiales + validación
function cotizar(tipo, H, V, cantidad, zona) {
  const sistema = new SistemaEuroalum(tipo, H, V);
  const orden = sistema.generar_orden_produccion();
  const valido = validarViento(tipo, H, V, zona);
  const costo = calcularCosto(orden, cantidad);
  return { orden, valido, costo };
}
```

4.2 Generador de Órdenes de Corte (CNC)

```json
{
  "orden": "OP-2025-001",
  "sistema": "SYS-01",
  "dimensiones": { "H": 1200, "V": 1500 },
  "perfiles": [
    { "clave": "2314", "cant": 2, "corte": "45° H", "medida": 1200 },
    { "clave": "2314", "cant": 2, "corte": "45° V", "medida": 1500 },
    { "clave": "2297", "cant": 4, "corte": "45°",   "medida": 601 },
    { "clave": "2297", "cant": 4, "corte": "45° V", "medida": 1438 },
    { "clave": "2276", "cant": 2, "corte": "90° V", "medida": 1435 }
  ],
  "vidrios": [
    { "desc": "Vidrio 6mm", "cant": 2, "ancho": 497, "alto": 1334 }
  ]
}
```

4.3 Configurador Visual (Web)

· El usuario ingresa H y V con sliders.
· El sistema dibuja en SVG la ventana a escala.
· Se actualizan automáticamente: perfiles, herrajes, vidrios, validación de viento.

4.4 Integración con ERP / CRM

· Tablas normalizadas → importar a MySQL/PostgreSQL.
· API REST para consultar perfiles, herrajes, fórmulas.
· Generación de PDF con despiece y lista de materiales.

4.5 Manual de Mantenimiento

· Asociar herrajes a perfiles para reemplazo.
· Códigos A-XXXX vinculados a proveedores.
· Historial de compatibilidad (ej: esquinero 1659 compatible con 12009 y 2314).

---

5. 📊 RESUMEN EJECUTIVO

Categoría Cantidad Notas
Perfiles catalogados 28 Códigos 2059–2361, 12009–12016
Sistemas definidos 5 Corrediza, Puerta Duo, Oscilobatiente, Proyectante, Fijo
Fórmulas de corte 30+ Parametrizadas por H y V
Herrajes únicos 35+ Códigos A-XXXX
Curvas de viento 6 A–F, 45–220 kg/m²
Vidrios soportados 3 6mm, Duo 6+1/4+6, Duo 6+3/8+6

---

¿Necesitas que genere el script SQL completo para crear la base de datos, o un archivo JSON con toda la estructura para importar directamente? También puedo desarrollar el motor paramétrico en Python/JavaScript con pruebas unitarias.