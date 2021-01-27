---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Funktionen FiveQubitCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853145"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="0d2fa-102">Funktionen FiveQubitCode</span><span class="sxs-lookup"><span data-stu-id="0d2fa-102">FiveQubitCode function</span></span>

<span data-ttu-id="0d2fa-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0d2fa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0d2fa-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d2fa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d2fa-105">Returnerar ett QECC-värde som representerar ⟦ 5, 1, 3 ⟧ kod kodare och avkodare med Syndrome på plats.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="0d2fa-106">Utdata: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="0d2fa-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="0d2fa-107">Returnerar en implementering av en Quantum-fel korrigerings kod genom att ange en `QECC` typ.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d2fa-108">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="0d2fa-108">Remarks</span></span>

<span data-ttu-id="0d2fa-109">Den här koden hittades oberoende av följande två dokument:</span><span class="sxs-lookup"><span data-stu-id="0d2fa-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="0d2fa-110">C.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-110">C.</span></span> <span data-ttu-id="0d2fa-111">&.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-111">H.</span></span> <span data-ttu-id="0d2fa-112">Bennett, D. DiVincenzo, J. A.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="0d2fa-113">Smolin och W. K.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-113">Smolin and W. K.</span></span> <span data-ttu-id="0d2fa-114">Wootters, "blandat läge entanglement och Quantum Error Correction", inventering. Rev. A, 54 (1996) s. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 och</span><span class="sxs-lookup"><span data-stu-id="0d2fa-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="0d2fa-115">R.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-115">R.</span></span> <span data-ttu-id="0d2fa-116">Laflamme, C. Miquel, J. P.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="0d2fa-117">Paz och W. H.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-117">Paz and W. H.</span></span> <span data-ttu-id="0d2fa-118">Zurek, "fel korrigerings kod för perfekt Quantum", "inventering. Rev. lett.</span><span class="sxs-lookup"><span data-stu-id="0d2fa-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="0d2fa-119">77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="0d2fa-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>