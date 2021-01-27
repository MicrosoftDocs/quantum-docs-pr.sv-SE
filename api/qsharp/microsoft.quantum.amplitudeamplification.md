---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Namn område för Microsoft. Quantum. AmplitudeAmplification
ms.date: 1/23/2021 12:00:00 AM
ms.topic: managed-reference
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: a014f923de62c5e660c1c0fc839fbe60e80f8ba9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845837"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Namn område för Microsoft. Quantum. AmplitudeAmplification

Det här namn området innehåller funktioner och åtgärder för att utföra amplitud-förstärkning.



## <a name="description"></a>Description

Oblivious amplitud-förstärkning med partiella reflektioner är den mest generella formen av amplitud-förstärkning som implementeras här.

Detta anropas via åtgärden AmpAmpObliviousByReflectionPhases.

Detta har två register: `ancillaRegister` och `systemRegister` .

Detta godkänner två Oracle för dessa reflektioner av typen `ReflectionOracle` som bara agerar i `ancillaRegister` registret.

Detta godkänner en Oracle-specifik till Oblivious amplitud-förstärkning av typ `ObliviousOracle` som fungerar tillsammans i båda registren.

Indatamängden `ancillaRegister` antas vara den unika $-$1-eigenstate för den första reflektions operatorn $I-2 \ ket {s} \ bra {s} $.

Reflektioner om ett mål Quantum-tillstånd implementeras ofta genom att man antar åtkomst till en Oracle som förbereder detta tillstånd från beräknings basen $ \ket{0\cdots 0} $.

Vår konvention för dessa Oracle kräver två register: en enda-qubit- `flagQubit` registrering och ett register för allt annat i ancillaRegister-registret.

Oracle-typen `StateOracle` agerar gemensamt på båda registren för att skapa mål tillstånd som flaggats av $ \ket {1} $ i `flagQubit` registret med en riktig amplitud.

Reflektionen `ReflectionOracle` om det här flagg läget genereras av åtgärden `TargetStateReflectionOracle` .

Reflektionen `ReflectionOracle` om ingångs läget som `ancillaRegister` genereras av StateOracle inverteras och sedan återspeglar ungefär $ \ket{0\cdots 0} $ med ReflectionStart ().

Oracle-typen `DeterministicStateOracle` agerar i `qubitState` registren för att skapa mål tillstånd exakt utan flagga.

`AmpAmpObliviousByOraclePhases` är en version av Oblivious amplitud-förstärkning som accepterar Oracle `StateOracle` och `ObliviousOracle` i stället för reflexer.

Observera att amplitud förstärkning är ett specialfall av Oblivious amplitud-förstärkning där `ObliviousOracle` är identitets operatorn, och det finns inga system-qubits, d.v.s. `systemRegister` tomt.

Detta anropas genom åtgärden `AmpAmByReflectionPhases` och `AmpAmpByOraclePhases` .

Faserna för partiella reflektioner i standard fallet för Grover-sökning tillhandahålls av funktionen AmpAmpPhasesStandard.

Vi har till exempel följande beroenden: AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.