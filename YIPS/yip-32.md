---
YIP: 32
Título: Remove YFI burning
Estado: Implemented
Autor: Sunil Srivatsa (@alphastorm)
Discusiones: https://gov.yearn.finance/t/yip-32-remove-yfi-burning/1907
Fecha de creación: 2020-08-01
---

## Explicación corta
Remove YFI burning from the protocol.

## Resumen
YFI represents a claim on yEarn protocol fees. To claim fees, YFI can either be burned or staked in the governance pool.

This YIP is to decide whether or not to keep the burning mechanism.

## Motivación
It makes no sense to burn because the price of YFI will always be higher than the claimable fee value. This is because YFI represents current assets in the fee pool plus future expected cashflows. Staking is just obviously better.

**A FAVOR**: Remove YFI burning from the protocol.

**EN CONTRA**: No change (start burning YFI for fees).

## Metadatos

| Nombre                | Valor                                      |
|---------------------|--------------------------------------------|
| Propuesta por         | 0x74630370197b4c4795bFEeF6645ee14F8cf8997D |
| Votos totales a favor     | 3054.9983 (97.89%)                         |
| Votos totales en contra | 65.8346 (2.10%)                            |
| Quorum              | 24.5% ✔                                    |
| Bloque inicial         | 10576777                                   |
| Bloque final           | 10594057                                   |

Fuente: [yieldfarming.info YFI Governance Information](https://yieldfarming.info/yearn/vote/)

## Derechos de autor
Derechos de autor y derechos relacionados con renuncia a través de [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
