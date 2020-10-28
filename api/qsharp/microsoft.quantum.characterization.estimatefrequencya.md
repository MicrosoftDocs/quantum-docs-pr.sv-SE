---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92728227"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="1f7c0-102">EstimateFrequencyA-åtgärd</span><span class="sxs-lookup"><span data-stu-id="1f7c0-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="1f7c0-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="1f7c0-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="1f7c0-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f7c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f7c0-105">Med tanke på en förberedelse som är adjointable och mätning, beräknar den frekvens med vilken mätningen lyckas (returnerar `Zero` ) genom att utföra ett angivet antal utvärderings versioner.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="1f7c0-106">Indata</span><span class="sxs-lookup"><span data-stu-id="1f7c0-106">Input</span></span>

### <a name="preparation--qubit--unit-adj"></a><span data-ttu-id="1f7c0-107">förberedelse: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhets](xref:microsoft.quantum.lang-ref.unit) justering</span><span class="sxs-lookup"><span data-stu-id="1f7c0-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="1f7c0-108">En adjointable-åtgärd $P $ som förbereder ett angivet tillstånd $ \rho $ på sin ingående registrering.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="1f7c0-109">Mått: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="1f7c0-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="1f7c0-110">En åtgärd $M $ som representerar uppskattning av ränta.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="1f7c0-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f7c0-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f7c0-112">Antalet qubits som förberedelsen och mätar varje åtgärd för.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="1f7c0-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f7c0-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f7c0-114">Antalet gånger som mätningen ska utföras för att uppskatta ränte frekvensen.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="1f7c0-115">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1f7c0-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1f7c0-116">En uppskattning i $ \hat{p} $ av den frekvens med vilken $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ returnerar `Zero` , som erhålls med hjälp av den ej vägd binomialfördelningen $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, där $n \_ {\uparrow} $ är antalet `Zero` resultat som observerats.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f7c0-117">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="1f7c0-117">Remarks</span></span>

<span data-ttu-id="1f7c0-118">För adjointable-åtgärder kan vissa antaganden, till exempel genom att anropa åtgärden, förbereda qubits till exakt samma tillstånd, vilket gör det möjligt för mål datorer att göra vissa prestanda optimeringar.</span><span class="sxs-lookup"><span data-stu-id="1f7c0-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>