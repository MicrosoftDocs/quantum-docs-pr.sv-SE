---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850058"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="cf867-102">SyndromeMeasOp-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="cf867-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="cf867-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="cf867-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="cf867-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf867-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cf867-105">Representerar en åtgärd som används för att mäta Syndrome för ett felkorrigerande kod block.</span><span class="sxs-lookup"><span data-stu-id="cf867-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="cf867-106">Exempel</span><span class="sxs-lookup"><span data-stu-id="cf867-106">Example</span></span>

<span data-ttu-id="cf867-107">Mät syndromes för bit-flip-koden $S = \langle ZZI, IZZ \rangle $ med Scratch qubits i ett icke-feltolerant sätt:</span><span class="sxs-lookup"><span data-stu-id="cf867-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="cf867-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="cf867-108">Remarks</span></span>

<span data-ttu-id="cf867-109">Signaturen `(LogicalRegister => Syndrome)` representerar en åtgärd som agerar gemensamt på qubits i `LogicalRegister` och vissa hjälp qubits följt av en mätning av hjälp qubits för att extrahera ett `Syndrome` värde som representerar `Result[]` dessa mått.</span><span class="sxs-lookup"><span data-stu-id="cf867-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf867-110">Se även</span><span class="sxs-lookup"><span data-stu-id="cf867-110">See Also</span></span>

- [<span data-ttu-id="cf867-111">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="cf867-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="cf867-112">Microsoft. Quantum. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="cf867-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)