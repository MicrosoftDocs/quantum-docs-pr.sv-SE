---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Funktionen QuantumROMQubitCount
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 0ec1e042b9f675505f73bfcdcc6706d0bc0367df
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210411"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="e2859-102">Funktionen QuantumROMQubitCount</span><span class="sxs-lookup"><span data-stu-id="e2859-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="e2859-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e2859-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e2859-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e2859-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="e2859-105">QuantumROMQubitCount är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="e2859-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="e2859-106">Använd <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> i stället.</span><span class="sxs-lookup"><span data-stu-id="e2859-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="e2859-107">Returnerar det totala antalet qubits som måste allokeras till den åtgärd som returnerades av `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="e2859-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="e2859-108">Indata</span><span class="sxs-lookup"><span data-stu-id="e2859-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e2859-109">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e2859-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e2859-110">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="e2859-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="e2859-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e2859-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e2859-112">Antalet koefficienter som anges i `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="e2859-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="e2859-113">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="e2859-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="e2859-114">Första parametern</span><span class="sxs-lookup"><span data-stu-id="e2859-114">First parameter</span></span>

<span data-ttu-id="e2859-115">En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.</span><span class="sxs-lookup"><span data-stu-id="e2859-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>