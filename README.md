# IR Playbook — OIV Portuario 🇨🇱

Herramienta interactiva de respuesta a incidentes de ciberseguridad para **Operadores de Importancia Vital (OIV)** bajo la **Ley 21.663** (Ley Marco de Ciberseguridad de Chile).

Construida desde experiencia operacional real como Delegado de Ciberseguridad en infraestructura crítica portuaria.

---

## ¿Qué problema resuelve?

Cuando te llaman a las 2am con una alerta de ransomware, tienes **3 horas** para enviar la Alerta Temprana a ANCI. En ese momento no puedes estar buscando la taxonomía oficial en el Diario Oficial, navegando entre documentos dispersos y tratando de recordar a quién llamar primero.

Este playbook reemplaza ese proceso fragmentado con un flujo guiado, un timer regulatorio visible y un generador de reportes prellenado.

---

## Funcionalidades

- **Timer regulatorio en tiempo real** — countdown para las 4 ventanas de la Ley 21.663: Alerta Temprana (3h), Actualización (72h), Informe Final (30 días) y notificación DIRECTEMAR
- **Clasificación automática** — describe lo que ves en lenguaje natural y el sistema sugiere la categoría según la taxonomía oficial ANCI (Resolución Exenta N°7/2025)
- **Selección manual por taxonomía** — las 4 áreas de impacto y 11 efectos observables de la Resolución N°7/2025 en formato de selección múltiple
- **Plan de acción dinámico** — las acciones se adaptan según el tipo de incidente y el activo afectado (incluye ramificaciones específicas para OT/ICS, ransomware, exfiltración y DDoS)
- **Generador de reportes ANCI** — produce los tres templates regulatorios (Alerta Temprana, Actualización 72h, Informe Final) prellenados con la información del incidente
- **Log cronológico con timestamp** — registro automático de cada acción + notas manuales
- **100% offline** — funciona como archivo HTML local, sin servidor, sin instalación, sin conexión a internet requerida

---

## Marco normativo

| Norma | Relevancia |
|---|---|
| Ley 21.663 — Ley Marco de Ciberseguridad | Obligación de reporte para OIV y SE |
| DS N°295/2024 — Reglamento de Reporte | Plazos y contenidos mínimos del reporte |
| Resolución Exenta N°7/2025 (ANCI) | Taxonomía oficial de incidentes |
| Ley 21.719 — Protección de Datos Personales | Notificación si hay datos personales afectados |

---

## Cómo usar

### Opción A — Archivo local (recomendado para uso en incidente)

```bash
# Clona el repositorio
git clone https://github.com/renatocuellarp/ir-playbook-ovi.git

# Abre el archivo directamente en tu navegador
# Windows: doble clic sobre playbook-ir.html
# macOS/Linux:
open playbook-ir.html
```

### Opción B — GitHub Pages

Accede desde cualquier dispositivo (incluyendo móvil) en:
`https://renatocuellarp.github.io/ir-playbook-ovi/`

> **Nota sobre portapapeles:** La función "Copiar al portapapeles" requiere HTTPS o localhost. Funciona en GitHub Pages y al servir localmente. Desde archivo local, usa Firefox o descarga el reporte como .txt.

---

## Personalización para tu organización

Antes de usar en producción, personaliza estas secciones en `playbook-ir.html`:

```
// PERSONALIZAR: Activos de tu inventario
// Busca: "asset-card" — reemplaza con tus activos reales y niveles de criticidad

// PERSONALIZAR: Contactos de escalamiento  
// Busca: "contact-item" — reemplaza con nombres, teléfonos y emails reales

// PERSONALIZAR: Identificación institucional
// Busca: "rInstitution" — puedes precargar el nombre de tu organización
```

Los placeholders están comentados en el código para facilitar la adaptación.

---

## Estructura del repositorio

```
ir-playbook-ovi/
├── README.md
├── playbook-ir.html        ← herramienta principal (autocontenida)
├── LICENSE
└── CHANGELOG.md
```

---

## Roadmap

- [ ] Integración con inventario de activos externo (JSON configurable)
- [ ] Módulo de tabletop exercises con escenarios predefinidos
- [ ] Exportación de reporte en formato PDF
- [ ] Integración con TIP (Threat Intelligence Platform) para correlación automática
- [ ] Template de notificación DIRECTEMAR para incidentes OT marítimos

---

## Contexto y motivaciones

Este proyecto forma parte de un ecosistema más amplio de herramientas de ciberseguridad para infraestructura crítica chilena, desarrollado desde experiencia práctica como Delegado de Ciberseguridad en un operador portuario clasificado como OIV bajo Ley 21.663.

El enfoque es construir herramientas que resuelvan problemas operacionales reales, no demos conceptuales. La taxonomía ANCI, los plazos regulatorios y los flujos de escalamiento están verificados contra la normativa vigente a la fecha de publicación.

---

## Licencia

MIT License — libre uso, adaptación y distribución con atribución.

Si lo adaptas para tu organización o lo mejoras, considera hacer un PR o dejar una estrella. El objetivo es que más delegados de ciberseguridad en Chile tengan acceso a herramientas prácticas alineadas a la regulación local.

---

## Contacto

[LinkedIn](https://www.linkedin.com/in/renato-cuellar-pavez/) · [GitHub](https://github.com/renatocuellarp)

*Última actualización normativa verificada: Resolución Exenta ANCI N°7/2025 (marzo 2025)*
