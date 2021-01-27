---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Funktionen EqualityFactR
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853333"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="26d93-102">Funktionen EqualityFactR</span><span class="sxs-lookup"><span data-stu-id="26d93-102">EqualityFactR function</span></span>

<span data-ttu-id="26d93-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="26d93-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="26d93-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26d93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26d93-105">Förutsätter att en klassisk resultat variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="26d93-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="26d93-106">Indata</span><span class="sxs-lookup"><span data-stu-id="26d93-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="26d93-107">faktiskt: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="26d93-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="26d93-108">Den variabel som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="26d93-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="26d93-109">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="26d93-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="26d93-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="26d93-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="26d93-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="26d93-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="26d93-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="26d93-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26d93-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26d93-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

