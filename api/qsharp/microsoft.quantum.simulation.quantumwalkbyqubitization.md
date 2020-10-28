---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Funktionen QuantumWalkByQubitization
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92734118"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="f8b62-102">Funktionen QuantumWalkByQubitization</span><span class="sxs-lookup"><span data-stu-id="f8b62-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="f8b62-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f8b62-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f8b62-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8b62-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8b62-105">Konverterar en block kodnings reflektion till en Quantum-LED.</span><span class="sxs-lookup"><span data-stu-id="f8b62-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="f8b62-106">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f8b62-106">Description</span></span>

<span data-ttu-id="f8b62-107">Utifrån en `BlockEncodingReflection` person som representeras av en enhetlig $U $ som kodar en viss operatör $H $ of Interest, konverterar den till en Quantum-sats $W $ som innehåller spektrumet $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="f8b62-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="f8b62-108">Indata</span><span class="sxs-lookup"><span data-stu-id="f8b62-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="f8b62-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="f8b62-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="f8b62-110">En `BlockEncodingReflection` enhetlig $U $ som ska konverteras till en Quantum-LED.</span><span class="sxs-lookup"><span data-stu-id="f8b62-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="f8b62-111">Utdata: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhet](xref:microsoft.quantum.lang-ref.unit) just + CTL</span><span class="sxs-lookup"><span data-stu-id="f8b62-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f8b62-112">En Quantum-$W $ som agerar gemensamt på registren `a` och `s` som blockerar-kodar $H $ och innehåller spektrumet $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="f8b62-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="f8b62-113">Referenser</span><span class="sxs-lookup"><span data-stu-id="f8b62-113">References</span></span>

- <span data-ttu-id="f8b62-114">Hamiltonian-simulering av Qubitization Guang lämnar demon Hao Low, Isak L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="f8b62-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="f8b62-115">Se även</span><span class="sxs-lookup"><span data-stu-id="f8b62-115">See Also</span></span>

- [<span data-ttu-id="f8b62-116">Microsoft. Quantum. simulering. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="f8b62-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="f8b62-117">Microsoft. Quantum. simulering. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="f8b62-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)