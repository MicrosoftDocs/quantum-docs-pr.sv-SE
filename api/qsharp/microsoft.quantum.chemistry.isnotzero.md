---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: Funktionen IsNotZero
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839603"
---
# <a name="isnotzero-function"></a><span data-ttu-id="6cf0f-102">Funktionen IsNotZero</span><span class="sxs-lookup"><span data-stu-id="6cf0f-102">IsNotZero function</span></span>

<span data-ttu-id="6cf0f-103">Namnrymd: [Microsoft. Quantum. kemi](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6cf0f-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="6cf0f-104">Paket: [Microsoft. Quantum. kemi](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6cf0f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6cf0f-105">Kontrollerar om ett `Double` tal inte är ungefär noll.</span><span class="sxs-lookup"><span data-stu-id="6cf0f-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6cf0f-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6cf0f-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="6cf0f-107">nummer: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6cf0f-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6cf0f-108">Antal som ska kontrol leras</span><span class="sxs-lookup"><span data-stu-id="6cf0f-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="6cf0f-109">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6cf0f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6cf0f-110">Returnerar true om `number` har ett absolut värde som är större än `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="6cf0f-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>