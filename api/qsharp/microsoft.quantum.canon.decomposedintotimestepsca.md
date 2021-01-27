---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: Funktionen DecomposedIntoTimeStepsCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: e82df36d2e4f3767a152d5c92d7b1897c744a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840693"
---
# <a name="decomposedintotimestepsca-function"></a>Funktionen DecomposedIntoTimeStepsCA

Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Returnerar en åtgärd som implementerar Trotter – Suzuki Integrator för en specifik åtgärd.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Indata

### <a name="nsteps--int"></a>nSteps: [int](xref:microsoft.quantum.lang-ref.int)

Antalet åtgärder som ska avgränsas i tids stegen.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>OP: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

En åtgärd som accepterar en index Indatatyp (typ `Int` ) och en tids Indatatyp (typ `Double` ) för dekomposition.


### <a name="trotterorder--int"></a>trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)

Väljer den ordning för Trotter – Suzuki Integrator som ska användas.
Order 1 och till och med order 2, 4, 6,... stöds för närvarande.



## <a name="output--doublet--unit--is-adj--ctl"></a>Utdata: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [enhet](xref:microsoft.quantum.lang-ref.unit)  är just + CTL

Returnerar en enhetlig implementering av Trotter – Suzuki Integrator, där den första parametern `Double` är integrations steg storleken, och den andra parametern är den som har agerat.

## <a name="type-parameters"></a>Typparametrar

### <a name="t"></a>Inte

Typen som varje tidpunkt ska agera på. normalt, antingen `Qubit[]` eller `Qubit` .

## <a name="remarks"></a>Kommentarer

När `order` den här funktionen anropas med samma som `1` , returnerar den här funktionen en åtgärd som kan simuleras av den lägsta ordningen Trotter – Suzuki Integrator $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $ där vi har följt notationen av [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) och låt $ \lambda $ vara utvecklings tiden (representeras av den returnerade åtgärdens första gång). och låt $ \{ H_j \} _ {j = 1} ^ {m} $ vara den uppsättning av dynamiska generatorer för (sned-Hermitian) som `op(j, lambda, _)` är integrerad som simuleras av den enhetliga operatorn $e ^ {H_j \lambda} $.

På samma sätt `order` returnerar en av `2` de andra ordningarna symmetrisk Trotter – Suzuki Integrator $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.
\end{align} $ $

Högre t.o.m. värden i `order` implementeras med hjälp av den rekursiva konstruktionen av [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Referenser

- [*D. W. bär, G. Ahokas, R. Cleve, B. C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)