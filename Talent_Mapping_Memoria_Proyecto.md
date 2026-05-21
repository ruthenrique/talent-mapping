# Talent Mapping · Memoria del Proyecto
**Versión activa:** `Talent_Match_v18.html`  
**Última actualización:** Mayo 2026  
**Documento preparado para:** equipo de Capital Humano BSG

---

## ¿Qué es esto?

Dashboard de **Talent Mapping** para el proceso interno de evaluación y seguimiento de talento de BSG. Es un archivo HTML único que funciona localmente en el navegador, sin necesidad de servidor ni conexión a internet.

> **Claim:** *Personas que viven la marca antes de venderla.*

---

## Cómo abrir el dashboard

1. Descargar el archivo `Talent_Match_v18.html`
2. Hacer doble clic para abrirlo en cualquier navegador (Chrome, Edge, Firefox)
3. Ingresar con usuario y contraseña

No requiere instalación ni conexión a internet.

---

## Accesos y usuarios

### Tabla de usuarios activos

| Nombre | Usuario | Contraseña | Perfil | Alcance |
|--------|---------|------------|--------|---------|
| Giannina Zambaglione | `gzambaglione` | `gz123` | Super Administrador | Total |
| Ruth Enrique | `renrique` | `re123` | Super Administrador | Total |
| Mario Falguieres | `mfalguieres` | `mf123` | Super Administrador | Total |
| Damián Carnero | `dcarnero` | `dc123` | Visualización Global | Total (sin edición) |
| Cecilia Alessandro | `calessandro` | `ca123` | Referente País | Solo Argentina |
| Capital Humano AR | `ch_ar` | `ch123` | Administrador AR | Solo Argentina |
| Fiamma Zangaro | `fzangaro` | `fz123` | HRBP | Sus colaboradores |
| Lucila Picon | `lpicon` | `lp123` | HRBP | Sus colaboradores |
| Micaela Panebianco | `mpanebianco` | `mp123` | HRBP | Sus colaboradores |

### Permisos por perfil

| Acción | Super Admin | Administrador | Ref. País | HRBP | Vis. Global |
|--------|-------------|---------------|-----------|------|-------------|
| Ver todos los datos | ✅ | ❌ (solo AR) | ❌ (solo AR) | ❌ (solo propios) | ✅ |
| Calibrar | ✅ | ✅ | ✅ | ✅ | ❌ |
| Exportar todos los datos (CSV) | ✅ | ❌ | ❌ | ❌ | ❌ |
| Exportar Plan de Acción | ✅ | ✅ | ❌ | ❌ | ❌ |
| Ver Configuración | ✅ | ❌ | ❌ | ❌ | ❌ |
| Ver Data Maestro | ✅ | ❌ | ❌ | ❌ | ❌ |
| Ver Talent Mapping (tab) | ✅ | ❌ | ❌ | ❌ | ❌ |
| Subir Excel | ✅ | ✅ | ❌ | ❌ | ❌ |

---

## Orden de pestañas

```
Dashboard → Nuevos Ingresos → Talent Review → Calibración → Plan de Acción → Talent Mapping → Data Maestro → Configuración
```

---

## Descripción de cada pestaña

### 1. Dashboard
Vista ejecutiva con KPIs y gráficos generales.

**KPIs:**
- Total Evaluados · Promotores · Neutros · Detractores
- Score Promedio
- Salud Cultural (NPS) = % Promotores − % Detractores
- % Recontratación (personas con reselección = "Sí")
- Con Potencial

**Filtros disponibles** (jerárquicos, como tags seleccionables):  
Unidad de Negocio → Año → Marca → Región → Distrito → Tienda → Localización → Provincia → Posición

**Gráficos:**
- Distribución Talent Mapping (donut)
- Recontratación con % en centro (donut)
- Por Marca (barras apiladas Promotor/Neutro/Detractor)
- Score por Dimensión (radar)
- Distribución por Distrito (barras apiladas)
- Tabla: Tiendas con más Detractores

---

### 2. Nuevos Ingresos
Personas con **menos de 1 año de antigüedad**.

- KPIs específicos de nuevos ingresos
- % con Potencial
- Índice de Recontratación de nuevos
- Filtros completos (misma jerarquía que Dashboard)
- Gráficos: Distribución TM · Por Rol · Por Tienda (agrupado por nombre sin códigos)
- Tabla detalle ordenable y con buscador

---

### 3. Talent Review
Solo personas con **Potencial = "Sí"**.

- Filtros: Unidad · Año · Marca · Región · Distrito · Tienda · Localización · Provincia · Posición
- KPIs: Total con Potencial · Promotores · Score Promedio
- Gráficos: Distribución Talent Mapping · Por Rol
- Tabla ordenable con buscador

---

### 4. Calibración
Validación y ajuste de la clasificación Talent Mapping de cada persona.

**¿Quién puede calibrar?** Super Admin, Administrador, Referente País y HRBP.

**Funcionalidades:**
- **Filtros** jerárquicos completos + filtro de estado (Todos / Pendiente / Calibrado)
- **Barra de progreso** visual: % calibrado · % pendiente · cantidad restante
- **Orden predeterminado** de tabla: Promotores → Neutros → Detractores
- Tabla ordenable por cualquier columna, con buscador
- Columna "Editado por" muestra quién hizo el último cambio y cuándo

**Modal de calibración por persona:**
- Datos originales del VCD (solo lectura)
- Selector de clasificación: **Promotor / Neutro / Detractor** (con indicador visual del cambio)
- Estado: **Pendiente / Calibrado**
- Campo de comentario por cada guardado
- **Historial completo** de cambios (fecha, hora, usuario, clasificación anterior → nueva)

---

### 5. Plan de Acción
Plan de acción focalizado por distrito. Accesible para todos los roles.

**Navegación:**
- Filtro por Región (tags)
- Selector de Distrito (tags) — el primer distrito se selecciona automáticamente al entrar
- Buscador de personas dentro del distrito

**Por cada distrito muestra:**
- KPIs: Total · % Detractores · % Neutrales · % Promotores · NPS · Con Potencial
- **Acciones registradas** (ordenadas: Detractores → Neutros → Promotores) con:
  - Badge de tipo (Detractor / Neutro / Promotor)
  - Fecha, autor y fecha de creación
  - Botón eliminar
- **Formulario inline**: acción + tipo + fecha de seguimiento (todos obligatorios)
- **Personas del distrito** agrupadas: Detractores → Neutros → Promotores
  - Cada persona tiene campo de **Observaciones** con:
    - Historial de entradas (fecha, hora, nombre del usuario)
    - Solo muestra la última por defecto
    - `<details>` expandible para ver el historial completo

**Exportar Plan de Acción (CSV):** disponible para Super Admin y Administrador.

---

### 6. Talent Mapping *(solo admins)*
Mapa de talento con detalle por dimensión.

- Filtros: Marca · Distrito · Tienda
- KPIs: Total Mapeados · Score Promedio · Con Potencial
- Gráfico: Score por Dimensión (barras) · Distribución Talent Mapping (donut)
- Tabla completa con las 6 dimensiones + Score + Clasificación
- Tabla ordenable con buscador

---

### 7. Data Maestro *(solo admins)*
Nómina completa de todos los evaluados.

- Filtro por texto (nombre o ID SF) y por tipo (Nómina / Nuevo Ingreso)
- Tabla con: Nombre · ID SF · Rol · Tienda · Distrito · Antigüedad · Score · Clasif. TM · Reselección · Potencial
- Tabla ordenable con buscador

---

### 8. Configuración *(solo Super Administrador)*

- **Subir Excel** para actualizar la base de datos completa
- **Pesos de dimensiones** editables (porcentajes que suman 100%)
- **Umbrales de clasificación** editables (Promotor / Neutro)
- **Exportar todos los datos** a CSV (incluye scores, clasificaciones, estado de calibración)

---

## Lógica de cálculo

### Score Talent Mapping
```
Score = promedio PONDERADO de 6 dimensiones
Dimensiones: Talent Match · Imagen · Gestión · Soft Skills · Customer · Cultura
Pesos por defecto: 16.67% cada una (configurable en Configuración)
```

### Clasificación
| Clasificación | Condición |
|---------------|-----------|
| **Promotor** | Score ≥ 4.0 |
| **Neutro** | Score ≥ 3.0 |
| **Detractor** | Score < 3.0 |

> Los umbrales son configurables desde la pestaña Configuración (solo Super Admin).

### Indicadores clave
| Indicador | Fórmula |
|-----------|---------|
| % Recontratación | Personas con reselección = "Sí" / Total × 100 |
| Salud Cultural (NPS) | % Promotores − % Detractores |
| Nuevos Ingresos | Personas con antigüedad < 1 año |

### Clasificación efectiva (calibrada)
Si una persona fue calibrada por HRBP o Admin, el dashboard usa la **clasificación calibrada** en todos los KPIs y gráficos. Los datos originales del VCD se conservan siempre.

---

## Datos actuales cargados

**40 personas evaluadas · Argentina · Region 3**

| Dato | Valores disponibles |
|------|---------------------|
| Marca | TM · IS |
| Distritos | Distrito 11 · Distrito 18 |
| Región | Region 3 |
| Provincias | Buenos Aires · CABA · Chubut · Tierra del Fuego |
| Localizaciones | GBA · CABA · Interior |
| Roles | Store Experience Manager · Instore VM · Sales Experience Assistant |

**Tiendas TM (Distrito 11):**
TM-CABILDO · TM-CABILDO 2 · TM-CABILDO 3 · TM-DOT 2 · TM-MARTINEZ · TM-OLIVOS · TM-SAN ISIDRO 2 · TM-UNICENTER · TM-UNICENTER 2

**Tiendas IS (Distrito 18):**
IS-BAHIA BLANCA 1 · IS-BAHIA BLANCA 2 · IS-COMODORO RIVADAVIA · IS-MAR DEL PLATA 3 · IS-MAR DEL PLATA 4 · IS-TANDIL · IS-TRELEW · IS-USHUAIA

---

## Actualizar datos desde Excel

1. Ingresar como Super Admin o Administrador
2. Ir a **Configuración**
3. En la sección "Actualizar información desde Excel", hacer clic o arrastrar el archivo `.xlsx`
4. El sistema reemplaza los datos y recalcula automáticamente

**Columnas requeridas en el Excel:**
`Usuario · ID respuesta · Nombre VCD · ID Success Factor · Nombre · Fecha de contratación · Unidad de Negocio · Marca · Región · Distrito · Tienda · HRBP · Localización · Provincia · Título puesto actual · FIT ADN · IMAGEN DE MARCA · GESTION DEL NEGOCIO · SOFT SKILL / LIDERAZGO · CUSTOMER EXPERIENCE · ENGAGEMENT Y CULTURA · POTENCIAL Y DESARROLLO · ¿La volverías a seleccionar?`

> El sistema tolera variaciones menores en los nombres de columnas.

---

## Filtros — funcionamiento

- Se muestran como **tags seleccionables** (sin dropdowns)
- Son **jerárquicos**: al seleccionar Unidad, solo aparecen las Marcas de esa unidad; al seleccionar Marca, solo los Distritos de esa marca, y así sucesivamente
- Al cambiar un filtro padre, los filtros hijos se limpian automáticamente
- El filtro **Año** aparece en segundo lugar (junto a Unidad de Negocio) y refleja el año de la sesión actual

---

## Persistencia de datos

La información se guarda **en memoria durante la sesión**. Al cerrar o recargar el navegador se pierde:
- Las calibraciones realizadas
- Los planes de acción ingresados
- Las observaciones registradas

> Para persistencia real entre sesiones se requeriría un backend o base de datos. Esto es una limitación conocida de la versión actual (archivo HTML independiente).

---

## Historial de versiones

| Versión | Cambios clave |
|---------|---------------|
| v8–v9 | Primera versión con datos reales, UI clean, filtros como tags |
| v10 | Usuarios nombrados, roles personalizados |
| v11 | Filtros jerárquicos, calibración simplificada, Plan de Acción operativo |
| v12 | Filtros compactos, historial de calibración, tooltips con %, export CSV |
| v13 | Filtros en Nuevos Ingresos, buscadores en tablas, orden por columnas, exportación Plan |
| v14 | Auto-selección de distrito en Plan de Acción |
| v15 | Fix duplicación TM-UNICENTER, observaciones con historial, nomenclaturas, filtro año |
| v16 | Nomenclaturas finales (Talent Mapping / Talent Match), filtro año desde 2026, observaciones con historial visual |
| v17 | Datos actualizados desde Excel con tiendas unificadas (sin códigos) |
| v18 | Permisos exportación ajustados, barra de progreso calibración, filtro estado calibración, reordenamiento pestañas |

---

## Pendientes conocidos

- **Persistencia real**: los datos de calibración, planes y observaciones se pierden al recargar. Se necesita backend para persistencia entre sesiones.
- **Fiamma Zangaro**: usuario HRBP creado pero sin colaboradores asignados en el Excel actual (su `hrbp` no aparece en los datos). Verá el tablero vacío hasta que se actualice el Excel.
- **Multi-país**: actualmente solo cargados datos de Argentina. La arquitectura de roles ya está preparada para más países.
- **Exportación con observaciones**: el CSV exportado desde Configuración no incluye las observaciones del Plan de Acción por persona.
