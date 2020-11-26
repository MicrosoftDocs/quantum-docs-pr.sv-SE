---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: f70d2d1352c7b2eebee7a863eba97d78d7351dab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200857"
---
# <a name="fivequbitcodeencoderimpl-operation"></a><span data-ttu-id="c16d6-102">FiveQubitCodeEncoderImpl-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c16d6-102">FiveQubitCodeEncoderImpl operation</span></span>

<span data-ttu-id="c16d6-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="c16d6-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="c16d6-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c16d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c16d6-105">Privat åtgärd som används för att implementera både 5 qubit-kodare och avkodare.</span><span class="sxs-lookup"><span data-stu-id="c16d6-105">Private operation used to implement both the 5 qubit encoder and decoder.</span></span>

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c16d6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="c16d6-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="c16d6-107">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c16d6-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c16d6-108">en matris som innehåller 1 qubit som är indatamängds qubit.</span><span class="sxs-lookup"><span data-stu-id="c16d6-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="c16d6-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c16d6-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c16d6-110">en matris som innehåller 4 qubits som lägger till redundans.</span><span class="sxs-lookup"><span data-stu-id="c16d6-110">an array holding 4 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c16d6-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c16d6-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c16d6-112">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="c16d6-112">Remarks</span></span>

<span data-ttu-id="c16d6-113">Den specifika kodare som valts togs från papper V. Kliuchnikov och D. Maslov, "optimering av Clifford-kretsar", "inventering. Rev. inventering. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figur 4b) och kräver totalt 11 grindar.</span><span class="sxs-lookup"><span data-stu-id="c16d6-113">The particular encoder chosen was taken from the paper V. Kliuchnikov and D. Maslov, "Optimization of Clifford Circuits," Phys. Rev. Phys. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figure 4b) and requires a total of 11 gates.</span></span>