---
uid: Microsoft.Quantum.Math.RealMod
title: Funktionen RealMod
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731038"
---
# <a name="realmod-function"></a><span data-ttu-id="1a2e6-102">Funktionen RealMod</span><span class="sxs-lookup"><span data-stu-id="1a2e6-102">RealMod function</span></span>

<span data-ttu-id="1a2e6-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1a2e6-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1a2e6-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1a2e6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1a2e6-105">Beräknar modulen mellan två reella tal.</span><span class="sxs-lookup"><span data-stu-id="1a2e6-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="1a2e6-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1a2e6-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="1a2e6-107">värde: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a2e6-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a2e6-108">Ett reellt tal $x $ för att ta modulen.</span><span class="sxs-lookup"><span data-stu-id="1a2e6-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="1a2e6-109">modulo: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a2e6-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a2e6-110">Ett reellt tal som ska ta modulen med $x $ med avseende på.</span><span class="sxs-lookup"><span data-stu-id="1a2e6-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="1a2e6-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a2e6-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1a2e6-112">Det minsta värde som ska returneras av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="1a2e6-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="1a2e6-113">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1a2e6-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="1a2e6-114">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1a2e6-114">Remarks</span></span>

<span data-ttu-id="1a2e6-115">Den här funktionen beräknar den verkliga modulen genom att figursätta den verkliga linjen om enhets cirkeln och sedan hitta vinkeln på den enhets cirkel som motsvarar indatan.</span><span class="sxs-lookup"><span data-stu-id="1a2e6-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="1a2e6-116">`minValue`Inmatarna anger sedan i praktiken var du vill klippa ut enhets cirkeln.</span><span class="sxs-lookup"><span data-stu-id="1a2e6-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>