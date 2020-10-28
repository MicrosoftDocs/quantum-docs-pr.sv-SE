---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733867"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="b4f95-102">RequiresCapability-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="b4f95-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="b4f95-103">Namnrymd: [Microsoft. Quantum. Target](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="b4f95-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="b4f95-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4f95-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4f95-105">Compile-känt attribut som används för att markera ett anrop med de körnings funktioner som krävs.</span><span class="sxs-lookup"><span data-stu-id="b4f95-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="b4f95-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="b4f95-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="b4f95-107">Nivå: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b4f95-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b4f95-108">Namnet på den körnings kapacitets nivå som krävs för anropet.</span><span class="sxs-lookup"><span data-stu-id="b4f95-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="b4f95-109">Orsak: [sträng](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b4f95-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b4f95-110">En beskrivning av varför anropet kräver denna körnings funktion.</span><span class="sxs-lookup"><span data-stu-id="b4f95-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4f95-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="b4f95-111">Remarks</span></span>

<span data-ttu-id="b4f95-112">Det här attributet läggs automatiskt till callables av kompilatorn, om inte en instans av det här attributet redan finns på det anrop som kan anropas.</span><span class="sxs-lookup"><span data-stu-id="b4f95-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="b4f95-113">Den bör inte användas förutom i sällsynta fall där kompilatorn inte härleder den nödvändiga funktionen korrekt.</span><span class="sxs-lookup"><span data-stu-id="b4f95-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="b4f95-114">Nedan visas en lista med namn på kapacitets nivåer, i ökande funktioner eller minskning av begränsningar:</span><span class="sxs-lookup"><span data-stu-id="b4f95-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="b4f95-115">Mått resultatet kan inte jämföras med likhet.</span><span class="sxs-lookup"><span data-stu-id="b4f95-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="b4f95-116">Mått resultat kan bara jämföras med likhets uttryck i IF-Statements villkorliga uttryck i åtgärder.</span><span class="sxs-lookup"><span data-stu-id="b4f95-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="b4f95-117">Blocket i en If-instruktion som är beroende av ett resultat kan inte innehålla set-instruktioner för föränderligt-variabler som deklareras utanför blocket eller Return-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="b4f95-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="b4f95-118">Inga körnings begränsningar.</span><span class="sxs-lookup"><span data-stu-id="b4f95-118">No runtime restrictions.</span></span> <span data-ttu-id="b4f95-119">Alla Q #-program kan köras.</span><span class="sxs-lookup"><span data-stu-id="b4f95-119">Any Q# program can be executed.</span></span>