---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: Funktionen EqualityFactR
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201775"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="cefe7-102">Funktionen EqualityFactR</span><span class="sxs-lookup"><span data-stu-id="cefe7-102">EqualityFactR function</span></span>

<span data-ttu-id="cefe7-103">Namnrymd: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cefe7-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cefe7-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cefe7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cefe7-105">Förutsätter att en klassisk resultat variabel har det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="cefe7-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cefe7-106">Indata</span><span class="sxs-lookup"><span data-stu-id="cefe7-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="cefe7-107">faktiskt: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="cefe7-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="cefe7-108">Den variabel som ska kontrol leras.</span><span class="sxs-lookup"><span data-stu-id="cefe7-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="cefe7-109">förväntat: __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="cefe7-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="cefe7-110">Det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="cefe7-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="cefe7-111">meddelande: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cefe7-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cefe7-112">Fel meddelande strängen som ska användas när kontrollen utlöses.</span><span class="sxs-lookup"><span data-stu-id="cefe7-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cefe7-113">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cefe7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

