---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193632"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="72a0a-102">PrepareSingleQubitIdentity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="72a0a-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="72a0a-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="72a0a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="72a0a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72a0a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72a0a-105">Förbereder en qubit i blandat läge för maximally.</span><span class="sxs-lookup"><span data-stu-id="72a0a-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="72a0a-106">Den förbereder den aktuella qubit i läget $ \boldone/$2 genom att använda depolarisering Channel $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ WHERE $ \sigma \_ i $ är den $i $ th Pauli-operatorn och där $ \rho $ är en densitet som representerar ett blandat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="72a0a-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="72a0a-107">Indata</span><span class="sxs-lookup"><span data-stu-id="72a0a-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="72a0a-108">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72a0a-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72a0a-109">En qubit vars tillstånd ska avsättas på det sätt som beskrivs ovan.</span><span class="sxs-lookup"><span data-stu-id="72a0a-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72a0a-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72a0a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="72a0a-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="72a0a-111">Remarks</span></span>

<span data-ttu-id="72a0a-112">Det blandade State $ \boldone/$2 som beskriver resultatet av att tillämpa den här åtgärden på ett tillstånd beskriver implicit ett förväntat värde över slumpmässiga val som gjorts i den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="72a0a-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="72a0a-113">För alla enskilda program mappar den här åtgärden rent tillstånd till rent tillstånd, men den fungerar enligt beskrivningen i förväntan.</span><span class="sxs-lookup"><span data-stu-id="72a0a-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="72a0a-114">I synnerhet kan den här åtgärden användas i process-tomography för att mäta *icke-enhetens* komponenter i en kanal.</span><span class="sxs-lookup"><span data-stu-id="72a0a-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>