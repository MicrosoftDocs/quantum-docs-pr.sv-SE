---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92729694"
---
# <a name="applyccnotchain-operation"></a><span data-ttu-id="ce12b-102">ApplyCCNOTChain-åtgärd</span><span class="sxs-lookup"><span data-stu-id="ce12b-102">ApplyCCNOTChain operation</span></span>

<span data-ttu-id="ce12b-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ce12b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ce12b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ce12b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ce12b-105">Implementerar en överlappande av CCNOT-grindar som styrs på motsvarande bitar av två qubit-register, och fungerar på nästa qubit i en av registren.</span><span class="sxs-lookup"><span data-stu-id="ce12b-105">Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers.</span></span>
<span data-ttu-id="ce12b-106">Från qubits vid position 0 i båda registren register som kontroller, tillämpas CCNOT på qubit vid position 1 i mål registret, och styrs sedan av qubits vid position 1 på qubit vid position 2 i mål registret, osv., som avslutas med en åtgärd på mål qubit i position `Length(nQubits)-1` .</span><span class="sxs-lookup"><span data-stu-id="ce12b-106">Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.</span></span>

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ce12b-107">Indata</span><span class="sxs-lookup"><span data-stu-id="ce12b-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="ce12b-108">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce12b-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce12b-109">Qubit-registrering, används endast för kontroller.</span><span class="sxs-lookup"><span data-stu-id="ce12b-109">Qubit register, only used for controls.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="ce12b-110">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ce12b-110">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ce12b-111">Qubit-register som används för kontroller och som mål.</span><span class="sxs-lookup"><span data-stu-id="ce12b-111">Qubit register, used for controls and as target.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ce12b-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ce12b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ce12b-113">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="ce12b-113">Remarks</span></span>

<span data-ttu-id="ce12b-114">Mål qubit-registret måste ha en qubit över det andra registret.</span><span class="sxs-lookup"><span data-stu-id="ce12b-114">The target qubit register must have one qubit more than the other register.</span></span>