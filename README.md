# DiarIA

De tu tema a tu podcast diario, con citas verificadas. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/diaria/

**Idiomas:** español (por defecto), inglés, portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

- Uno o varios **radares** (perfiles): ámbito, prioridades ordenadas, temas de fondo, exclusiones, revistas a vigilar, idioma, duración (10/15/20 min), una o dos voces y frecuencia (diaria, laborables o N por semana). Se mezclan alternando o con un peso por radar.
- **Un clic** («Preparar el episodio de hoy», o 3-5 seguidos): busca candidatos con acceso abierto en Europe PMC y OpenAlex (y en tu biblioteca de PDF), los valora con tu perfil y elige uno.
- **Solo con texto completo**: Europe PMC (XML), Unpaywall/OpenAlex (PDF) o un PDF tuyo. Si no hay texto completo, el artículo pasa a «Sugerencias» con su enlace.
- **Referencia comprobada en Crossref** (autores, año, revista, volumen, páginas). Exporta RIS y BibTeX.
- **Informe de siete apartados** más ficha técnica, y **guion** (narración o diálogo) con una cita literal de 8 a 25 palabras por idea.
- **Podcast** con la voz de OpenAI (gpt-4o-mini-tts) y duración real medida.
- Historial con estado (escuchado/pendiente), cobertura de temas, copia de seguridad (sin audio ni claves).

## Qué comprueba el código y qué hace la IA

| La IA | El código |
|---|---|
| Valora cada candidato de 0 a 10, le asigna tema y tipo, redacta informe y guion | Puntuación final (+1 revisión/posicionamiento/opinión, −2 tema repetido en los últimos 5 episodios, +1 tema sin episodio) y desempates |
| Propone una cita literal por idea | Busca la cita en el texto (ignora mayúsculas, tildes, ligaduras y guiones de final de línea); exige 8-25 palabras; si falla, una corrección y, si persiste, elimina la idea |
| Escribe la presentación del artículo | Solo admite datos de la ficha verificada en Crossref |
| — | Descarte de errata, preprints y tipos excluidos; cifras que no están en el artículo; duración del audio |

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude (texto). La voz la genera siempre OpenAI, con su clave. Las claves se guardan solo en el navegador. No hace falta servidor.

## Privacidad

Radares, historial, texto de los artículos y audios se guardan en este navegador (IndexedDB). Salen: palabras de búsqueda y DOI hacia Europe PMC, OpenAlex, Crossref y Unpaywall (datos públicos); hacia tu proveedor de IA, tu perfil con correos, DNI y teléfonos enmascarados, resúmenes y el texto del artículo elegido; hacia OpenAI, el guion para la voz. Antes del primer envío de cada sesión se muestra la muestra del perfil. El «contexto de aplicación» solo desempata y nunca llega al informe ni al guion.

## Límites

- La verificación comprueba que **la cita existe en el texto**, no que la idea la interprete bien. Si se elimina una idea, el texto del apartado puede seguir mencionándola: la app lo avisa, pero hay que revisarlo.
- La calidad del artículo (tipo, diseño, muestra) la juzga la IA a partir del resumen; ante la duda se conserva y se avisa.
- Muchos PDF de editoriales no se pueden descargar desde el navegador (CORS): entonces se pide subir el PDF. Los PDF de dos columnas pueden mezclar frases y dar falsas alarmas.
- Funciona con artículos en acceso abierto indexados en PubMed/PMC; no automatiza el acceso institucional.
- No se ejecuta sola a una hora fija: hay que abrir la app (o usar «Preparar 3/5 episodios»).
- Probada con servicios simulados; **no se ha probado con claves reales ni con la voz real**.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) y Miguel Pastor González (Universidad Miguel Hernández de Elche).

A partir de la especificación «De tu tema a tu podcast diario» de Miguel Pastor González, cuyo flujo diario funciona desde septiembre de 2026 sobre Claude Code; esta versión lo lleva al navegador, con varios radares y la clave de cada persona.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. y Pastor González, M. (2026). *DiarIA* (v1.0.0) [Software]. (DOI en trámite)

## Licencia

MIT. Véase [LICENSE](LICENSE).
