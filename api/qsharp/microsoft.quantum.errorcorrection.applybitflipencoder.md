---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827699"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="47063-102">ApplyBitFlipEncoder-åtgärd</span><span class="sxs-lookup"><span data-stu-id="47063-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="47063-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="47063-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="47063-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47063-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47063-105">Privat åtgärd som används för att implementera både bit vända kodare och avkodare.</span><span class="sxs-lookup"><span data-stu-id="47063-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="47063-106">Observera att den här kodaren kan använda en enhetlig återställning på plats, i så fall kommer det att "orsaka" det fel som beskrivs i Start läget för `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="47063-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="47063-107">I synnerhet, om `auxQubits` är inlednings vis i tillstånd $ \ket {10} $, kommer detta att orsaka ett $X _1 $-fel på den kodade qubit.</span><span class="sxs-lookup"><span data-stu-id="47063-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="47063-108">Indata</span><span class="sxs-lookup"><span data-stu-id="47063-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="47063-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="47063-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="47063-110">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47063-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="47063-111">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="47063-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="47063-112">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="47063-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="47063-113">Referenser</span><span class="sxs-lookup"><span data-stu-id="47063-113">References</span></span>

- <span data-ttu-id="47063-114">doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="47063-114">doi:10.1103/PhysRevA.85.044302</span></span>