---
uid: Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
title: ReflectionPhases-användardefinierad typ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ReflectionPhases
qsharp.summary: Phases for a sequence of partial reflections in amplitude amplification.
ms.openlocfilehash: 743ece778239c223573a3a8536ae8059cea09d5f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191354"
---
# <a name="reflectionphases-user-defined-type"></a><span data-ttu-id="820d4-102">ReflectionPhases-användardefinierad typ</span><span class="sxs-lookup"><span data-stu-id="820d4-102">ReflectionPhases user defined type</span></span>

<span data-ttu-id="820d4-103">Namnrymd: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="820d4-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="820d4-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="820d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="820d4-105">Faser för en sekvens av partiella reflektioner i amplitud förstärkning.</span><span class="sxs-lookup"><span data-stu-id="820d4-105">Phases for a sequence of partial reflections in amplitude amplification.</span></span>

```qsharp

newtype ReflectionPhases = (AboutStart : Double[], AboutTarget : Double[]);
```



## <a name="named-items"></a><span data-ttu-id="820d4-106">Namngivna objekt</span><span class="sxs-lookup"><span data-stu-id="820d4-106">Named Items</span></span>

### <a name="aboutstart--double"></a><span data-ttu-id="820d4-107">AboutStart: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="820d4-107">AboutStart : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="820d4-108">En matris med faser för reflektion om start tillstånd.</span><span class="sxs-lookup"><span data-stu-id="820d4-108">An array of phases for reflection about the start state.</span></span>
### <a name="abouttarget--double"></a><span data-ttu-id="820d4-109">AboutTarget: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="820d4-109">AboutTarget : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="820d4-110">En matris med faser för reflektion om mål status.</span><span class="sxs-lookup"><span data-stu-id="820d4-110">An array of phases for reflection about the target state.</span></span>

## <a name="remarks"></a><span data-ttu-id="820d4-111">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="820d4-111">Remarks</span></span>

<span data-ttu-id="820d4-112">Båda matriserna måste ha samma längd.</span><span class="sxs-lookup"><span data-stu-id="820d4-112">Both arrays must be of equal length.</span></span> <span data-ttu-id="820d4-113">Observera att i många fall introducerar den första fasen om start tillstånd och senaste fasen om mål tillstånd en global fas ändring och kan ställas in på $0 $.</span><span class="sxs-lookup"><span data-stu-id="820d4-113">Note that in many cases, the first phase about the start state and last phase about the target state introduces a global phase shift and may be set to $0$.</span></span>