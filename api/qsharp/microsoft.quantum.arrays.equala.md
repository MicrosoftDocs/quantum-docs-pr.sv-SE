---
uid: Microsoft.Quantum.Arrays.EqualA
title: Likhets funktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848695"
---
# <a name="equala-function"></a><span data-ttu-id="e8b3e-102">Likhets funktion</span><span class="sxs-lookup"><span data-stu-id="e8b3e-102">EqualA function</span></span>

<span data-ttu-id="e8b3e-103">Namnrymd: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8b3e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8b3e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8b3e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8b3e-105">Två matriser av samma typ och ett predikat som har definierats för par element i matriserna, kontrollerar om matriserna är lika.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="e8b3e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="e8b3e-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="e8b3e-107">lika med: (t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e8b3e-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e8b3e-108">En funktion från tupel `('T, 'T)` till `Bool` som används för att kontrol lera om två element i matriser är lika.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="e8b3e-109">matris1: ' t []</span><span class="sxs-lookup"><span data-stu-id="e8b3e-109">array1 : 'T[]</span></span>

<span data-ttu-id="e8b3e-110">Den första matrisen som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="e8b3e-111">matris2: ' t []</span><span class="sxs-lookup"><span data-stu-id="e8b3e-111">array2 : 'T[]</span></span>

<span data-ttu-id="e8b3e-112">Den andra matrisen som ska jämföras.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e8b3e-113">Utdata: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e8b3e-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e8b3e-114">Värdet `true` IF och endast IF `array1` och `array2` är lika med.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="e8b3e-115">Det vill säga om båda matriserna har samma längd och alla element är lika definierade som de av `equal` .</span><span class="sxs-lookup"><span data-stu-id="e8b3e-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e8b3e-116">Typparametrar</span><span class="sxs-lookup"><span data-stu-id="e8b3e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8b3e-117">Inte</span><span class="sxs-lookup"><span data-stu-id="e8b3e-117">'T</span></span>

<span data-ttu-id="e8b3e-118">Typen för varje mat ris element.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="e8b3e-119">Exempel</span><span class="sxs-lookup"><span data-stu-id="e8b3e-119">Example</span></span>

<span data-ttu-id="e8b3e-120">Följande kod kontrollerar om olika par av matriser är lika:</span><span class="sxs-lookup"><span data-stu-id="e8b3e-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="e8b3e-121">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="e8b3e-121">Remarks</span></span>

<span data-ttu-id="e8b3e-122">Den här funktionen definieras för generiska typer. det vill säga när vi har två matriser `'T[]` och en funktion `equal: ('T, 'T) -> Bool` , returnerar den här funktionen ett `Bool` värde som anger om matriserna är lika.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="e8b3e-123">För att två matriser ska anses vara lika måste de ha samma längd och elementen i samma positioner i matriserna måste vara identiska.</span><span class="sxs-lookup"><span data-stu-id="e8b3e-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>