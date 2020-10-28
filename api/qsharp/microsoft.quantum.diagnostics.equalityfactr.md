---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Funktionen EqualityFactR
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 2b293dc581ed58f7e3864a952fb3ecafa68e759c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727231"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="1f05b-102">Funktionen EqualityFactR</span><span class="sxs-lookup"><span data-stu-id="1f05b-102">EqualityFactR function</span></span>

<span data-ttu-id="1f05b-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1f05b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1f05b-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f05b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f05b-105">Förutsätter att en klassisk resultat variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="1f05b-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1f05b-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1f05b-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="1f05b-107">faktiskt: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="1f05b-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="1f05b-108">Den variabel som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="1f05b-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="1f05b-109">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="1f05b-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="1f05b-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="1f05b-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1f05b-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1f05b-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1f05b-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="1f05b-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1f05b-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f05b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

