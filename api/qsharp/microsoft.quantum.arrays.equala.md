---
uid: Microsoft.Quantum.Arrays.EqualA
title: Likhets funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 176e15139a27d375fb047c07fa1ee778dc8cc2ce
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221376"
---
# <a name="equala-function"></a><span data-ttu-id="a3845-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="a3845-102">EqualA function</span></span>

<span data-ttu-id="a3845-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a3845-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a3845-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3845-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3845-105">Två matriser av samma typ och ett predikat som har definierats för par element i matriserna, kontrollerar om matriserna är lika.</span><span class="sxs-lookup"><span data-stu-id="a3845-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="a3845-106">Indata</span><span class="sxs-lookup"><span data-stu-id="a3845-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="a3845-107">lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a3845-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a3845-108">En funktion från tupel `('T, 'T)` till `Bool` som används för att kontrol lera om två element i matriser är lika.</span><span class="sxs-lookup"><span data-stu-id="a3845-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="a3845-109">matris1: ' t []</span><span class="sxs-lookup"><span data-stu-id="a3845-109">array1 : 'T[]</span></span>

<span data-ttu-id="a3845-110">Den första matrisen som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a3845-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="a3845-111">matris2: ' t []</span><span class="sxs-lookup"><span data-stu-id="a3845-111">array2 : 'T[]</span></span>

<span data-ttu-id="a3845-112">Den andra matrisen som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="a3845-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a3845-113">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a3845-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a3845-114">Värdet `true` IF och endast IF `array1` och `array2` är lika med.</span><span class="sxs-lookup"><span data-stu-id="a3845-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="a3845-115">Det vill säga om båda matriserna har samma längd och alla element är lika definierade som de av `equal` .</span><span class="sxs-lookup"><span data-stu-id="a3845-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a3845-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="a3845-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a3845-117">Inte</span><span class="sxs-lookup"><span data-stu-id="a3845-117">'T</span></span>

<span data-ttu-id="a3845-118">Typen för varje mat ris element.</span><span class="sxs-lookup"><span data-stu-id="a3845-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3845-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="a3845-119">Remarks</span></span>

<span data-ttu-id="a3845-120">Den här funktionen definieras för generiska typer. det vill säga när vi har två matriser `'T[]` och en funktion `equal: ('T, 'T) -> Bool` , returnerar den här funktionen ett `Bool` värde som anger om matriserna är lika.</span><span class="sxs-lookup"><span data-stu-id="a3845-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="a3845-121">För att två matriser ska anses vara lika måste de ha samma längd och elementen i samma positioner i matriserna måste vara identiska.</span><span class="sxs-lookup"><span data-stu-id="a3845-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>