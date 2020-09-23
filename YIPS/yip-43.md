---
YIP: 43
Título: Mejorar las categorías de las YIPs	
Estado: Rechazada
Autor: sam bacha <sam@freighttrust.com>
Discusiones: https://gov.yearn.finance/t/proposal-add-new-statuses-to-yip-proposals-non-protocol-change/3608

Fecha de creación: 2020-08-24
---


## Explicación corta
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->

Añadir nuevos `estado`(s) a las `YIPs` para que el(los) autor(es) pueda(n) gestionar mejor las `YIPs` en el contexto de la colaboración comunitaria y para que la gobernanza cuente con procedimientos adecuados para fomentar la cooperación comunitaria.

## Resumen
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the YIP is implemented, not *why* it should be done or *how* it will be done. If the YIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->

Esta propuesta *solo* agregará al estado actual de las `YIPs propuestas` en el sentido de que solo cambia los _potenciales_`estados` disponibles para una `YIP`. No supone ningún cambio en el `protocolo`: solo afecta a la documentación y los procedimientos de gobernanza (únicamente aquellos off-chain).

Propongo los siguientes cambios para reflejar un nuevo estado de las posibles 'YIPs':

1. Modificación de la plantilla de la YIP
2. Modificación del validador de Gemfile de la YIP
3. Modificación del archivo README de la YIP

## Motivación
<!--This is the problem statement. This is the *why* of the YIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the YIP proposes changing how something is calculated, you must address *why* the current calculation is inaccurate or wrong. This is not the place to describe how the YIP will address the issue!-->

 > El estado actual de los procedimientos para las `YIPS` es inadecuado, ya que limita innecesariamente los posibles resultados de una `YIP` propuesta, mientras que no brinda ni al autor(es) ni al consejo de gobernanza flexibilidad para poder tratar con las `YIPs` propuestas por la comunidad

Este es un cambio de *documentación* y *procedimiento*. De hecho, no hay una descripción explícita para proponer tales cambios en la gobernanza *(que pueda encontrar).*

Este cambio es necesario ya que explica mejor la *intención* del formato de la YIP a el(los) autor(es). También proporciona funcionalidad adicional de gobernanza en sus procedimientos a fin de no 'alienar' potencialmente a el(los) autor(es) al rechazar una YIP cuando podría haber sido retirada. Esto asegura que también el(los) autor(es) participa(n) activamente en el proceso de su propuesta presentada y en la comunidad en general (en la medida en que estén al tanto de otras YIPs con las que pueden competir).

## Especificación

*Cambios en 'NEGRITA'*

Propuesta - una YIP que está lista para ser revisada en una llamada de gobernanza
Aprobada - una YIP que ha sido aceptada para su implementación por la comunidad de yEarn.
Implementada - una YIP que ya está en mainnet.
Rechazada - una YIP que ha sido rechazada.
**Retirada - una YIP que ha sido retirada por su(s) autor(es).**
**Diferida - una YIP que la gobernanza ha decidido poner en pausa hasta que otra YIP u otro cambio con la que debería ir en conjunto sea propuesto.**
**Moribunda - una YIP que hace tiempo fue implentada. Este ha quedado obsoleta 'Y' no requiere ninguna sustitución explícita.** 

El estado "Retirada" es similar: significa que el autor de la YIP ha decidido que la YIP es en realidad una "mala" idea, o ha aceptado que otra propuesta contra la que compite es una mejor alternativa.

### Esquema de trabajo propuesto
```
Propuesta -> Aprobada -> Implementada
  ^                     |
  +----> Rechazada      +----> Moribunda 
  |
  +----> Retirada
  v
Diferida
```

#### Nuevos estados para las YIPs

> To be added are the following

- Withdrawn
- Moribund
- Deferred


### Visión de conjunto
<!--This is a high level overview of *how* the YIP will solve the problem. The overview should clearly describe how the new feature will be implemented.-->

#### Nuevos estados para las YIPs
- Withdrawn
Means that the YIP author has decided that the YIP is actually a bad idea, or has accepted that a competing proposal is a better alternative.
- Moribund
Obsolete and requires no explicit replacement, it SHOULD be marked "Moribund"
- Deferred
Governance placed status upon a YIP that means that they would like to know more information, or that they would like to see if the author(s) can work with another proposed YIP and combine it into a single YIP, etc.


### Razón fundamental

The reasoning behind this is that it is unclear what will happen to a YIP should material facts change during its initial formal proposal and when its actually voted on by governance. Changes may be introduced between then, and the author may want to withdraw the proposal. This also frees up the governance council in that they are no longer obligated to reject every single YIP that may no longer be relevant, instead sharing the responsibility with the actual author(s). 

### Especificación técnica
<!--
NOTE: NO PROTOCOL CHANGES ARE PROPOSED 
THE ONLY TECHNICAL CHANGES ARE IN THE RUBY VALIDATION PROCESS FOR YIPS
-->
Technical implementation involves:

* changes in the validation Gemfile 
* changes in the template `.md` file

#### Cambios en el archivo plantilla `.md` 

Below is a sample `.yaml` file to illustrate the _new_ header that should be used in the `yip-template.md` file

```yaml
---
YIP: <YIP number>
Title: <YIP title>
Author: < firstName, lastName, @githubUsrName, contact@address.com >
Type: <Informational | Standards Track>
Status: <WIP | Proposed | Approved | Deferred | Withdrawn | Rejected |
           Implemented | Replaced | Moribund>
    Version: <major>[.<minor>]
    Created: <date created on, in ISO 8601 (yyyy-mm-dd) format>
    Requires (*optional): <YIP number(s)>
    Implementation (*optional): <Added if YIP passes>

Discussions-to: <Create a new thread on https://gov.yearn.finance/ and drop the link here>

* Requires: <YIP numbers>
* Replaces: <YIP numbers>
* Replaced-By: <YIP number>
---
```

#### Validador YIP (Ruby Gem)

> current version: `1.0.2`, should be bumped to `1.1.0`
Changes located [github.com/iearn-finance/yip_validator/blob/master/lib/yip_validator/validator.rb#L25](https://github.com/iearn-finance/yip_validator/blob/master/lib/yip_validator/validator.rb#L25)

```ruby
    validates_inclusion_of :status, in: ['WIP', 'Proposed', 'Approved', 'Implemented', 'Rejected']
```
```ruby
    validates_inclusion_of :status, in: ['WIP', 'Proposed', 'Approved', 'Implemented', 'Rejected', 'Withdrawn', 'Deferred', 'Moribund']
```

See Files Changed here [https://github.com/sambacha/yip_validator/tree/YIP-Proposed](https://github.com/sambacha/yip_validator/tree/YIP-Proposed)

### Casos de prueba

See `travis-ci` logs for the `Rub Gem` update here [https://travis-ci.com/github/sambacha/yip_validator/builds/181226022](https://travis-ci.com/github/sambacha/yip_validator/builds/181226022)

```bash
total:2, valid:2, invalid:0, errors:0
	statuses: [["Withdrawn", 1], ["Implemented", 1]]
  raises exception if it includes invalid yips
spec/fixtures/invalid/yip-7.md is NOT valid:	 {:status=>["is not included in the list"]}

```

## Derechos de autor
Derechos de autor y derechos relacionados con renuncia a través de [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
