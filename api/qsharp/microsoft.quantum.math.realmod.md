---
uid: Microsoft.Quantum.Math.RealMod
title: Funktionen RealMod
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228261"
---
# <a name="realmod-function"></a><span data-ttu-id="37a1c-102">Funktionen RealMod</span><span class="sxs-lookup"><span data-stu-id="37a1c-102">RealMod function</span></span>

<span data-ttu-id="37a1c-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="37a1c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="37a1c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37a1c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37a1c-105">Beräknar modulen mellan två reella tal.</span><span class="sxs-lookup"><span data-stu-id="37a1c-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="37a1c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="37a1c-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="37a1c-107">värde: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37a1c-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37a1c-108">Ett reellt tal $x $ för att ta modulen.</span><span class="sxs-lookup"><span data-stu-id="37a1c-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="37a1c-109">modulo: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37a1c-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37a1c-110">Ett reellt tal som ska ta modulen med $x $ med avseende på.</span><span class="sxs-lookup"><span data-stu-id="37a1c-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="37a1c-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37a1c-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37a1c-112">Det minsta värde som ska returneras av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="37a1c-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="37a1c-113">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37a1c-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="37a1c-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="37a1c-114">Remarks</span></span>

<span data-ttu-id="37a1c-115">Den här funktionen beräknar den verkliga modulen genom att figursätta den verkliga linjen om enhets cirkeln och sedan hitta vinkeln på den enhets cirkel som motsvarar indatan.</span><span class="sxs-lookup"><span data-stu-id="37a1c-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="37a1c-116">`minValue`Inmatarna anger sedan i praktiken var du vill klippa ut enhets cirkeln.</span><span class="sxs-lookup"><span data-stu-id="37a1c-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>