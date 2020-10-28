---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Funktionen IsNotZero
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728125"
---
# <a name="isnotzero-function"></a><span data-ttu-id="24d41-102">Funktionen IsNotZero</span><span class="sxs-lookup"><span data-stu-id="24d41-102">IsNotZero function</span></span>

<span data-ttu-id="24d41-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="24d41-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="24d41-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="24d41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="24d41-105">Kontrollerar om ett `Double` tal inte är ungefär noll.</span><span class="sxs-lookup"><span data-stu-id="24d41-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="24d41-106">Indata</span><span class="sxs-lookup"><span data-stu-id="24d41-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="24d41-107">nummer: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="24d41-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="24d41-108">Antal som ska kontrol leras</span><span class="sxs-lookup"><span data-stu-id="24d41-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="24d41-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="24d41-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="24d41-110">Returnerar true om `number` har ett absolut värde som är större än `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="24d41-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>