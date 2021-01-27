---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: Funktionen QuantumROMQubitCount
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856799"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="484be-102">Funktionen QuantumROMQubitCount</span><span class="sxs-lookup"><span data-stu-id="484be-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="484be-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="484be-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="484be-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="484be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="484be-105">QuantumROMQubitCount är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="484be-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="484be-106">Använd <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> i stället.</span><span class="sxs-lookup"><span data-stu-id="484be-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="484be-107">Returnerar det totala antalet qubits som måste allokeras till den åtgärd som returnerades av `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="484be-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="484be-108">Indata</span><span class="sxs-lookup"><span data-stu-id="484be-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="484be-109">targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="484be-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="484be-110">Mål felet $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="484be-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="484be-111">nCoeffs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="484be-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="484be-112">Antalet koefficienter som anges i `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="484be-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="484be-113">Utdata: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="484be-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="484be-114">Första parametern</span><span class="sxs-lookup"><span data-stu-id="484be-114">First parameter</span></span>

<span data-ttu-id="484be-115">En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.</span><span class="sxs-lookup"><span data-stu-id="484be-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>