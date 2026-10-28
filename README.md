# Project Explainer

Skill que ayuda a explicar conceptos, herramientas, procedimientos y buenas prácticas usando el proyecto como contexto y recurriendo también a conocimientos generales y fuentes externas pertinentes. Responde en español por defecto, o en otro idioma si el usuario lo solicita o el contexto indica claramente que lo prefiere. Distingue los hechos comprobados de las hipótesis y los ejemplos; ante una pregunta explicativa, no modifica archivos ni ejecuta el procedimiento sin una solicitud expresa.

## Requisitos y compatibilidad

- Un agente que pueda leer instrucciones Markdown y, para aprovechar el contexto, acceder a los archivos del proyecto.
- Acceso a fuentes actualizadas cuando la respuesta dependa de información cambiante. Si no está disponible, el agente debe indicar la limitación.
- `SKILL.md` utiliza el formato abierto [Agent Skills](https://agentskills.io/specification/). La compatibilidad de instalación y activación depende del agente; la calidad de la respuesta depende también del modelo y de sus herramientas. No se garantiza un resultado idéntico en todos ellos.

## Instalación en Codex

En una conversación con Codex, solicita:

> Usa `$skill-installer` para instalar la skill de la raíz del repositorio `simonisdev/explicador-de-proyectos`. Usa la ruta `.` y el nombre de destino `project-explainer`.

El instalador incluido en Codex requiere indicar tanto la ruta `.` como el nombre de destino para una skill situada en la raíz. Puedes darle la dirección `https://github.com/simonisdev/explicador-de-proyectos` junto con la instrucción anterior. La skill quedará disponible en el siguiente turno. Si ya existe una carpeta `project-explainer`, el instalador no la sobrescribe: revisa primero la sección de actualización.

Para usarla desde un proyecto, abre ese proyecto en el agente e invócala, por ejemplo:

> `$project-explainer` Explícame qué hace el archivo de configuración de este proyecto.

> `$project-explainer` ¿Qué significa ejecutar las pruebas de integración en este proyecto?

El agente necesita acceso al proyecto para fundamentar sus respuestas en sus archivos. Si no dispone de ese acceso, puede ofrecer una explicación general e indicar la limitación. Si no puede acceder a una fuente o verificar un dato, debe indicarlo.

## Otros agentes

Consulta la documentación de tu agente para saber si admite Agent Skills y dónde instala o descubre carpetas de skills. Si admite el formato, instala o copia la carpeta del repositorio con el nombre `project-explainer` en la ubicación indicada por ese agente. La forma de invocarla puede variar.

Si no admite skills de forma nativa, abre `SKILL.md` y proporciona su contenido como instrucciones en la conversación, junto con el acceso al proyecto cuando sea posible. En ese caso la activación manual, los permisos y la forma de acceder a archivos dependen de la herramienta.

## Actualización

Las instalaciones son copias locales y no se actualizan automáticamente al cambiar GitHub. Antes de actualizar, revisa los cambios en el repositorio y conserva cualquier modificación local que quieras mantener. Después, reemplaza la carpeta instalada siguiendo las instrucciones de tu agente.

En Codex, el instalador no reemplaza una carpeta existente. Para conservarla, renómbrala como copia de respaldo y vuelve a ejecutar la instrucción de instalación. La carpeta habitual es `~/.codex/skills/project-explainer`; si has configurado `CODEX_HOME`, está en la carpeta `skills/project-explainer` de esa ubicación. No elimines la copia anterior hasta haber comprobado la nueva.

## Licencia

[MIT](LICENSE).
