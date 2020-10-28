---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: Funktionen SteaneCodeRecoveryX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726970"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="36df5-102">Funktionen SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="36df5-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="36df5-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="36df5-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="36df5-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36df5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36df5-105">Avkodare för X-delen av stabiliserings gruppen i ⟦ 7, 1, 3 ⟧ Steane Quantum Code.</span><span class="sxs-lookup"><span data-stu-id="36df5-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="36df5-106">Indata</span><span class="sxs-lookup"><span data-stu-id="36df5-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="36df5-107">Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="36df5-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="36df5-108">En Syndrome-matris som erhålls från att mäta stabiliseraren X-del.</span><span class="sxs-lookup"><span data-stu-id="36df5-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="36df5-109">Utdata: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="36df5-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="36df5-110">En matris med Pauli-åtgärder som, när de tillämpas på det kodade Quantum-systemet, korrigerar det fel som motsvarar `syndrome` .</span><span class="sxs-lookup"><span data-stu-id="36df5-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36df5-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="36df5-111">Remarks</span></span>

<span data-ttu-id="36df5-112">Den valda avkodaren använder CSS-egenskapen för ⟦ 7, 1, 3 ⟧ Steane kod, dvs. den korrigerar X-fel och Z-fel separat.</span><span class="sxs-lookup"><span data-stu-id="36df5-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="36df5-113">En egenskap i koden är att platsen för X, Z-korrigeringen som ska tillämpas är 3D-kodningen för X respektive Z-Syndrome när det betraktas som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="36df5-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="36df5-114">Referenser</span><span class="sxs-lookup"><span data-stu-id="36df5-114">References</span></span>

- <span data-ttu-id="36df5-115">D.</span><span class="sxs-lookup"><span data-stu-id="36df5-115">D.</span></span> <span data-ttu-id="36df5-116">Gottesman, "stabiliserings koder och Quantum Error Correction", Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="36df5-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="36df5-117">Se även</span><span class="sxs-lookup"><span data-stu-id="36df5-117">See Also</span></span>

- [<span data-ttu-id="36df5-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="36df5-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="36df5-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="36df5-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)