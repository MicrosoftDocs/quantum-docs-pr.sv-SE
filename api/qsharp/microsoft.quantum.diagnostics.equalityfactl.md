---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: Funktionen EqualityFactL
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727237"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="28dff-102">Funktionen EqualityFactL</span><span class="sxs-lookup"><span data-stu-id="28dff-102">EqualityFactL function</span></span>

<span data-ttu-id="28dff-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="28dff-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="28dff-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28dff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28dff-105">Förutsätter att en klassisk BigInt-variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="28dff-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="28dff-106">Indata</span><span class="sxs-lookup"><span data-stu-id="28dff-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="28dff-107">faktiskt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="28dff-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="28dff-108">Det tal som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="28dff-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="28dff-109">förväntat: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="28dff-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="28dff-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="28dff-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="28dff-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="28dff-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="28dff-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="28dff-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28dff-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28dff-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

