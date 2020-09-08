---
YIP: 0
Título: Propósito y guías para una YIP
Estatus: Implementada 
Autor: La comunidad de yEarn
Discuciones: https://gov.yearn.finance/
Fecha de creación: 2020-07-22
Fecha de actualización: 2020-09-03
---

## ¿Qué es una YIP?

Una YIP es una propuesta de mejora de yEarn (yEarn Improvement Proposal en inglés) que ha sido adaptada de las SIP utilizadas por Synthetix. La finalidad de este proceso es asegurar que los cambios en yEarn son transparentes y democráticos. Una YIP es un documento que provee información a la comunidad de yEarn a cerca de un cambio propuesto que afecta al sistema. El autor de esta es el responsable de buscar el concenso y la aprobación de la comunidad, además de documentar los pros y contras presentados por los distintos miembros de la comunidad acerca del cambio propuesto.

## Fundamentación de las YIPs

Nosotros pretendemos que las YIPs sean el principal mecanismo mediante el cual se proponen mejoras, se analiza la posición de la comunidad frente a un problema y se documentan posibles cambios en yEarn. Como estas son almacenadas en archivos de texto en un repositorio, esta queda guardada para su revisión en un futuro.

Se recomienda encarecidamente que cada YIP contenga una propuesta clave o una idea nueva. Cuanto más concisa sea la YIP, más probabilidades tendrá de tener éxito.

Una YIP debe de cumplir ciertos criterios para ser aceptada. Debe de ser clara y debe tener una descripción completa y detallada de la propuesta que se quiere hacer. La propuesta debe de representar un cambio significativo en un aspecto del sistema.

## Esquema de trabajo de una YIP

Las partes involucradas en el proceso son el *autor*, los [*editores*](#yip-editors) y la comunidad de yEarn.

:warning: Antes de empezar, evalúa detenidamente tu idea. Pregúntale a la comunidad de yEarn primero si la idea es original para evitar perder el tiempo en una propuesta que será rechazada en base a una investigación previa (buscar en Internet no siempre va a funcionar). Además, también es de cierta utilidad asegurarte de que la idea es aplicable a la comunidad entera y no solo al autor de ella. Sólo por el hecho de que una idea le parezca buena a su autor no significa que vaya a tener el efecto previsto por él. Los foros públicos en los que puedes captar el interés de los demás hacia tu YIP son [el Discord de yEarn no oficial] o [el canal de Telegram de yEarn no oficial].

Tu papel como autor es escribir la YIP usando el estilo y el formato descrito a continuación, guiar las discusiones en los foros apropiados y construir concenso alrededor de la idea. Este es el camino que sigue una YIP exitosa: 

```
Propuesta -> Aprobada -> Implementada
  ^                     |
  +----> Rechazada      +----> Moribunda 
  |
  +----> Retirada
  v
Diferida
```
Cada cambio de estado es pedido por el autor de la YIP y revisado por los editores. Haz un pull request para actualizar el estado de la YIP. Por favor, incluye también una dirección donde la gente debería ir para continuar la discusión a cerca de tu YIP. Los editores procesarán el cambio de estado siguiendo las siguientes directrices:

* **Work in progress (WIP)** -- Cuando un autor ha preguntado la comunidad de yEarn si su idea tiene alguna posibilidad de salir adelante, él redactará un borrador de YIP como un [pull request]. Considera incluir también una implementación si servirá de ayuda a la hora de que otras personas estudien la YIP.

* **Propuesta** Si está de acuerdo, un editor asignará a la YIP un número y fusionará la pull request. El editor no denegará ninguna YIP sin justificación. Las YIPs propuestas se discutirán en los canales apropiados. Si hay un nivel razonable de consenso en torno al cambio en la convocatoria de gobernanza, el cambio pasará a estar aprobado. Si el cambio es controvertido, se puede realizar una votación entre los titulares de tokens para resolver el problema o se puede retrasar la aprobación hasta que se alcance el consenso.

* **Aprobada** -- Esta YIP ha sido acogida positivamente por la comunidad y ahora se prioriza su desarrollo.
* **Implementada** -- Esta YIP ha sido implementada y desplegada en mainnet.
* **Rechazada** -- Esta YIP ha fracasado en su intento de conseguir el conceso de la comunidad.
* **Retirada** --  Esta YIP ha sido retirada por su autor o autores.
* **Diferida** -- Esta YIP está pendiente de otra YIP o otro cambio con el que se debería incluir en conjunto.
* **Moribunda** -- Esta YIP ha sido implementada en el pasado pero ahora ha quedado obsoleta y no requiere un reemplazo explícito.

## ¿Qué forma una YIP exitosa?

Cada YIP debe de estar compuesta por las siguientes partes:

- Preámbulo - RFC 822 style headers que contienen metadatos a cerca de la YIP, incluído el número de la YIP, un pequeño título descriptivo (limitado a 44 caracteres) y los datos del autor.
- Explicación corta - “Si no puedes explicarlo con palabras sencillas, entonces es que no lo entiendes lo suficiente.” Proporcione una explicación simplificada y accesible para la gente del YIP.
- Resumen - Una descripción corta (~200 palabras) del problema técnico que se está abordando.
- Motivación (*opcional) - La motivación es una parte crítica para las YIPs que desean cambiar yEarn. Aquí se debe explicar claramente por qué la especificación existente es inadecuada para resolver el problema que la YIP resuelve. Las YIPs presentadas sin suficiente motivación puede ser rechazadas por completo.
- Especificación - La especificación técnica debe describir la sintaxis y semántica de cualquier característica nueva.
- Razonamiento fundamental - El fundamento da cuerpo a la especificación al describir qué motivó el diseño y por qué se tomaron decisiones de diseño particulares. Debe describir los diseños alternativos que se consideraron y el trabajo relacionado. El razonamiento también debe proporcionar evidencia de consenso dentro de la comunidad y en él se debe discutir las objeciones o preocupaciones importantes que surjan durante la discusión.

- Test Cases - Test cases may be added during the implementation phase but are required before implementation.
- Copyright Waiver - All YIPs must be in the public domain. See the bottom of this YIP for an example copyright waiver.

## YIP Formats and Templates

YIPs should be written in [markdown] format.
Image files should be included in a subdirectory of the `assets` folder for that YIP as follows: `assets/yip-X` (for yip **X**). When linking to an image in the YIP, use relative links such as `../assets/yip-X/image.png`.

## YIP Header Preamble

Each YIP must begin with an [RFC 822](https://www.ietf.org/rfc/rfc822.txt) style header preamble, preceded and followed by three hyphens (`---`). This header is also termed ["front matter" by Jekyll](https://jekyllrb.com/docs/front-matter/). The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` yip:` <YIP number> (this is determined by the YIP editor)

` title:` <YIP title>

` author:` <a list of the author's or authors' name(s) and/or username(s), or name(s) and email(s). Details are below.>

` * discussions-to:` \<a url pointing to the official discussion thread at gov.yearn.finance\>

` status:` < WIP | PROPOSED | APPROVED | IMPLEMENTED >

` created:` <date created on>

` * updated:` <comma separated list of dates>

` * requires:` <YIP number(s)>

` * resolution:` \<a url pointing to the resolution of this YIP\>

Headers that permit lists must separate elements with commas.

Headers requiring dates will always do so in the format of ISO 8601 (yyyy-mm-dd).

#### `author` header

The `author` header optionally lists the names, email addresses or usernames of the authors/owners of the YIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the author header value must be:

> Random J. User &lt;address@dom.ain&gt;

or

> Random J. User (@username)

if the email address or GitHub username is included, and

> Random J. User

if the email address is not given.

#### `discussions-to` header

While an YIP is in WIP or Proposed status, a `discussions-to` header will indicate the URL at [gov.yearn.finance](https://gov.yearn.finance/) where the YIP is being discussed.

#### `created` header

The `created` header records the date that the YIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

#### `updated` header

The `updated` header records the date(s) when the YIP was updated with "substantial" changes. This header is only valid for YIPs of Draft and Active status.

#### `requires` header

YIPs may have a `requires` header, indicating the YIP numbers that this YIP depends on.

## Auxiliary Files

YIPs may include auxiliary files such as diagrams. Such files must be named YIP-XXXX-Y.ext, where “XXXX” is the YIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

## YIP Editors

The current YIP editors are:

` * Artem K (@banteg)`

` * Cooper Turley (@Cooopahtroopa)`

` * Daryl Lau (@Daryllautk)`

` * Klim K (@milkyklim)`

` * Sunil Srivatsa (@alphastorm)`

## YIP Editor Responsibilities

For each new YIP that comes in, an editor does the following:

- Read the YIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to get to final status.
- The title should accurately describe the content.
- Check the YIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the YIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the YIP is ready for the repository, the YIP editor will:

- Assign an YIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this YIP)

- Merge the corresponding pull request

- Send a message back to the YIP author with the next step.

The YIP editors monitor YIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on YIPs. We merely do the administrative & editorial part.

## History

The YIP document was derived heavily from the SIP Synthetix Improvement Proposal document in many places text was simply copied and modified. Any comments about the YIP document should be directed to the YIP editors.

### Bibliography

[the unofficial yEarn Discord]: https://discord.com/invite/3AGgWxy
[the unofficial yEarn Telegram]: https://t.me/yearnfinance
[pull request]: https://github.com/iearn-finance/YIPS/pulls
[markdown]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
