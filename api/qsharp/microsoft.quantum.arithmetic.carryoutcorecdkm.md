---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92731638"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="c498e-102">CarryOutCoreCDKM-åtgärd</span><span class="sxs-lookup"><span data-stu-id="c498e-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="c498e-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c498e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c498e-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c498e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c498e-105">Kärn åtgärden i RippleCarryAdderCDKM, som används med ovanstående ApplyOuterCDKMAdder-åtgärd, som har avvisats med den här åtgärden för att hämta den inre driften av RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="c498e-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="c498e-106">Den här åtgärden beräknar qubit och tillämpar en sekvens av inte portar på en del av indatan `ys` .</span><span class="sxs-lookup"><span data-stu-id="c498e-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c498e-107">Indata</span><span class="sxs-lookup"><span data-stu-id="c498e-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c498e-108">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c498e-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c498e-109">Första qubit-registrering.</span><span class="sxs-lookup"><span data-stu-id="c498e-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c498e-110">gar: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c498e-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c498e-111">Andra qubit-registrering.</span><span class="sxs-lookup"><span data-stu-id="c498e-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="c498e-112">Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c498e-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c498e-113">Ancilla-qubit som används i RippleCarryAdderCDKM har skickats till den här åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c498e-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="c498e-114">bär: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c498e-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c498e-115">Utför qubit i RippleCarryAdderCDKM-åtgärden.</span><span class="sxs-lookup"><span data-stu-id="c498e-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c498e-116">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c498e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="c498e-117">Referenser</span><span class="sxs-lookup"><span data-stu-id="c498e-117">References</span></span>

- <span data-ttu-id="c498e-118">Stefan A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum krusning-Drive-extra kretsen", 2004.</span><span class="sxs-lookup"><span data-stu-id="c498e-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1