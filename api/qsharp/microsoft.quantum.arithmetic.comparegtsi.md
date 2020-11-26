---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: a0e8ef66f1e1a62d4f6a78364135376810507534
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223501"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="5d985-102">CompareGTSI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5d985-102">CompareGTSI operation</span></span>

<span data-ttu-id="5d985-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5d985-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5d985-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="5d985-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="5d985-105">Omslutning för signerad heltals jämförelse: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="5d985-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5d985-106">Indata</span><span class="sxs-lookup"><span data-stu-id="5d985-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="5d985-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5d985-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5d985-108">Första $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="5d985-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="5d985-109">gar: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5d985-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="5d985-110">Andra $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="5d985-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="5d985-111">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5d985-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5d985-112">Kommer att vändas om $xs > gar $</span><span class="sxs-lookup"><span data-stu-id="5d985-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d985-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d985-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

