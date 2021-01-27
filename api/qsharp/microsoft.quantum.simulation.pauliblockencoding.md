---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: Funktionen PauliBlockEncoding
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848010"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="75ee8-102">Funktionen PauliBlockEncoding</span><span class="sxs-lookup"><span data-stu-id="75ee8-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="75ee8-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="75ee8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="75ee8-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="75ee8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="75ee8-105">Skapar en typ av block kodning för en Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="75ee8-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="75ee8-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ beskrivs av en summa av Pauli-termer $P _j $, var och en med verklig koefficient $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="75ee8-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="75ee8-107">Indata</span><span class="sxs-lookup"><span data-stu-id="75ee8-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="75ee8-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="75ee8-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="75ee8-109">En `GeneratorSystem` som beskriver $H $ som en summa av Pauli villkor</span><span class="sxs-lookup"><span data-stu-id="75ee8-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="75ee8-110">Utdata: ([dubbel](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="75ee8-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="75ee8-111">Första parametern</span><span class="sxs-lookup"><span data-stu-id="75ee8-111">First parameter</span></span>

<span data-ttu-id="75ee8-112">En-norm för koefficienter $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="75ee8-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="75ee8-113">Andra parameter</span><span class="sxs-lookup"><span data-stu-id="75ee8-113">Second parameter</span></span>

<span data-ttu-id="75ee8-114">En `BlockEncodingReflection` enhetlig $U $ Hamiltonian $H $.</span><span class="sxs-lookup"><span data-stu-id="75ee8-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="75ee8-115">Eftersom den här lösningen uppfyller $U ^ 2 = I $, är det också en reflektion.</span><span class="sxs-lookup"><span data-stu-id="75ee8-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="75ee8-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="75ee8-116">Remarks</span></span>

<span data-ttu-id="75ee8-117">Detta erhålls genom att förbereda och stoppa statusen $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $, och skapa en multiplicering-kontrollerad <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> och <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="75ee8-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>