---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: _ExtractLogicalQubitFromSteaneCode åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853218"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="90151-102">_ExtractLogicalQubitFromSteaneCode åtgärd</span><span class="sxs-lookup"><span data-stu-id="90151-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="90151-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="90151-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="90151-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90151-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90151-105">Syndrome mått och inversen av inbäddning.</span><span class="sxs-lookup"><span data-stu-id="90151-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="90151-106">$X $-och $Z $-stabilisatorer behandlas inte lika, vilket beror på det särskilda valet av kodnings kretsen.</span><span class="sxs-lookup"><span data-stu-id="90151-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="90151-107">Den här asymmetry leder till en annan Syndrome extraherings rutin.</span><span class="sxs-lookup"><span data-stu-id="90151-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="90151-108">En kan mäta Syndrome genom att mäta Pauli-operatorn för flera qubit direkt i kod staten, men för destillations ändamål returneras den logiska qubit till en enda qubit, i vilken Syndrome mätningar kan göras utan ytterligare ancillas.</span><span class="sxs-lookup"><span data-stu-id="90151-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="90151-109">Indata</span><span class="sxs-lookup"><span data-stu-id="90151-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="90151-110">kod: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="90151-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="90151-111">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit),[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="90151-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="90151-112">Det logiska qubit och ett par med heltal för $X $-Syndrome och $Z $-syndrome.</span><span class="sxs-lookup"><span data-stu-id="90151-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="90151-113">De representerar index för koden qubit som en enskild $X $-eller $Z $-Error skulle ha orsakat den uppmätta syndrome.</span><span class="sxs-lookup"><span data-stu-id="90151-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="90151-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="90151-114">Remarks</span></span>

<span data-ttu-id="90151-115">Observera att den här åtgärden inte har marker ATS som `internal` enhets test direkt beroende av den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="90151-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="90151-116">Som en framtida förbättring bör enhets test omplaneras till enbart beroende på offentliga callables direkt.</span><span class="sxs-lookup"><span data-stu-id="90151-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="90151-117">Den här rutinen är anpassad till en viss kodnings krets för Steane 7 qubit-kod; om kodnings kretsen ändras kanske Syndrome-resultatet måste tolkas annorlunda.</span><span class="sxs-lookup"><span data-stu-id="90151-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>