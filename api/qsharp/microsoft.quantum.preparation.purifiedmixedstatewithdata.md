---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: Funktionen PurifiedMixedStateWithData
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229961"
---
# <a name="purifiedmixedstatewithdata-function"></a>Funktionen PurifiedMixedStateWithData

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en åtgärd som förbereder en rening av ett blandat tillstånd, Entangled med ett register som representerar en specifik samling data.
Ett "rena blandat tillstånd med data" syftar på ett tillstånd för formatet Σi √ Pi | i ⟩ | XI ⟩ | garbagei ⟩ där varje XI är en bitstring som innehåller ytterligare data som är kopplade till registret | i ⟩.

Se https://arxiv.org/pdf/1805.03662.pdf?page=15 för ytterligare diskussion.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Beskrivning

Använder den Quantum-ROM-teknik som representerar en specifik densitet, som returnerar denna representation som en åtgärd för förberedelse av tillstånd.

I synnerhet en lista över $N $ koefficienter $ \ alpha_j $ och en bitstring $ \vec{x}_j $ som är associerad med respektive koefficient. den här funktionen returnerar en åtgärd som använder Quantum-Rom-tekniken för att förbereda en ungefärlig $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ av blandat tillstånd $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $ där varje $p _j $ är en uppskattning av den aktuella koefficienten $ \ alpha_j $, t. ex. $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ för varje $j $.

När du godkände ett index register och ett register över skräp qubits, inlednings vis i status $ \ket {0} \ket{00\cdots 0}, den returnerade åtgärden förbereder båda registren i reningen av $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $ så att att återställa och avallokera skräp registreringen är den önskade förberedelsen i mål felet $ \epsilon $.

## <a name="input"></a>Indata

### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mål felet $ \epsilon $.


### <a name="coefficients--doublebool"></a>koefficienter: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Matris med $N $-koefficienter som anger sannolikheten för grund tillstånd, tillsammans med bitstring $ \vec{x} _j $ som är associerad med respektive koefficient.
Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Utdata: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

En åtgärd som förbereder $ \tilde \rho $ som en rening på ett gemensamt index och skräp registrering.

## <a name="remarks"></a>Kommentarer

De koefficienter som anges för den här åtgärden är normaliserade efter 1 – normal, så att koefficienterna alltid anses som beskriver en giltig kategoriska-sannolikhets fördelning.

## <a name="references"></a>Referenser

- Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. preparation. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)