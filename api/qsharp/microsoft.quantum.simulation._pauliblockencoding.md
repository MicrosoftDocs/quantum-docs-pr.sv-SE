---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: _PauliBlockEncoding funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92726340"
---
# <a name="_pauliblockencoding-function"></a><span data-ttu-id="9d636-102">_PauliBlockEncoding funktion</span><span class="sxs-lookup"><span data-stu-id="9d636-102">_PauliBlockEncoding function</span></span>

<span data-ttu-id="9d636-103">Namnrymd: [Microsoft. Quantum. simulering](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="9d636-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="9d636-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d636-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d636-105">Skapar en typ av block kodning för en Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="9d636-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="9d636-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ beskrivs av en summa av Pauli-termer $P _j $, var och en med verklig koefficient $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="9d636-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="9d636-107">Indata</span><span class="sxs-lookup"><span data-stu-id="9d636-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="9d636-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="9d636-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="9d636-109">En `GeneratorSystem` som beskriver $H $ som en summa av Pauli villkor</span><span class="sxs-lookup"><span data-stu-id="9d636-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a><span data-ttu-id="9d636-110">statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) rejust + CTL</span><span class="sxs-lookup"><span data-stu-id="9d636-110">statePrepUnitary : [Double](xref:microsoft.quantum.lang-ref.double)[] -> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9d636-111">En enhetlig åtgärd $V $ som tillämpar den enhetliga $V _j $ som styrs av index $ \ket{j} $, med en funktion $f: j\rightarrow V_j $.</span><span class="sxs-lookup"><span data-stu-id="9d636-111">A unitary operation $V$ that applies the unitary $V_j$ controlled on index $\ket{j}$, given a function $f: j\rightarrow V_j$.</span></span>


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="9d636-112">multiplexor: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) rejust + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL</span><span class="sxs-lookup"><span data-stu-id="9d636-112">multiplexer : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl) -> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>





## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="9d636-113">Utdata: ([dubbel](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="9d636-113">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="9d636-114">Första parametern</span><span class="sxs-lookup"><span data-stu-id="9d636-114">First parameter</span></span>

<span data-ttu-id="9d636-115">En-norm för koefficienter $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="9d636-115">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="9d636-116">Andra parameter</span><span class="sxs-lookup"><span data-stu-id="9d636-116">Second parameter</span></span>

<span data-ttu-id="9d636-117">En `BlockEncodingReflection` enhetlig $U $ Hamiltonian $U $.</span><span class="sxs-lookup"><span data-stu-id="9d636-117">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $U$.</span></span> <span data-ttu-id="9d636-118">Eftersom den här lösningen uppfyller $U ^ 2 = I $, är det också en reflektion.</span><span class="sxs-lookup"><span data-stu-id="9d636-118">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d636-119">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9d636-119">Remarks</span></span>

<span data-ttu-id="9d636-120">Exempel åtgärder för att förbereda och avförbereda statusen $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ och skapa en multiplicering-kontrollerad enhetlighet är <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> och <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="9d636-120">Example operations the prepare and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and construct a multiply-controlled unitary are <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>