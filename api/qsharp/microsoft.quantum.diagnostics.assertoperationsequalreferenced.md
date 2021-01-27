---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853471"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced-åtgärd

Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Två åtgärder förutsätter att de fungerar identiskt för alla ingångs tillstånd.

Den här kontrollen implementeras med hjälp av Choi – Jamiołkowski-isomorphism för att minska försäkran till en qubit-tillstånds kontroll på två Entangled-register.
Den här åtgärden behöver därför bara ett enda anrop till varje åtgärd som testas, men kräver två gånger så många qubits som ska allokeras.
Denna kontroll kan användas för att se till att en optimerad version av en åtgärd fungerar identiskt med dess naïve-implementering, eller att en åtgärd som agerar på ett intervall av icke-Quantum-indata accepterar kända fall.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Indata

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Antalet qubits som ska skickas till varje åtgärd.


### <a name="actual--qubit--unit"></a>faktiskt: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit) 

Åtgärd som ska testas.


### <a name="expected--qubit--unit--is-adj"></a>förväntat: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = just> [enhet](xref:microsoft.quantum.lang-ref.unit)

Åtgärd som definierar det förväntade beteendet för åtgärden under test.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Kommentarer

Den här åtgärden kräver att den förväntade åtgärden är adjointable, så att inversen kan utföras i själva mål registret.
Formellt, en kan ange en transponering-åtgärd, vilket innebär att detta krav uppfylls, men transponering-åtgärden är inte i allmänt fysiskt realizable för valfria Quantum-åtgärder och ingår därför inte här som ett alternativ.