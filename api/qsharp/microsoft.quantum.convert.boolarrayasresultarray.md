---
uid: Microsoft.Quantum.Convert.BoolArrayAsResultArray
title: Funktionen BoolArrayAsResultArray
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsResultArray
qsharp.summary: Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.
ms.openlocfilehash: 388fb67ba33810fc813fb646577bfa7f4a2b51ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224470"
---
# <a name="boolarrayasresultarray-function"></a><span data-ttu-id="13613-102">Funktionen BoolArrayAsResultArray</span><span class="sxs-lookup"><span data-stu-id="13613-102">BoolArrayAsResultArray function</span></span>

<span data-ttu-id="13613-103">Namnrymd: [Microsoft. Quantum. convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="13613-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="13613-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13613-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13613-105">Konverterar en `Bool[]` typ till en `Result[]` typ, där `true` mappas till `One` och `false` mappas till `Zero` .</span><span class="sxs-lookup"><span data-stu-id="13613-105">Converts a `Bool[]` type to a `Result[]` type, where `true` is mapped to `One` and `false` is mapped to `Zero`.</span></span>

```qsharp
function BoolArrayAsResultArray (input : Bool[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="13613-106">Indata</span><span class="sxs-lookup"><span data-stu-id="13613-106">Input</span></span>

### <a name="input--bool"></a><span data-ttu-id="13613-107">Indatatyp: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="13613-107">input : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="13613-108">`Bool[]` som ska konverteras.</span><span class="sxs-lookup"><span data-stu-id="13613-108">`Bool[]` to be converted.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="13613-109">Utdata: __ogiltigt <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="13613-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="13613-110">En `Result[]` som representerar `input` .</span><span class="sxs-lookup"><span data-stu-id="13613-110">A `Result[]` representing the `input`.</span></span>