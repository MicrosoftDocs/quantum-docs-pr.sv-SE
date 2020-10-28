---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726994"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="b2fa3-102">SteaneCodeEncoderImpl-åtgärd</span><span class="sxs-lookup"><span data-stu-id="b2fa3-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="b2fa3-103">Namnrymd: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="b2fa3-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="b2fa3-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2fa3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2fa3-105">Privat åtgärd som används för att implementera både Steane-kod och avkodare.</span><span class="sxs-lookup"><span data-stu-id="b2fa3-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b2fa3-106">Indata</span><span class="sxs-lookup"><span data-stu-id="b2fa3-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="b2fa3-107">data: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2fa3-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2fa3-108">en matris som innehåller 1 qubit som är indatamängds qubit.</span><span class="sxs-lookup"><span data-stu-id="b2fa3-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="b2fa3-109">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2fa3-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2fa3-110">en matris som innehåller 6 qubits som lägger till redundans.</span><span class="sxs-lookup"><span data-stu-id="b2fa3-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2fa3-111">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2fa3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

