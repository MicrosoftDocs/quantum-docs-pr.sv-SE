---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842005"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="5eee2-102">ApplyAndChain-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5eee2-102">ApplyAndChain operation</span></span>

<span data-ttu-id="5eee2-103">Namnrymd: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5eee2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5eee2-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5eee2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5eee2-105">Beräknar en kedja av och portar</span><span class="sxs-lookup"><span data-stu-id="5eee2-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="5eee2-106">Description</span><span class="sxs-lookup"><span data-stu-id="5eee2-106">Description</span></span>

<span data-ttu-id="5eee2-107">Hjälp-qubits för att beräkna temporära resultat måste anges explicit.</span><span class="sxs-lookup"><span data-stu-id="5eee2-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="5eee2-108">Längden på registreringen är `Length(ctrlRegister) - 2` , om det finns minst två kontroller, annars är längden 0.</span><span class="sxs-lookup"><span data-stu-id="5eee2-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="5eee2-109">Indata</span><span class="sxs-lookup"><span data-stu-id="5eee2-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="5eee2-110">auxRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5eee2-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="5eee2-111">ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5eee2-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="5eee2-112">mål: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5eee2-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="5eee2-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5eee2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

