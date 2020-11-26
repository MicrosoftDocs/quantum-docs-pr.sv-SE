---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Funktionen IsNotZero
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204070"
---
# <a name="isnotzero-function"></a><span data-ttu-id="d5406-102">Funktionen IsNotZero</span><span class="sxs-lookup"><span data-stu-id="d5406-102">IsNotZero function</span></span>

<span data-ttu-id="d5406-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d5406-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="d5406-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="d5406-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="d5406-105">Kontrollerar om ett `Double` tal inte är ungefär noll.</span><span class="sxs-lookup"><span data-stu-id="d5406-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="d5406-106">Indata</span><span class="sxs-lookup"><span data-stu-id="d5406-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="d5406-107">nummer: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d5406-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d5406-108">Antal som ska kontrol leras</span><span class="sxs-lookup"><span data-stu-id="d5406-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="d5406-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d5406-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d5406-110">Returnerar true om `number` har ett absolut värde som är större än `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="d5406-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>