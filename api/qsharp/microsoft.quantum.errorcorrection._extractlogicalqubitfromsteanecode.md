---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727153"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="34f41-102">_ExtractLogicalQubitFromSteaneCode åtgärd</span><span class="sxs-lookup"><span data-stu-id="34f41-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="34f41-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="34f41-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="34f41-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="34f41-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="34f41-105">Syndrome mått och inversen av inbäddning.</span><span class="sxs-lookup"><span data-stu-id="34f41-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="34f41-106">$X $-och $Z $-stabilisatorer behandlas inte lika, vilket beror på det särskilda valet av kodnings kretsen.</span><span class="sxs-lookup"><span data-stu-id="34f41-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="34f41-107">Den här asymmetry leder till en annan Syndrome extraherings rutin.</span><span class="sxs-lookup"><span data-stu-id="34f41-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="34f41-108">En kan mäta Syndrome genom att mäta Pauli-operatorn för flera qubit direkt i kod staten, men för destillations ändamål returneras den logiska qubit till en enda qubit, i vilken Syndrome mätningar kan göras utan ytterligare ancillas.</span><span class="sxs-lookup"><span data-stu-id="34f41-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="34f41-109">Indata</span><span class="sxs-lookup"><span data-stu-id="34f41-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="34f41-110">kod: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="34f41-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="34f41-111">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="34f41-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="34f41-112">Det logiska qubit och ett par med heltal för $X $-Syndrome och $Z $-syndrome.</span><span class="sxs-lookup"><span data-stu-id="34f41-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="34f41-113">De representerar index för koden qubit som en enskild $X $-eller $Z $-Error skulle ha orsakat den uppmätta syndrome.</span><span class="sxs-lookup"><span data-stu-id="34f41-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="34f41-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="34f41-114">Remarks</span></span>

<span data-ttu-id="34f41-115">Observera att den här åtgärden inte har marker ATS som `internal` enhets test direkt beroende av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="34f41-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="34f41-116">Som en framtida förbättring bör enhets test omplaneras till enbart beroende på offentliga callables direkt.</span><span class="sxs-lookup"><span data-stu-id="34f41-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="34f41-117">Den här rutinen är anpassad till en viss kodnings krets för Steane 7 qubit-kod; om kodnings kretsen ändras kanske Syndrome-resultatet måste tolkas annorlunda.</span><span class="sxs-lookup"><span data-stu-id="34f41-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>