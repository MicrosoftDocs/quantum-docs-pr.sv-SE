---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: Funktionen PurifiedMixedState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854292"
---
# <a name="purifiedmixedstate-function"></a>Funktionen PurifiedMixedState

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en åtgärd som förbereder en rening av ett blandat tillstånd.
Ett "renat blandat tillstånd" syftar på tillstånd i formatet | ψ ⟩ = Σi √ Pi | i ⟩ | garbagei ⟩ som anges av en Vector of koefficienter {PI}. Tillstånd för detta formulär kan minskas till blandade tillstånd ρ ≔ Pi | i ⟩ ⟨ i | genom att spåra "skräp"-registret (det vill säga ett blandat läge som är diagonalt i beräknings basen).

Se https://arxiv.org/pdf/1805.03662.pdf?page=15 för ytterligare diskussion.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Description

Använder den Quantum-ROM-teknik som representerar en specifik densitet, som returnerar denna representation som en åtgärd för förberedelse av tillstånd.

I synnerhet en lista över $N $ koefficienter $ \ alpha_j $, den här funktionen returnerar en åtgärd som använder en Quantum-ROM-teknik för att förbereda en uppskattning $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ av det blandade tillstånd $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ där varje $p _j $ är en approximation till den aktuella koefficienten $ \ alpha_j $, t. ex. $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ för varje $j $.

När du godkände ett index register och ett register över skräp qubits från början i tillstånd $ \ket {0} \ket{00\cdots 0} förbereder den returnerade åtgärden båda registren i reningen av $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, så att återställning och avallokerar skräp registreringen fungerar som den önskade förberedelsen i mål felet $ \epsilon $.

## <a name="input"></a>Indata

### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mål felet $ \epsilon $.


### <a name="coefficients--double"></a>koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

Matris med $N $-koefficienter som anger sannolikheten för bas tillstånd.
Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Utdata: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

En åtgärd som förbereder $ \tilde \rho $ som en rening på ett gemensamt index och skräp registrering.

## <a name="example"></a>Exempel

Följande kodfragment förbereder en rening av $3 $-qubit State $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, där $ \vec\alpha = (1,0, 2,0, 3,0, 4,0, 5,0) $ och mål felet är $10 ^ {-3} $:

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>Kommentarer

De koefficienter som anges för den här åtgärden är normaliserade efter 1 – normal, så att koefficienterna alltid anses som beskriver en giltig kategoriska-sannolikhets fördelning.

## <a name="references"></a>Referenser

- Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. preparation. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)