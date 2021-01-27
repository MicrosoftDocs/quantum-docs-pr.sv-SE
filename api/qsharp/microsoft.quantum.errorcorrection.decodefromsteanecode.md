---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827390"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="3ad45-102">DecodeFromSteaneCode-åtgärd</span><span class="sxs-lookup"><span data-stu-id="3ad45-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="3ad45-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="3ad45-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="3ad45-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ad45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ad45-105">En inverterad kodnings åtgärd som mappar ett kodat Quantum-register till en kodad Quantum-register under ⟦ 7, 1, 3 ⟧ Steane Quantum Code.</span><span class="sxs-lookup"><span data-stu-id="3ad45-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="3ad45-106">Indata</span><span class="sxs-lookup"><span data-stu-id="3ad45-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="3ad45-107">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="3ad45-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="3ad45-108">En matris med qubits som representerar det logiska tillstånd för kodade 5 qubit-kod.</span><span class="sxs-lookup"><span data-stu-id="3ad45-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="3ad45-109">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="3ad45-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="3ad45-110">En qubit-matris med längden 1 som representerar det avkodade läget i den första parametern, tillsammans med hjälp qubits i den andra parametern.</span><span class="sxs-lookup"><span data-stu-id="3ad45-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="3ad45-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="3ad45-111">Remarks</span></span>

<span data-ttu-id="3ad45-112">Den valda avkodaren använder CSS-egenskapen för ⟦ 7, 1, 3 ⟧ Steane kod, dvs. den korrigerar X-fel och Z-fel separat.</span><span class="sxs-lookup"><span data-stu-id="3ad45-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="3ad45-113">En egenskap i koden är att platsen för X, Z-korrigeringen som ska tillämpas är 3D-kodningen för X respektive Z-Syndrome när det betraktas som ett heltal.</span><span class="sxs-lookup"><span data-stu-id="3ad45-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="3ad45-114">Referenser</span><span class="sxs-lookup"><span data-stu-id="3ad45-114">References</span></span>

- <span data-ttu-id="3ad45-115">D.</span><span class="sxs-lookup"><span data-stu-id="3ad45-115">D.</span></span> <span data-ttu-id="3ad45-116">Gottesman, "stabiliserings koder och Quantum Error Correction", Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="3ad45-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="3ad45-117">Se även</span><span class="sxs-lookup"><span data-stu-id="3ad45-117">See Also</span></span>

- [<span data-ttu-id="3ad45-118">Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="3ad45-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="3ad45-119">Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="3ad45-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="3ad45-120">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="3ad45-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)