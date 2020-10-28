---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732651"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="8ea5a-102">PrepareQubit-åtgärd</span><span class="sxs-lookup"><span data-stu-id="8ea5a-102">PrepareQubit operation</span></span>

<span data-ttu-id="8ea5a-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8ea5a-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8ea5a-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8ea5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8ea5a-105">Förbereder en qubit i eigenstate + 1 ( `Zero` ) för den aktuella Pauli-operatorn.</span><span class="sxs-lookup"><span data-stu-id="8ea5a-105">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="8ea5a-106">Om identitets operatören anges förbereds qubit i blandat läge för maximally.</span><span class="sxs-lookup"><span data-stu-id="8ea5a-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="8ea5a-107">Om qubit inlednings vis i $ \ket {0} $-tillstånd, förbereder den här åtgärden qubit i $ + $1-eigenstate för en specifik Pauli-operatör, eller, för `PauliI` , i maximally blandat tillstånd i stället (se <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="8ea5a-107">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="8ea5a-108">Om qubit har varit i ett annat tillstånd än $ \ket {0} $, tillämpar den här åtgärden följande portar: $H $ för `PauliX` , $HS $ för `PauliY` , $I $ för `PauliZ` och <xref:microsoft.quantum.preparation.preparesinglequbitidentity> `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="8ea5a-108">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8ea5a-109">Indata</span><span class="sxs-lookup"><span data-stu-id="8ea5a-109">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="8ea5a-110">grund: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8ea5a-110">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8ea5a-111">En Pauli-operatör $P $.</span><span class="sxs-lookup"><span data-stu-id="8ea5a-111">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="8ea5a-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ea5a-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ea5a-113">En qubit som ska förberedas.</span><span class="sxs-lookup"><span data-stu-id="8ea5a-113">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ea5a-114">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ea5a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

