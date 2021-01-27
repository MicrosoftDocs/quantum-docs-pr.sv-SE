---
uid: Microsoft.Quantum.Synthesis.Extended
title: Utökad funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855479"
---
# <a name="extended-function"></a><span data-ttu-id="6acee-102">Utökad funktion</span><span class="sxs-lookup"><span data-stu-id="6acee-102">Extended function</span></span>

<span data-ttu-id="6acee-103">Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6acee-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6acee-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6acee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6acee-105">Utökar ett spektrum med inverterade koefficienter</span><span class="sxs-lookup"><span data-stu-id="6acee-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="6acee-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6acee-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="6acee-107">spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6acee-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6acee-108">Spectral-koefficienter</span><span class="sxs-lookup"><span data-stu-id="6acee-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="6acee-109">Utdata: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6acee-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6acee-110">Koefficienter följt av inverterad kopia</span><span class="sxs-lookup"><span data-stu-id="6acee-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="6acee-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="6acee-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```