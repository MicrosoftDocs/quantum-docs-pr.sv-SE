---
uid: Microsoft.Quantum.Arithmetic.CompareGTSI
title: CompareGTSI-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGTSI
qsharp.summary: 'Wrapper for signed integer comparison: `result = xs > ys`.'
ms.openlocfilehash: f725bdbaa945a4f87e90fc71930c37642113c21a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846698"
---
# <a name="comparegtsi-operation"></a><span data-ttu-id="7ecd5-102">CompareGTSI-åtgärd</span><span class="sxs-lookup"><span data-stu-id="7ecd5-102">CompareGTSI operation</span></span>

<span data-ttu-id="7ecd5-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7ecd5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7ecd5-104">Paket: [Microsoft. Quantum. numeric](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="7ecd5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="7ecd5-105">Omslutning för signerad heltals jämförelse: `result = xs > ys` .</span><span class="sxs-lookup"><span data-stu-id="7ecd5-105">Wrapper for signed integer comparison: `result = xs > ys`.</span></span>

```qsharp
operation CompareGTSI (xs : Microsoft.Quantum.Arithmetic.SignedLittleEndian, ys : Microsoft.Quantum.Arithmetic.SignedLittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7ecd5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="7ecd5-106">Input</span></span>

### <a name="xs--signedlittleendian"></a><span data-ttu-id="7ecd5-107">XS: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7ecd5-107">xs : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7ecd5-108">Första $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="7ecd5-108">First $n$-bit number</span></span>


### <a name="ys--signedlittleendian"></a><span data-ttu-id="7ecd5-109">gar: [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7ecd5-109">ys : [SignedLittleEndian](xref:Microsoft.Quantum.Arithmetic.SignedLittleEndian)</span></span>

<span data-ttu-id="7ecd5-110">Andra $n $-bit Number</span><span class="sxs-lookup"><span data-stu-id="7ecd5-110">Second $n$-bit number</span></span>


### <a name="result--qubit"></a><span data-ttu-id="7ecd5-111">resultat: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="7ecd5-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="7ecd5-112">Kommer att vändas om $xs > gar $</span><span class="sxs-lookup"><span data-stu-id="7ecd5-112">Will be flipped if $xs > ys$</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ecd5-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ecd5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

