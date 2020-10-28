---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Funktionen ExpandedCoefficients
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92727648"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="eb487-102">Funktionen ExpandedCoefficients</span><span class="sxs-lookup"><span data-stu-id="eb487-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="eb487-103">Namnrymd: [Microsoft. Quantum. kemi. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="eb487-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="eb487-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb487-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb487-105">Utökar komprimerings representationen av Jordan-Wigner-koefficienter för att kunna hämta en en-till-en-mappning mellan dessa och Pauli villkor.</span><span class="sxs-lookup"><span data-stu-id="eb487-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="eb487-106">Indata</span><span class="sxs-lookup"><span data-stu-id="eb487-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="eb487-107">coeff: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eb487-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eb487-108">En matris med koefficienter som läses från Jordan-Wigner Hamiltonian data struktur.</span><span class="sxs-lookup"><span data-stu-id="eb487-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="eb487-109">termType: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eb487-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eb487-110">Jordan-Wigner termns typ.</span><span class="sxs-lookup"><span data-stu-id="eb487-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="eb487-111">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="eb487-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="eb487-112">Expanderade matriser med koefficienter, en per Pauli-period.</span><span class="sxs-lookup"><span data-stu-id="eb487-112">Expanded arrays of coefficients, one per Pauli term.</span></span>