---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: Funktionen TargetStateReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: 65ad316a6ac986ebd0dc28b25859026a60aa3239
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191116"
---
# <a name="targetstatereflectionoracle-function"></a><span data-ttu-id="f3d0b-102">Funktionen TargetStateReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="f3d0b-102">TargetStateReflectionOracle function</span></span>

<span data-ttu-id="f3d0b-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="f3d0b-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3d0b-105">Skapar en `ReflectionOracle` om mål tillstånd som har marker ATS unikt av flaggan qubit.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-105">Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.</span></span>

<span data-ttu-id="f3d0b-106">Mål status har en enda qubit inställd på 1, och alla andra 0: $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-106">The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.</span></span>

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a><span data-ttu-id="f3d0b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="f3d0b-107">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="f3d0b-108">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-108">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f3d0b-109">Index för att flagga qubit $f $ för Oracle.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-109">Index to flag qubit $f$ of oracle.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="f3d0b-110">Utdata: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="f3d0b-110">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="f3d0b-111">En `ReflectionOracle` som visar om det tillstånd som har marker ATS med $ \ket {1} _F $.</span><span class="sxs-lookup"><span data-stu-id="f3d0b-111">A `ReflectionOracle` that reflects about the state marked by $\ket{1}_f$.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3d0b-112">Se även</span><span class="sxs-lookup"><span data-stu-id="f3d0b-112">See Also</span></span>

- [<span data-ttu-id="f3d0b-113">Microsoft. Quantum. Canon. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="f3d0b-113">Microsoft.Quantum.Canon.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Canon.ReflectionOracle)