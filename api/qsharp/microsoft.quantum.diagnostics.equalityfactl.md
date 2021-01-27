---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: Funktionen EqualityFactL
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829148"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="a664a-102">Funktionen EqualityFactL</span><span class="sxs-lookup"><span data-stu-id="a664a-102">EqualityFactL function</span></span>

<span data-ttu-id="a664a-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a664a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a664a-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a664a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a664a-105">Förutsätter att en klassisk BigInt-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="a664a-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a664a-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a664a-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="a664a-107">faktiskt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a664a-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a664a-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="a664a-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="a664a-109">förväntat: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a664a-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="a664a-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="a664a-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="a664a-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a664a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a664a-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="a664a-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a664a-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a664a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

