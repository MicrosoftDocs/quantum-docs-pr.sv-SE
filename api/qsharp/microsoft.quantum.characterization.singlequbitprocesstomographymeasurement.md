---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 3756040df8e34ecee1e968428b08387e0096ab7b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204206"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="9422e-102">SingleQubitProcessTomographyMeasurement-åtgärd</span><span class="sxs-lookup"><span data-stu-id="9422e-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="9422e-103">Namnrymd: [Microsoft. Quantum. karakterisering](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="9422e-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="9422e-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9422e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9422e-105">Utför en qubit process tomography mått i Pauli-basen, med tanke på en viss kanal av intresse.</span><span class="sxs-lookup"><span data-stu-id="9422e-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="9422e-106">Indata</span><span class="sxs-lookup"><span data-stu-id="9422e-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="9422e-107">förberedelse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9422e-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9422e-108">Pauli-basen $P $ där en qubit ska förberedas.</span><span class="sxs-lookup"><span data-stu-id="9422e-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="9422e-109">Mått: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9422e-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9422e-110">Pauli-basen $Q $ i vilken en qubit ska mätas.</span><span class="sxs-lookup"><span data-stu-id="9422e-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="9422e-111">kanal: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9422e-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9422e-112">En enda qubit-kanal $ \Lambda $ vars beteende beräknas med process tomography.</span><span class="sxs-lookup"><span data-stu-id="9422e-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9422e-113">Utdata: __ogiltig <Result>__</span><span class="sxs-lookup"><span data-stu-id="9422e-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9422e-114">Resultatet `Zero` med sannolikhet $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="9422e-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="9422e-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9422e-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="9422e-116">Kommentarer</span><span class="sxs-lookup"><span data-stu-id="9422e-116">Remarks</span></span>

<span data-ttu-id="9422e-117">Distributionen över resultaten som returneras av den här åtgärden är ett specialfall av qubit status tomography.</span><span class="sxs-lookup"><span data-stu-id="9422e-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="9422e-118">Låt $ \rho = J (\Lambda)/$2 vara Choi – Jamiłkowski-tillstånd för $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="9422e-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="9422e-119">Sedan är fördelningen ovan identisk med $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ där $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 är den effektiva mätning som motsvarar $P $ och $Q $.</span><span class="sxs-lookup"><span data-stu-id="9422e-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>