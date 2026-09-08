# Informe de contenidos, estructura y tecnología

## Landing page de Vínculos Chiloé

**Fecha de elaboración:** 8 de septiembre de 2026  
**Repositorio:** [lfavreau/vinculos-web](https://github.com/lfavreau/vinculos-web)  
**Sitio de referencia:** [vinculoschiloe.cl](https://vinculoschiloe.cl/)  
**Alcance de implementación actual:** página de inicio o *landing page*. Las páginas internas del menú se documentan como contexto, pero no forman parte de esta etapa.

---

## 1. Resumen ejecutivo

Vínculos Chiloé es una organización territorial sin fines de lucro cuyo relato público une educación, comunidad, cultura local, derechos y acompañamiento terapéutico. Trabaja con niños, niñas, adolescentes, personas adultas, familias y comunidades de la provincia de Chiloé. Su propuesta educativa se apoya especialmente en el Aprendizaje Basado en Proyectos (ABP), la investigación del territorio y la construcción colectiva del conocimiento. La organización también desarrolla una línea diferenciada de tratamiento y rehabilitación para personas adultas. Estas definiciones se encuentran en la [portada institucional](https://vinculoschiloe.cl/), la página de [Comunidades de Aprendizaje Castro](https://vinculoschiloe.cl/comunidades-de-aprendizaje-castro/), la página de [Comunidad Terapéutica](https://vinculoschiloe.cl/comunidad-terapeutica/) y la [Memoria Anual 2023 de ONG Vínculos](https://vinculoschiloe.cl/wp-content/uploads/2024/11/MEMORIA-ANUAL-2023-ONG-VINCULOS.pdf).

La nueva página debe funcionar como una portada clara y contemporánea, no como una réplica completa del WordPress anterior. Su trabajo principal es responder rápidamente cinco preguntas:

1. ¿Qué es Vínculos Chiloé?
2. ¿Qué hace la Escuela Vínculos?
3. ¿Cómo se vive su propuesta educativa?
4. ¿Qué es la Comunidad Terapéutica y cómo se diferencia de la escuela?
5. ¿Cómo contactar, postular o visitar cada espacio?

La landing actual ya contiene la estructura base para responderlas. El mayor pendiente funcional es reemplazar la galería estática por un **feed real de Instagram**, presentado editorialmente como **“La comunidad en movimiento”**.

---

## 2. Alcance y criterio de este informe

Este documento combina cuatro tipos de evidencia:

- El sitio público actual de Vínculos Chiloé y sus documentos enlazados.
- Noticias externas con autor o institución responsable y fecha identificable.
- El inventario técnico adjunto `migration-blueprint.zip`.
- El código de la reconstrucción en Astro alojado en este repositorio.

El archivo adjunto se utilizó únicamente como **inventario técnico**. Su propio contenido indica que es una captura de tipo `schema-only`, sin valores editoriales ni datos personales; por esa razón no basta para reconstruir textos, fotografías ni noticias. Los contenidos se verificaron en fuentes públicas separadas.

En el resto del informe se usa la siguiente distinción:

- **Hecho verificado:** contenido respaldado por una fuente pública o por el código del proyecto.
- **Decisión actual:** algo que ya existe en la landing del repositorio.
- **Recomendación:** propuesta para una siguiente iteración, todavía no implementada.

---

## 3. De qué trata la web

### 3.1 Identidad institucional

El concepto central es **“Educación · Comunidad · Territorio”**. La portada pública define a Vínculos como una institución sin fines de lucro que trabaja en educación en la provincia y el archipiélago de Chiloé, tanto en sectores urbanos como rurales. La [Memoria Anual 2023](https://vinculoschiloe.cl/wp-content/uploads/2024/11/MEMORIA-ANUAL-2023-ONG-VINCULOS.pdf) amplía este marco a educación, salud, capacitación, medio ambiente, desarrollo comunitario, derechos humanos y actividades deportivo-recreativas.

La web no debiera presentarse como una escuela convencional ni como un sitio clínico aislado. Debe mostrar una organización con dos líneas relacionadas por una misma mirada comunitaria:

- **Línea educativa:** Escuela y Comunidades de Aprendizaje, ABP, cultura chilota, oficios, artes, territorio e inclusión.
- **Línea terapéutica:** tratamiento y rehabilitación para personas adultas, con atención residencial y ambulatoria, redes territoriales y enfoque socioeducativo.

### 3.2 Audiencias principales

- Familias y apoderados que evalúan matricular a sus hijos e hijas.
- Estudiantes y comunidad escolar.
- Personas adultas y familias que buscan orientación sobre tratamiento.
- Instituciones públicas, organizaciones comunitarias y redes colaboradoras.
- Personas interesadas en el trabajo educativo, cultural y territorial de Chiloé.
- Medios, donantes o posibles aliados que necesitan conocer trayectoria, resultados y transparencia.

### 3.3 Mensaje editorial recomendado

La portada debe comunicar que **el territorio no es un decorado, sino parte de la metodología educativa y comunitaria**. La cobertura de [El Insular del 17 de mayo de 2024](https://elinsular.cl/2024/05/17/comunidad-de-aprendizaje-vinculos-educacion-con-pertinencia-local/) describe el ABP como hilo conductor de las asignaturas y menciona proyectos sobre mar, bosque nativo, historia local, crisis hídrica y tradiciones chilotas. Esto respalda una narrativa visual basada en experiencias reales, investigación, salidas a terreno y comunidad.

---

## 4. Arquitectura general de la web

El WordPress de referencia expone cuatro entradas principales: **Inicio, Cursos, Comunidad y Noticias**. Para esta etapa solo se implementa **Inicio**.

| Área | Propósito | Estado actual |
| --- | --- | --- |
| Inicio | Presentación institucional, llamados prioritarios, vida comunitaria, metodología, ubicaciones y contacto | Implementada como landing |
| Cursos | Oferta o experiencias educativas, niveles, talleres y proyectos | Fuera de alcance; trabajar después |
| Comunidad | Profundización institucional, comunidad educativa y Comunidad Terapéutica | Fuera de alcance; la landing solo incluye un resumen y un llamado |
| Noticias | Archivo editorial con artículos, fechas, autores, categorías y documentos | Fuera de alcance; la landing podría mostrar tres destacados en el futuro |

Esta separación evita que la portada vuelva a acumular todos los contenidos históricos en una sola página. La landing debe resumir y derivar; las páginas internas deberán profundizar cuando se diseñen.

---

## 5. Secciones de la landing page

### 5.1 Encabezado de marca

**Propósito:** reconocimiento inmediato de Vínculos Chiloé.

**Contenido actual:** logotipo institucional centrado sobre fondo blanco.

**Recomendación:** mantenerlo simple en esta fase. Cuando se trabaje el menú, el encabezado deberá incorporar navegación accesible, indicador de página activa y una acción prioritaria —por ejemplo, “Matrícula” o “Contacto”— sin quitar protagonismo al logotipo.

### 5.2 Hero o portada principal

**Propósito:** explicar la institución en una sola pantalla.

**Contenido actual:** fotografía territorial, marca, lema “Educación · Comunidad · Territorio”, definición institucional y tres frases sobre públicos y metodología.

**Fuente:** [página principal de Vínculos Chiloé](https://vinculoschiloe.cl/).

**Recomendación editorial:** conservar un título breve y una bajada de máximo tres líneas. La explicación más larga puede pasar a “Quiénes somos”. La imagen debe tener permiso de uso, versión optimizada y un punto focal definido para móvil.

### 5.3 Avisos prioritarios

**Propósito:** hacer visibles acciones de alta urgencia o valor público.

**Contenido actual:**

- **Matrícula 2026**, enlazada al formulario publicado por la organización.
- **Cuenta pública**, enlazada al repositorio documental del sitio original.

**Recomendación funcional:** estos avisos deben administrarse como datos, no quedar escritos permanentemente en el componente. Cada aviso necesita título, descripción, URL, vigencia, tipo de enlace y estado activo. Cuando venza “Matrícula 2026”, debe poder ocultarse sin modificar la maqueta.

### 5.4 “La comunidad en movimiento”: feed de Instagram

Esta sección **no debe considerarse una galería fotográfica convencional**. Debe ser un **feed de Instagram** que muestre actividad reciente de la comunidad educativa y que funcione como prueba viva del proyecto.

**Nombre editorial recomendado:** **La comunidad en movimiento**  
**Título complementario:** “Momentos que construyen aprendizaje”  
**Cuenta principal para el feed escolar:** [@escuela.vinculos.chiloe](https://www.instagram.com/escuela.vinculos.chiloe/)

La relación entre la escuela y esa cuenta también aparece en la noticia de [El Insular](https://elinsular.cl/2024/05/17/comunidad-de-aprendizaje-vinculos-educacion-con-pertinencia-local/), que deriva a ese perfil para conocer el trabajo educativo.

#### Comportamiento esperado

- Mostrar las 6 publicaciones más recientes en una grilla de 3 columnas en escritorio, 2 en tablet y 1 o 2 en móvil según el ancho disponible.
- Cada tarjeta debe abrir la publicación original, no solo el perfil general.
- Usar la imagen, texto alternativo o resumen, fecha y enlace proporcionados por una integración autorizada.
- Incluir el botón “Seguir en Instagram”.
- Mantener una última versión válida en caché si Instagram no responde.
- Mostrar un estado alternativo sobrio si el feed está temporalmente indisponible.
- Evitar *scraping* frágil de HTML y no exponer credenciales o tokens en el navegador.
- Revisar consentimiento y resguardo de imagen de niños, niñas y adolescentes antes de reutilizar publicaciones.

#### Estado técnico actual

La landing muestra seis miniaturas procedentes del caché público del antiguo plugin de Instagram. Son una **maqueta visual**, no un feed vivo: todas enlazan al perfil y no se actualizan desde la API.

El inventario adjunto confirma que el WordPress anterior usaba **Smash Balloon Instagram Feed 6.10.0**. En Astro no corresponde copiar ese plugin: se necesita una integración autorizada para el nuevo entorno.

#### Implementación recomendada

1. Autorizar una fuente oficial de datos para la cuenta de Instagram.
2. Obtener las publicaciones durante la compilación y guardar un caché controlado.
3. Regenerar la web cuando cambie el contenido o según una frecuencia definida.
4. Guardar cualquier credencial solo en variables de entorno del proceso de compilación.
5. Incorporar un respaldo editorial local con seis publicaciones seleccionadas.

Con despliegue manual, el contenido se actualizará cada vez que se ejecute una nueva compilación. Si se necesita actualización automática, el futuro proveedor deberá permitir compilaciones programadas o un pequeño servicio de servidor. Esa decisión puede tomarse cuando se elija el hosting.

### 5.5 Comunidad Terapéutica de Adultos

**Propósito:** visibilizar la segunda línea de trabajo de la organización sin confundirla con la escuela.

**Contenido actual:** bloque fotográfico, explicación breve y llamada a conocer la comunidad.

**Fuentes:** [descripción institucional de la Comunidad Terapéutica](https://vinculoschiloe.cl/comunidad-terapeutica/), [directorio y documentos públicos](https://vinculoschiloe.cl/comunidad-terapeutica-2/) y [Memoria Anual 2023](https://vinculoschiloe.cl/wp-content/uploads/2024/11/MEMORIA-ANUAL-2023-ONG-VINCULOS.pdf).

La memoria informa que durante 2023 los programas atendieron a 24 personas en modalidad residencial y 61 en modalidad ambulatoria intensiva, provenientes de 8 de las 10 comunas de la provincia. Estas cifras pueden utilizarse en una sección de impacto únicamente con la etiqueta **“Resultados 2023”**; no deben mostrarse como cobertura vigente sin una memoria más reciente.

Como actualización externa, [SENDA informó el 14 de agosto de 2025](https://www.senda.gob.cl/noticia/senda-los-lagos-y-la-comunidad-terapeutica-vinculos-inauguran-primer-centro-de-tratamiento-para-mujeres-con-enfoque-de-genero-en-chiloe/) la apertura en Castro de un centro ambulatorio y residencial para mujeres con enfoque de género, con posibilidad de ingreso junto a hijos e hijas menores de cinco años. Por tratarse de un servicio sensible, los textos y datos de contacto deben validarse con la organización antes de publicarlos como información vigente.

### 5.6 Ubicaciones

**Propósito:** distinguir físicamente los dos espacios y facilitar la visita.

**Contenido actual:**

- Escuela Primaria Vínculos: Av. Galvarino Riveros 2458, Castro, Chiloé.
- Comunidad Terapéutica Adultos: Ubaldo Mancilla 115, Castro, Chiloé.

**Fuentes:** [portada institucional](https://vinculoschiloe.cl/) y [Memoria Anual 2023](https://vinculoschiloe.cl/wp-content/uploads/2024/11/MEMORIA-ANUAL-2023-ONG-VINCULOS.pdf). La cobertura de [El Insular](https://elinsular.cl/2024/05/17/comunidad-de-aprendizaje-vinculos-educacion-con-pertinencia-local/) también identifica la ubicación de la escuela.

**Recomendación:** mantener enlaces de texto a Google Maps en vez de cargar mapas embebidos pesados. Antes del lanzamiento debe verificarse la ortografía de “Mancilla/Mansilla”, porque las fuentes públicas no son consistentes.

### 5.7 Quiénes somos

**Propósito:** resumir identidad, alcance territorial y forma de contacto.

**Contenido actual:** definición institucional y teléfono `+56 9 5400 4960`.

**Fuente:** [portada institucional](https://vinculoschiloe.cl/).

**Recomendación:** agregar en una futura iteración un enlace “Conocer nuestra historia” y separar claramente el contacto escolar del terapéutico. No publicar correos o teléfonos adicionales hasta que la organización confirme responsable, horario y vigencia.

### 5.8 Metodología educativa

**Propósito:** convertir el ABP en un rasgo comprensible y diferenciador.

**Contenido actual:** explicación introductoria y secuencia “Preguntar · Investigar · Crear”.

**Fuentes:** [portada institucional](https://vinculoschiloe.cl/), [Comunidades de Aprendizaje Castro](https://vinculoschiloe.cl/comunidades-de-aprendizaje-castro/) y [reportaje de El Insular](https://elinsular.cl/2024/05/17/comunidad-de-aprendizaje-vinculos-educacion-con-pertinencia-local/).

La web anterior documenta proyectos sobre el bosque nativo y el mar de Chiloé. La [Cuenta Pública 2020](https://vinculoschiloe.cl/wp-content/uploads/2021/04/CUENTA_PUBLICA_2020_ESCUELA_VINCULOS_CHILOE.pdf) registra “Lo que nos cuenta el bosque de Chiloé” como proyecto articulador. El artículo institucional [“Navega Chilwé”](https://vinculoschiloe.cl/2019/aprendizaje/navega-chilwe-estudiantes-de-la-escuela-vinculos-chiloe-navegan-en-los-mares-del-archipielago/) muestra una experiencia de navegación, cultura del mar y aprendizaje territorial.

**Recomendación:** reemplazar las descripciones genéricas por uno o dos casos reales con año, pregunta de investigación, actividad territorial y resultado concreto. Así el ABP se demuestra en vez de solo definirse.

### 5.9 Noticias destacadas

Esta sección todavía no está en la landing reconstruida, pero es recomendable incorporarla después del feed o antes del pie de página.

**Función:** mostrar un máximo de tres contenidos recientes o especialmente representativos. Debe ser distinta del feed de Instagram:

- Instagram muestra actualidad cotidiana y visual.
- Noticias explica procesos, resultados, testimonios y documentos con mayor profundidad.

El archivo público contiene artículos relevantes, pero gran parte de la portada corresponde a 2018–2020. Entre ellos aparecen [“Navega Chilwé”](https://vinculoschiloe.cl/2019/aprendizaje/navega-chilwe-estudiantes-de-la-escuela-vinculos-chiloe-navegan-en-los-mares-del-archipielago/), “Lanzamiento de la Revista con los Pies en el Barrio”, “Isla Lemuy contada por sus habitantes” y “Vinculando historias con oficios”, reunidos en la página de [Comunidades de Aprendizaje](https://vinculoschiloe.cl/comunidades-de-aprendizaje/).

Para una portada actual no conviene ordenar automáticamente ese archivo como si fuera reciente. Primero debe hacerse una curaduría y luego publicar nuevas notas. Cada noticia necesita:

- Título y bajada.
- Fecha de publicación y, si corresponde, fecha de actualización.
- Autor o institución responsable.
- Imagen con crédito y texto alternativo.
- Categoría: Educación, Territorio, Comunidad, Terapia, Transparencia u otra taxonomía acordada.
- Fuente primaria y enlaces a documentos relacionados.
- Estado: borrador, publicada o archivada.

### 5.10 Pie de página

**Propósito:** cierre institucional, redes y accesos persistentes.

**Contenido actual:** marca, lema y enlaces a Facebook, Instagram y YouTube.

**Observación:** el feed escolar usa `@escuela.vinculos.chiloe`, mientras el pie actual enlaza a `@vinculos.chiloe`. Es posible que una cuenta represente a la escuela y la otra a la organización general; la relación debe confirmarse antes del lanzamiento y rotularse con claridad.

**Recomendación futura:** añadir datos legales mínimos, política de privacidad, accesibilidad, contacto, documentos públicos y año de copyright. No se debe agregar un enlace a un servicio de despliegue ni una marca de plataforma.

---

## 6. Propuesta editorial de contenidos

### 6.1 Jerarquía recomendada para Inicio

1. Marca y hero.
2. Avisos vigentes: matrícula, cuenta pública u otra prioridad.
3. “La comunidad en movimiento”: feed de Instagram.
4. Propuesta educativa y ABP.
5. Caso o proyecto territorial destacado.
6. Comunidad Terapéutica de Adultos.
7. Resultados o impacto, siempre fechados.
8. Tres noticias destacadas.
9. Ubicaciones y contacto.
10. Pie de página.

### 6.2 Tono de voz

- Cercano, territorial y humano.
- Claro y directo; evitar lenguaje excesivamente técnico o burocrático.
- Respetuoso de la diversidad de edades, géneros y trayectorias.
- Basado en experiencias verificables y voces de la comunidad.
- Cuidadoso al tratar consumo problemático, vulnerabilidad, infancia y salud.

### 6.3 Criterios para noticias y cifras

- Toda cifra debe indicar año, documento y alcance.
- Las noticias institucionales deben diferenciarse de cobertura periodística externa.
- No convertir publicaciones de redes sociales en noticias sin contexto, autoría y fecha.
- Corregir errores tipográficos heredados antes de migrar contenido.
- No mantener formularios de matrícula de años anteriores como enlaces principales.
- Revisar al menos una vez al trimestre teléfonos, ubicaciones, directorio y documentos descargables.

---

## 7. Tecnología del sitio anterior

Según el inventario adjunto `migration-blueprint.zip`, la instalación de referencia corresponde a:

| Elemento | Inventario detectado |
| --- | --- |
| CMS | WordPress 7.1 |
| Tema | Twenty Twenty-One 1.9, tema clásico |
| Constructor/bloques | Spectra 2.19.28 |
| Feed social | Smash Balloon Instagram Feed 6.10.0 |
| Caché | `advanced-cache.php` detectado como *drop-in* |
| Otros | Plugin de acceso del hosting, herramienta de migración y Health Check |

El sitio público confirma además que funciona con WordPress en el pie de algunas páginas. El inventario detecta archivos CSS y JavaScript del tema, Spectra, el feed de Instagram y componentes como carruseles. Esto explica parte de la complejidad y el peso acumulado de la portada anterior.

**Limitación del inventario:** fue generado en modo `schema-only`, con una sola página frontal inspeccionada y límites de tiempo y cobertura. Sirve para reconocer tecnologías y estructuras, pero no demuestra que cada plugin sea necesario ni contiene todo el contenido editorial.

---

## 8. Tecnología de la reconstrucción actual

### 8.1 Stack

| Capa | Implementación actual |
| --- | --- |
| Generador | Astro `^7.3.2` |
| Runtime de desarrollo | Node.js `>=22.12.0` |
| UI | HTML semántico dentro de componentes `.astro` |
| Estilos | CSS nativo global |
| JavaScript del cliente | Ninguno agregado para la landing |
| Framework adicional | Ninguno: no React, Vue, Svelte ni Tailwind |
| Salida | Sitio estático generado en `dist/` |
| Repositorio | GitHub, cuenta `lfavreau` |
| Despliegue | No configurado; se elegirá y ejecutará manualmente más adelante |

Astro permite generar HTML estático y organizar las rutas por archivos. Su documentación también permite manejar contenidos estructurados mediante colecciones locales o remotas, con validación y tipado; esto encaja con una futura sección de noticias sin obligar a incorporar un CMS desde ahora. Véanse la documentación oficial de [estructura de proyecto](https://docs.astro.build/en/basics/project-structure/), [rutas](https://docs.astro.build/en/guides/routing/) y [colecciones de contenido](https://docs.astro.build/en/guides/content-collections/).

### 8.2 Archivos principales

- `src/pages/index.astro`: contenido y estructura de la landing.
- `src/styles/global.css`: estilos generales y reglas adaptables.
- `astro.config.mjs`: configuración base de Astro.
- `package.json`: versión, motor Node y comandos del proyecto.
- `dist/`: resultado compilado; no es la fuente editable.

### 8.3 Comandos de trabajo

```bash
npm install
npm run dev
npm run build
npm run preview
```

El procedimiento de publicación manual será compilar con `npm run build` y subir el contenido de `dist/` al proveedor que se elija. No hay configuración de alojamiento de ChatGPT/OpenAI y este informe no recomienda crearla.

---

## 9. CSS y sistema visual

### 9.1 Enfoque actual

La landing usa CSS nativo, sin preprocesador ni biblioteca de utilidades. La composición se apoya en:

- CSS Grid para avisos, feed, ubicaciones, metodología y bloques en dos columnas.
- Flexbox para encabezado, hero y pie.
- `clamp()` para tipografía, alturas y espaciados fluidos.
- `svh` para adaptar el hero a la altura útil del dispositivo.
- `aspect-ratio` y `object-fit: cover` para las imágenes cuadradas del feed.
- Dos puntos de quiebre principales: `720px` y `480px`.
- Carga diferida (`loading="lazy"`) para las miniaturas del feed.

Astro admite tanto CSS global importado como estilos encapsulados por componente. La documentación oficial explica que los estilos dentro de un componente se aíslan automáticamente, lo que será útil cuando la portada se divida en piezas reutilizables: [Styles and CSS — Astro](https://docs.astro.build/en/guides/styling/).

### 9.2 Paleta detectada

| Uso | Color |
| --- | --- |
| Azul petróleo principal | `#123f4a` |
| Azul profundo de pie | `#082e38` |
| Azul de bloque | `#056d90` |
| Turquesa | `#159bbb` |
| Coral | `#e9556f` |
| Naranjo | `#f18f57` |
| Amarillo acento | `#f4cd70` |
| Fondo cálido | `#f5f2ec` |
| Blanco | `#ffffff` |

La combinación evoca mar, bosque, madera y comunidad. El contraste debe verificarse en cada combinación antes del lanzamiento, especialmente para textos pequeños sobre degradados y fotografías.

### 9.3 Tipografía

La pila actual es `Avenir Next`, `Avenir`, `Segoe UI`, `sans-serif`. Como Avenir no está disponible en todos los sistemas, la apariencia cambia según el dispositivo.

**Recomendación:** decidir entre una tipografía de sistema consistente o una fuente web con licencia, archivos locales y subconjuntos necesarios. Evitar depender de una fuente que el sitio no distribuye.

### 9.4 Mejoras CSS recomendadas

- Convertir colores, anchos y espaciados repetidos en variables CSS con nombres semánticos.
- Separar `global.css` en base, tokens y estilos por componente cuando aparezcan más páginas.
- Añadir estados de foco visibles para teclado, no solo `:hover`.
- Respetar `prefers-reduced-motion` en ampliaciones o futuras animaciones.
- Probar el layout en 320, 375, 768, 1024 y 1440 píxeles.
- Revisar `color-scheme: dark`, porque la mayor parte de la página es clara y futuros controles nativos podrían heredar una apariencia incorrecta.
- Evitar selectores globales demasiado amplios cuando se creen páginas internas.

---

## 10. Imágenes y medios

### 10.1 Estado actual

Las fotografías, el logotipo y las miniaturas se cargan desde `vinculoschiloe.cl`. Esto permitió reproducir rápidamente la identidad visual, pero deja la nueva web dependiente del servidor WordPress anterior. Si cambia una URL, se borra un archivo o se bloquea el acceso externo, la landing pierde imágenes.

La etiqueta HTML `<img>` con una URL remota no recibe automáticamente toda la optimización de imágenes de Astro. La documentación oficial recomienda configurar dominios remotos autorizados o trasladar los recursos al flujo de `<Image />`/`<Picture />`: [Images — Astro](https://docs.astro.build/en/guides/images/).

### 10.2 Recomendación

- Confirmar propiedad y autorización de cada fotografía.
- Descargar desde la fuente original únicamente los recursos aprobados por la organización.
- Guardar una copia controlada en el repositorio o en el futuro almacenamiento de medios.
- Generar variantes WebP/AVIF, dimensiones responsivas y tamaños explícitos.
- Escribir descripciones reales; no repetir el mismo `alt` genérico en todas las publicaciones.
- No usar fotografías sensibles de procesos terapéuticos sin autorización expresa.

---

## 11. Datos e integraciones

| Integración | Estado actual | Requisito siguiente |
| --- | --- | --- |
| Instagram escolar | Seis miniaturas estáticas | Feed autorizado, caché y enlaces por publicación |
| Instagram institucional | Enlace en pie | Confirmar relación con la cuenta escolar |
| Matrícula | Google Forms externo | Confirmar propietario, vigencia y texto de privacidad |
| Cuenta pública | Enlace al WordPress anterior | Migrar PDFs aprobados a almacenamiento controlado |
| Mapas | Enlaces de búsqueda de Google Maps | Validar dirección y coordenadas |
| Teléfono | Enlace `tel:` | Confirmar número y a qué unidad corresponde |
| Noticias | No implementadas | Colección de contenido con esquema validado |
| Formulario de contacto | No implementado en la réplica | Definir receptor, privacidad, anti-spam y manejo de errores |

Para noticias, una colección de Astro puede validar campos como `title`, `description`, `pubDate`, `updatedDate`, `author`, `category`, `cover`, `coverAlt` y `source`. La [documentación de colecciones](https://docs.astro.build/en/guides/content-collections/) indica que pueden cargar Markdown, JSON o fuentes remotas y validar su estructura.

---

## 12. Accesibilidad

### Fortalezas actuales

- Documento en español (`lang="es"`).
- Secciones semánticas con títulos asociados.
- Enlaces telefónicos y de mapas utilizables sin JavaScript.
- Etiquetas `aria-label` en bloques relevantes.
- Dimensiones declaradas en algunos recursos y carga diferida en el feed.

### Pendientes

- Añadir enlace “Saltar al contenido”.
- Verificar contraste bajo WCAG 2.2 AA.
- Diseñar foco visible y navegación completa por teclado.
- Reemplazar textos alternativos genéricos por descripciones específicas.
- No depender exclusivamente del color para diferenciar avisos.
- Definir títulos claros para enlaces externos y documentos PDF.
- Probar zoom al 200 %, lectores de pantalla y movimiento reducido.
- Agregar transcripción o subtítulos si en el futuro se integran videos.

La accesibilidad es especialmente importante porque la web se dirige a públicos de edades, contextos y niveles de alfabetización digital diversos.

---

## 13. SEO y metadatos

### Implementado

- Título de página.
- Descripción breve.
- `charset` y `viewport`.
- Jerarquía principal con un `h1`.

### Recomendado antes de publicar

- URL canónica.
- Metadatos Open Graph y tarjeta social.
- Imagen social propia y optimizada.
- Favicon y manifiesto.
- `robots.txt` y sitemap.
- Datos estructurados de `Organization` y, si corresponde, `School`, con información verificada.
- Títulos y descripciones únicos para futuras páginas.
- Redirecciones desde las URLs históricas que se decida conservar.
- Página 404.
- Analítica respetuosa de la privacidad, solo si existe una necesidad institucional clara.

---

## 14. Rendimiento, seguridad y privacidad

### Rendimiento

La arquitectura estática y la ausencia de un framework de cliente reducen JavaScript y complejidad. Los principales riesgos actuales son el peso de fotografías remotas, el fondo grande del hero y la futura integración social.

Acciones recomendadas:

- Optimizar y versionar imágenes.
- Precargar solo el recurso realmente crítico del hero.
- Mantener dimensiones para evitar saltos de diseño.
- Cargar el feed después del contenido crítico o resolverlo durante la compilación.
- Medir Lighthouse y WebPageTest con red móvil antes de publicar.

### Seguridad

- No incluir tokens de Instagram ni claves de formularios en el código del navegador.
- Usar variables de entorno durante la compilación.
- Limitar dominios externos para imágenes, scripts y formularios.
- Evitar widgets de terceros que inyecten JavaScript sin auditoría.
- Mantener Node y Astro actualizados con una revisión planificada, no automática y ciega.

### Privacidad

- Documentar qué datos recibe cada formulario, con qué propósito y durante cuánto tiempo se conservan.
- No cargar mapas, videos o redes embebidas antes de definir el tratamiento de cookies y terceros.
- Validar consentimiento para imágenes de menores de edad y personas en tratamiento.
- Mostrar canales de contacto apropiados sin exponer información personal innecesaria.

---

## 15. Estado de implementación

### Ya implementado

- Proyecto Astro mínimo y compilable.
- Landing responsive en una sola ruta.
- Identidad visual base y hero.
- Avisos de matrícula y cuenta pública.
- Maqueta visual de “La comunidad en movimiento”.
- Llamado a Comunidad Terapéutica.
- Ubicaciones, “Quiénes somos”, ABP y pie de página.
- Repositorio en GitHub.

### Pendiente prioritario

1. Confirmar textos, teléfonos, direcciones, redes y vigencia de enlaces.
2. Implementar el feed autorizado de Instagram.
3. Obtener y alojar copias aprobadas de imágenes y documentos.
4. Agregar contenido de metodología basado en casos reales recientes.
5. Definir tres noticias destacadas actuales.
6. Completar SEO, accesibilidad y pruebas de rendimiento.
7. Elegir el servicio de hosting y desplegar manualmente.

### Fuera del alcance actual

- Menú definitivo.
- Páginas internas de Cursos, Comunidad y Noticias.
- Panel de administración o CMS.
- Automatización de despliegue.
- Migración completa del WordPress.

---

## 16. Criterios de aceptación para la landing final

- La portada explica en menos de un minuto qué es Vínculos Chiloé y sus dos líneas de trabajo.
- No se construyen todavía páginas internas del menú.
- “La comunidad en movimiento” obtiene publicaciones reales de la cuenta autorizada o muestra un respaldo editorial explícito.
- Ninguna cifra aparece sin año y fuente.
- Matrícula, cuenta pública, teléfono y ubicaciones están validados.
- Todas las fotografías tienen autorización, dimensión y texto alternativo pertinente.
- La página funciona desde 320 px, por teclado y con zoom al 200 %.
- La compilación `npm run build` termina sin errores.
- El resultado no depende de servicios de publicación de ChatGPT/OpenAI.
- El despliegue se realiza únicamente cuando el propietario elija el proveedor.

---

## 17. Fuentes consultadas

Todas las fuentes web se consultaron el **8 de septiembre de 2026**.

### Fuentes institucionales de Vínculos Chiloé

1. [Vínculos Chiloé — página principal](https://vinculoschiloe.cl/). Fuente para definición institucional, ABP, matrícula, cuenta pública, contacto, ubicaciones, archivo de noticias y proyectos sobre bosque y mar.
2. [Comunidades de Aprendizaje](https://vinculoschiloe.cl/comunidades-de-aprendizaje/). Fuente para el enfoque comunitario, Castro, Anexo Lemuy y el archivo histórico de aprendizaje.
3. [Comunidades de Aprendizaje Castro](https://vinculoschiloe.cl/comunidades-de-aprendizaje-castro/). Fuente para misión, visión, enfoque, historia, perfil de estudiantes, talleres y metodología por proyectos.
4. [Comunidad Terapéutica](https://vinculoschiloe.cl/comunidad-terapeutica/). Fuente para objetivos, público, modalidades de atención, trabajo territorial y redes.
5. [Directorio y documentos de Comunidad Terapéutica](https://vinculoschiloe.cl/comunidad-terapeutica-2/). Fuente para vigencia del directorio y enlaces a memoria y balance.
6. [Memoria Anual ONG Vínculos 2023](https://vinculoschiloe.cl/wp-content/uploads/2024/11/MEMORIA-ANUAL-2023-ONG-VINCULOS.pdf). Fuente para misión, visión, áreas de trabajo, público objetivo, cobertura terapéutica 2023 y acciones territoriales.
7. [Cuenta Pública Escuela Vínculos Chiloé 2019](https://vinculoschiloe.cl/wp-content/uploads/2022/12/CUENTA_PUBLICA_2019.pdf). Fuente para proyectos “Con los pies en el Barrio” y “Conectividad de Lemuy”.
8. [Cuenta Pública Escuela Vínculos Chiloé 2020](https://vinculoschiloe.cl/wp-content/uploads/2021/04/CUENTA_PUBLICA_2020_ESCUELA_VINCULOS_CHILOE.pdf). Fuente para el proyecto “Lo que nos cuenta el bosque de Chiloé”.
9. [Cuenta Pública Escuela Vínculos Chiloé 2023](https://vinculoschiloe.cl/wp-content/uploads/2024/04/CUENTA_PUBLICA_2023.pdf). Documento público reciente detectado para revisión editorial posterior.
10. [Navega Chilwé](https://vinculoschiloe.cl/2019/aprendizaje/navega-chilwe-estudiantes-de-la-escuela-vinculos-chiloe-navegan-en-los-mares-del-archipielago/), publicado el 10 de septiembre de 2019. Caso institucional de aprendizaje, navegación y cultura del mar.

### Fuentes externas

11. [“Comunidad de Aprendizaje Vínculos: educación con pertinencia local” — El Insular](https://elinsular.cl/2024/05/17/comunidad-de-aprendizaje-vinculos-educacion-con-pertinencia-local/), 17 de mayo de 2024. Fuente periodística para el proyecto educativo, ABP, tamaño de cursos, trabajo territorial, redes locales y cuenta de Instagram escolar.
12. [“SENDA Los Lagos y la Comunidad Terapéutica Vínculos inauguran primer centro de tratamiento para mujeres con enfoque de género en Chiloé” — SENDA](https://www.senda.gob.cl/noticia/senda-los-lagos-y-la-comunidad-terapeutica-vinculos-inauguran-primer-centro-de-tratamiento-para-mujeres-con-enfoque-de-genero-en-chiloe/), 14 de agosto de 2025. Fuente pública para la nueva línea de atención a mujeres en Castro.

### Fuentes técnicas

13. `migration-blueprint.zip`, archivo entregado por el propietario. Inventario `schema-only` para WordPress, tema, plugins y superficies técnicas. No contiene el contenido editorial completo.
14. [Project structure — Astro](https://docs.astro.build/en/basics/project-structure/). Referencia para organización de archivos y salida estática.
15. [Routing — Astro](https://docs.astro.build/en/guides/routing/). Referencia para rutas basadas en archivos.
16. [Styles and CSS — Astro](https://docs.astro.build/en/guides/styling/). Referencia para CSS global, CSS por componente y encapsulamiento.
17. [Content collections — Astro](https://docs.astro.build/en/guides/content-collections/). Referencia para estructurar y validar futuras noticias.
18. [Images — Astro](https://docs.astro.build/en/guides/images/). Referencia para optimización y autorización de imágenes remotas.

---

## 18. Conclusión

La reconstrucción en Astro es adecuada para esta etapa porque la prioridad es una portada rápida, clara y estable, con poco JavaScript y sin mantener toda la infraestructura del WordPress anterior. El código actual ya establece el lenguaje visual y la secuencia principal.

El siguiente salto de calidad no consiste en agregar más bloques genéricos, sino en conectar la landing con actividad y evidencia real: un feed autorizado de Instagram bajo **“La comunidad en movimiento”**, proyectos ABP fechados, noticias curadas, documentos públicos vigentes y datos de contacto confirmados. Con esos elementos, la página podrá transmitir no solo qué dice Vínculos Chiloé sobre sí misma, sino cómo trabaja y qué ocurre hoy en su comunidad.
