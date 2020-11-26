---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: Funktionen SteaneCodeRecoveryX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200378"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="6c0e4-102">Funktionen SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="6c0e4-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="6c0e4-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6c0e4-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6c0e4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6c0e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6c0e4-105">Avkodare för X-delen av stabiliserings gruppen i ⟦ 7, 1, 3 ⟧ Steane Quantum Code.</span><span class="sxs-lookup"><span data-stu-id="6c0e4-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="6c0e4-106">Indata</span><span class="sxs-lookup"><span data-stu-id="6c0e4-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="6c0e4-107">Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="6c0e4-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="6c0e4-108">En Syndrome-matris som erhålls från att mäta stabiliseraren X-del.</span><span class="sxs-lookup"><span data-stu-id="6c0e4-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="6c0e4-109">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="6c0e4-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="6c0e4-110">En matris med Pauli-åtgärder som, när de tillämpas på det kodade Quantum-systemet, korrigerar det fel som motsvarar `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="6c0e4-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c0e4-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="6c0e4-111">Remarks</span></span>

<span data-ttu-id="6c0e4-112">Den valda avkodaren använder CSS-egenskapen för ⟦ 7, 1, 3 ⟧ Steane kod, dvs. den korrigerar X-fel och Z-fel separat.</span><span class="sxs-lookup"><span data-stu-id="6c0e4-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="6c0e4-113">En egenskap i koden är att platsen för X, Z-korrigeringen som ska tillämpas är 3D-kodningen för X respektive Z-Syndrome när det betraktas som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="6c0e4-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="6c0e4-114">Referenser</span><span class="sxs-lookup"><span data-stu-id="6c0e4-114">References</span></span>

- <span data-ttu-id="6c0e4-115">D.</span><span class="sxs-lookup"><span data-stu-id="6c0e4-115">D.</span></span> <span data-ttu-id="6c0e4-116">Gottesman, "stabiliserings koder och Quantum Error Correction", Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="6c0e4-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="6c0e4-117">Se även</span><span class="sxs-lookup"><span data-stu-id="6c0e4-117">See Also</span></span>

- [<span data-ttu-id="6c0e4-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="6c0e4-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="6c0e4-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="6c0e4-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)