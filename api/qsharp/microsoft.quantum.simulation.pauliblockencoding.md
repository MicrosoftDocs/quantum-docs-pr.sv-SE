---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Funktionen PauliBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92730915"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="4484f-102">Funktionen PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="4484f-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="4484f-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4484f-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4484f-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4484f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4484f-105">Skapar en typ av block kodning för en Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4484f-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="4484f-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ beskrivs av en summa av Pauli-termer $P _j $, var och en med verklig koefficient $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="4484f-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="4484f-107">Indata</span><span class="sxs-lookup"><span data-stu-id="4484f-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="4484f-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="4484f-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="4484f-109">En `GeneratorSystem` som beskriver $H $ som en summa av Pauli villkor</span><span class="sxs-lookup"><span data-stu-id="4484f-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="4484f-110">Utdata: ([dubbel](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="4484f-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="4484f-111">Första parametern</span><span class="sxs-lookup"><span data-stu-id="4484f-111">First parameter</span></span>

<span data-ttu-id="4484f-112">En-norm för koefficienter $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="4484f-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="4484f-113">Andra parameter</span><span class="sxs-lookup"><span data-stu-id="4484f-113">Second parameter</span></span>

<span data-ttu-id="4484f-114">En `BlockEncodingReflection` enhetlig $U $ Hamiltonian $H $.</span><span class="sxs-lookup"><span data-stu-id="4484f-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="4484f-115">Eftersom den här lösningen uppfyller $U ^ 2 = I $, är det också en reflektion.</span><span class="sxs-lookup"><span data-stu-id="4484f-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="4484f-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="4484f-116">Remarks</span></span>

<span data-ttu-id="4484f-117">Detta erhålls genom att förbereda och stoppa statusen $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, och skapa en multiplicering-kontrollerad <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> och <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="4484f-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>