---
uid: Microsoft.Quantum.Math.RealMod
title: Funktionen RealMod
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848351"
---
# <a name="realmod-function"></a><span data-ttu-id="73c10-102">Funktionen RealMod</span><span class="sxs-lookup"><span data-stu-id="73c10-102">RealMod function</span></span>

<span data-ttu-id="73c10-103">Namnrymd: [Microsoft. Quantum. matematik](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="73c10-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="73c10-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73c10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73c10-105">Beräknar modulen mellan två reella tal.</span><span class="sxs-lookup"><span data-stu-id="73c10-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="73c10-106">Indata</span><span class="sxs-lookup"><span data-stu-id="73c10-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="73c10-107">värde: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73c10-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73c10-108">Ett reellt tal $x $ för att ta modulen.</span><span class="sxs-lookup"><span data-stu-id="73c10-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="73c10-109">modulo: [dubbel](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73c10-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73c10-110">Ett reellt tal som ska ta modulen med $x $ med avseende på.</span><span class="sxs-lookup"><span data-stu-id="73c10-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="73c10-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73c10-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73c10-112">Det minsta värde som ska returneras av den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="73c10-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="73c10-113">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73c10-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="73c10-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="73c10-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="73c10-115">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="73c10-115">Remarks</span></span>

<span data-ttu-id="73c10-116">Den här funktionen beräknar den verkliga modulen genom att figursätta den verkliga linjen om enhets cirkeln och sedan hitta vinkeln på den enhets cirkel som motsvarar indatan.</span><span class="sxs-lookup"><span data-stu-id="73c10-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="73c10-117">`minValue`Inmatarna anger sedan i praktiken var du vill klippa ut enhets cirkeln.</span><span class="sxs-lookup"><span data-stu-id="73c10-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>