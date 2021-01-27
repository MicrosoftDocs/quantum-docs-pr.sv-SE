---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency-åtgärd
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 1e044a08718e02d673edab1d6b9d16d7f09618dc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851889"
---
# <a name="estimatefrequency-operation"></a><span data-ttu-id="2716c-102">EstimateFrequency-åtgärd</span><span class="sxs-lookup"><span data-stu-id="2716c-102">EstimateFrequency operation</span></span>

<span data-ttu-id="2716c-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="2716c-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="2716c-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2716c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2716c-105">Med tanke på förberedelse och mätning beräknar den frekvens med vilken mätningen lyckas (returnerar `Zero` ) genom att utföra ett angivet antal utvärderings versioner.</span><span class="sxs-lookup"><span data-stu-id="2716c-105">Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="2716c-106">Indata</span><span class="sxs-lookup"><span data-stu-id="2716c-106">Input</span></span>

### <a name="preparation--qubit--unit"></a><span data-ttu-id="2716c-107">förberedelse: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2716c-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2716c-108">En åtgärd $P $ som förbereder ett angivet tillstånd $ \rho $ på sin ingående registrering.</span><span class="sxs-lookup"><span data-stu-id="2716c-108">An operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="2716c-109">Mått: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __ogiltigt <Result>__</span><span class="sxs-lookup"><span data-stu-id="2716c-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="2716c-110">En åtgärd $M $ som representerar uppskattning av ränta.</span><span class="sxs-lookup"><span data-stu-id="2716c-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="2716c-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2716c-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2716c-112">Antalet qubits som förberedelsen och mätar varje åtgärd för.</span><span class="sxs-lookup"><span data-stu-id="2716c-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="2716c-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2716c-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2716c-114">Antalet gånger som mätningen ska utföras för att uppskatta ränte frekvensen.</span><span class="sxs-lookup"><span data-stu-id="2716c-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="2716c-115">Utdata: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2716c-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2716c-116">En uppskattning i $ \hat{p} $ av den frekvens med vilken $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0})) $ returnerar `Zero` , som erhålls med hjälp av den ej vägd binomialfördelningen $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $, där $n \_ {\uparrow} $ är antalet `Zero` resultat som observerats.</span><span class="sxs-lookup"><span data-stu-id="2716c-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

<span data-ttu-id="2716c-117">Detta är särskilt viktigt på mål datorer som respekterar fysiska begränsningar, så att sannolikheten inte kan mätas.</span><span class="sxs-lookup"><span data-stu-id="2716c-117">This is particularly important on target machines which respect physical limitations, such that probabilities cannot be measured.</span></span>