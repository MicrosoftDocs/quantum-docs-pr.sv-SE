---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843333"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="5fdf9-102">CarryOutCoreCDKM-åtgärd</span><span class="sxs-lookup"><span data-stu-id="5fdf9-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="5fdf9-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="5fdf9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5fdf9-105">Kärn åtgärden i RippleCarryAdderCDKM, som används med ovanstående ApplyOuterCDKMAdder-åtgärd, som har avvisats med den här åtgärden för att hämta den inre driften av RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="5fdf9-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="5fdf9-106">Den här åtgärden beräknar qubit och tillämpar en sekvens av inte portar på en del av indatan `ys` .</span><span class="sxs-lookup"><span data-stu-id="5fdf9-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5fdf9-107">Indata</span><span class="sxs-lookup"><span data-stu-id="5fdf9-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="5fdf9-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5fdf9-109">Första qubit-registrering.</span><span class="sxs-lookup"><span data-stu-id="5fdf9-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="5fdf9-110">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5fdf9-111">Andra qubit-registrering.</span><span class="sxs-lookup"><span data-stu-id="5fdf9-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="5fdf9-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5fdf9-113">Ancilla-qubit som används i RippleCarryAdderCDKM har skickats till den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5fdf9-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="5fdf9-114">bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5fdf9-115">Utför qubit i RippleCarryAdderCDKM-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="5fdf9-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5fdf9-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fdf9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="5fdf9-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="5fdf9-117">References</span></span>

- <span data-ttu-id="5fdf9-118">Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum krusning-Drive-extra kretsen", 2004.</span><span class="sxs-lookup"><span data-stu-id="5fdf9-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1