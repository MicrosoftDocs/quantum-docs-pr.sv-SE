---
title: Pauli mått
description: Lär dig hur du arbetar med qubit Pauli mått åtgärder.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269481"
---
# <a name="pauli-measurements"></a><span data-ttu-id="6ef2c-103">Pauli mått</span><span class="sxs-lookup"><span data-stu-id="6ef2c-103">Pauli Measurements</span></span>

<span data-ttu-id="6ef2c-104">I de föregående diskussionerna har vi fokuserat på beräknings bas mått.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="6ef2c-105">I själva verket finns det andra vanliga mätningar som sker i den Quantum-bearbetningen som, från ett och samma perspektiv, är praktiska att uttrycka när det gäller beräknings bas mått.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="6ef2c-106">När du arbetar med Q # är den vanligaste typen av mätningar som du kommer att köra i troligen *Pauli mätningar*, som generaliserar beräknings bas mått för att ta med mätningar i andra baser och paritet mellan olika qubits.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="6ef2c-107">I sådana fall är det vanligt att diskutera en Pauli-operatör i allmänhet en operatör som $X, Y, Z $ eller $Z \otimes z, x \otimes x, x \otimes Y $ och så vidare.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="6ef2c-108">I Q # representeras qubit Pauli-operatörer vanligt vis av matriser av typen `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="6ef2c-109">Om du till exempel vill representera $X \otimes Z \otimes Y $ kan du använda matrisen `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="6ef2c-110">Att diskutera mått i Pauli-operatörer är särskilt vanligt i underfältet för en Quantum-fel korrigering.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="6ef2c-111">I Q # följer vi en liknande konvention. Vi förklarar nu den här alternativa vyn över mått.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="6ef2c-112">Innan du går in på Detaljer om hur du kan tänka på en Pauli-mätning, är det bra att tänka på vad som mäter en enskild qubit i en Quantum-dator till Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="6ef2c-113">Föreställ dig att vi har $n ett $ qubitt Quantum-tillstånd, och sedan mäter en qubit omedelbart ut hälften av de möjligheter för $2 ^ n $ som tillstånden kan ha.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="6ef2c-114">Med andra ord mäter måttet Quantum-tillstånd till ett av två halva blank steg.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="6ef2c-115">Vi kan generalisera det sätt vi tycker att mäta för att återspegla den här intuition.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="6ef2c-116">För att kortfattat identifiera dessa under utrymmen behöver vi ett språk för att beskriva dem.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="6ef2c-117">Ett sätt att beskriva två under utrymmen är genom att ange dem via en matris som bara har två unika Eigenvalues, som tas av en konvention som är $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="6ef2c-118">Ett enkelt exempel på hur du kan beskriva under utrymmen på det här sättet är $Z $ :</span><span class="sxs-lookup"><span data-stu-id="6ef2c-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="6ef2c-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-119">$$ \begin{align}</span></span>
  <span data-ttu-id="6ef2c-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="6ef2c-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-121">\end{align}</span></span>
$$

<span data-ttu-id="6ef2c-122">Genom att läsa de diagonala elementen i Pauli-$Z $ matrisen kan vi se att $Z $ har två eigenvectors, $ \ket{0 } $ och $ \ket{1 } $, med motsvarande Eigenvalues $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="6ef2c-123">Om vi mäter qubit och hämtar `Zero` (som motsvarar State $ \ket{0 } $) vet vi att situationen för vår qubit är en $ + 1 $ eigenstate av $Z $ operatören.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="6ef2c-124">På samma sätt `One` vet vi att vår qubit är en $-1 $ eigenstate av $Z $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="6ef2c-125">Den här processen kallas för Pauli-mått som "mäta Pauli $Z $ " och är helt likvärdig med att utföra en beräknings bas mätning.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="6ef2c-126">En \times $ matris på $2 2 som är en enhetlig transformering av $Z $ uppfyller även det här kriteriet.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="6ef2c-127">Det vill säga att vi också kan använda en matris $A = U ^ \dagger Z U $ , där $U $ är en annan enhetlig matris, för att ge en matris som definierar de två resultatet av en mätning i $ \pm 1- $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="6ef2c-128">Pauli-mätningarna hänvisar till den enhetliga motsvarigheten genom att identifiera $X, Y, Z- $ mått som likvärdiga mätningar som en kan göra för att få information från en qubit.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="6ef2c-129">De här måtten anges nedan för bekvämlighet.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="6ef2c-130">Pauli-mått</span><span class="sxs-lookup"><span data-stu-id="6ef2c-130">Pauli Measurement</span></span>  |<span data-ttu-id="6ef2c-131">Enhetlig omvandling</span><span class="sxs-lookup"><span data-stu-id="6ef2c-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="6ef2c-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-132">$Z$</span></span>               | <span data-ttu-id="6ef2c-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-133">$\boldone$</span></span>             |
| <span data-ttu-id="6ef2c-134">$X$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-134">$X$</span></span>               | <span data-ttu-id="6ef2c-135">$H$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-135">$H$</span></span>                    |
| <span data-ttu-id="6ef2c-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-136">$Y$</span></span>               | <span data-ttu-id="6ef2c-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="6ef2c-138">Det innebär att "mått $Y $ " är detsamma som att använda $HS ^ \dagger $ och sedan mäta beräknings grunden, där [`S`](xref:microsoft.quantum.intrinsic.s) är en inbyggd Quantum-åtgärd som ibland kallas "fas grind" och kan simuleras av den enhetliga matrisen</span><span class="sxs-lookup"><span data-stu-id="6ef2c-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="6ef2c-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-139">$$ \begin{align}</span></span>
    <span data-ttu-id="6ef2c-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="6ef2c-141">1 & 0 \\ \\ 0 & i \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="6ef2c-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-142">\end{align}</span></span>
$$

<span data-ttu-id="6ef2c-143">Det motsvarar också att använda $HS ^ \dagger $ i den Quantum State-vektorn och sedan mäta $Z $ , så att följande åtgärd motsvarar `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="6ef2c-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="6ef2c-144">Rätt tillstånd kan sedan hittas genom att transformera till beräknings grunden, som är ett belopp för att tillämpa $SH på den $ Quantum-delstats vektorn. i ovanstående kodfragment hanteras omvandlingen tillbaka till beräknings basen automatiskt genom användningen av `within … apply` blocket.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="6ef2c-145">I Q # säger vi resultatet---det vill, den klassiska information som extraheras från att interagera med tillstånds---anges av ett `Result` värde $j \in \\ {\Texttt{Zero } , \texttt{One } \\ } $ som anger om resultatet är i $ (-1) ^ j $ eigenspace i Pauli-operatorn uppmätt.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="6ef2c-146">Flera qubit-mått</span><span class="sxs-lookup"><span data-stu-id="6ef2c-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="6ef2c-147">Mätningar av multi-qubit Pauli-operatörer definieras på samma sätt som de visas på:</span><span class="sxs-lookup"><span data-stu-id="6ef2c-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="6ef2c-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ & -1&0&0 \\\\ 0&0 & -1&0 0&0&\\\\ 0&1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="6ef2c-149">Det innebär att behållna produkter av två Pauli $Z- $ operatörer utgör en matris som består av två blank steg bestående av $ + 1 $ och $-1 $ Eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="6ef2c-150">Precis som med ett qubit-fall utgör både ett halvt utrymme att hälften av det tillgängliga vektor utrymmet tillhör $ + 1 $ eigenspace och den återstående halvan till $-1- $ eigenspace.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="6ef2c-151">I allmänhet är det enkelt att se från definitionen av den beskrivande produkten som bevarar-produkten av Pauli $Z- $ operatörer och identiteten lyder på detta.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="6ef2c-152">Exempel:</span><span class="sxs-lookup"><span data-stu-id="6ef2c-152">For example,</span></span>

<span data-ttu-id="6ef2c-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-153">$$ \begin{align}</span></span>
    <span data-ttu-id="6ef2c-154">Z-\otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="6ef2c-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="6ef2c-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-156">\end{align}</span></span>
$$

<span data-ttu-id="6ef2c-157">Precis som tidigare beskriver en enhetlig omvandling av sådana matriser även två hälften-blank steg med namnet $ \pm 1 $ Eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="6ef2c-158">Till exempel, $X \otimes X = h \otimes h (z \otimes z) h \otimes h $ från den identitet som $Z = HXH $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="6ef2c-159">På samma sätt som med ett-qubit-fall kan alla två-qubit-Pauli-mått skrivas som $U ^ \dagger (Z \otimes \id) U $ för $4 \times 4 $ enhetliga matriser $U $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="6ef2c-160">Vi räknar upp omvandlingarna i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="6ef2c-161">I tabellen nedan använder vi $ \operatorname{SWAP } $ för att ange matrisen $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="6ef2c-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="6ef2c-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="6ef2c-164">$ $ som används för att simulera den inbyggda åtgärden [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="6ef2c-165">Pauli-mått</span><span class="sxs-lookup"><span data-stu-id="6ef2c-165">Pauli Measurement</span></span>     |<span data-ttu-id="6ef2c-166">Enhetlig omvandling</span><span class="sxs-lookup"><span data-stu-id="6ef2c-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="6ef2c-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="6ef2c-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="6ef2c-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="6ef2c-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="6ef2c-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="6ef2c-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="6ef2c-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="6ef2c-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="6ef2c-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="6ef2c-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="6ef2c-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="6ef2c-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="6ef2c-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="6ef2c-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="6ef2c-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-181">$Z\otimes Z$</span></span> | <span data-ttu-id="6ef2c-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="6ef2c-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-183">$X\otimes Z$</span></span> | <span data-ttu-id="6ef2c-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="6ef2c-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-185">$Y\otimes Z$</span></span> | <span data-ttu-id="6ef2c-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="6ef2c-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-187">$Z\otimes X$</span></span> | <span data-ttu-id="6ef2c-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="6ef2c-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-189">$X\otimes X$</span></span> | <span data-ttu-id="6ef2c-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="6ef2c-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-191">$Y\otimes X$</span></span> | <span data-ttu-id="6ef2c-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="6ef2c-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-193">$Z\otimes Y$</span></span> | <span data-ttu-id="6ef2c-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="6ef2c-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-195">$X\otimes Y$</span></span> | <span data-ttu-id="6ef2c-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="6ef2c-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="6ef2c-197">$Y\otimes Y$</span></span> | <span data-ttu-id="6ef2c-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="6ef2c-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="6ef2c-199">Här [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) visas åtgärden av följande skäl.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="6ef2c-200">Varje Pauli-mått som inte omfattar $ \boldone- $ matrisen är lika med upp till en enhetlig till $Z \otimes Z $ av ovanstående orsaker.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="6ef2c-201">Eigenvalues för $Z \otimes Z $ är bara beroende av pariteten för qubits som utgör varje beräknings bas vektor och de kontrollerade-inte-åtgärderna kan beräkna denna paritet och lagra den i den första biten.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="6ef2c-202">När den första biten mäts kan vi återställa identiteten för det resulterande halva utrymmet, vilket motsvarar att mäta Pauli-operatorn.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="6ef2c-203">Ytterligare en anmärkning: det kan vara frestande att anta att mät $Z \otimes z $ är detsamma som att mäta $Z \otimes \mathbb{1 } $ och sedan $ \mathbb{1 } \otimes Z $ . Detta antagande skulle vara falskt.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="6ef2c-204">Orsaken är att mät $Z \otimes Z- $ projekt är Quantum-status i antingen $ + 1- $ eller $-1- $ eigenstate för dessa operatörer.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="6ef2c-205">Mät $Z \otimes \mathbb{1 } $ och sedan $ \Mathbb{1 } \otimes z- $ projekt i den första delen av $Z \otimes \mathbb{1 } $ och sedan till ett halvt utrymme på $ \mathbb{1 } \otimes Z $ . Eftersom det finns fyra beräknings bas vektorer minskar statusen till ett kvartals utrymme och minskar därför den till en enda beräknings bas vektor.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="6ef2c-206">Korrelationer mellan qubits</span><span class="sxs-lookup"><span data-stu-id="6ef2c-206">Correlations between qubits</span></span>
<span data-ttu-id="6ef2c-207">Ett annat sätt att titta på Mät behållar produkter av Pauli-matriser som $X \otimes X $ eller $Z \otimes Z $ är att dessa mätningar gör det möjligt att titta på information som lagras i korrelationerna mellan de två qubits.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="6ef2c-208">Genom att mäta $X \otimes \id $ kan du titta på information som lagras lokalt i den första qubit.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="6ef2c-209">Även om båda typerna av mätningar är lika värdefulla i Quantum Computing, lyser den tidigare kraften i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="6ef2c-210">Det visar att i Quantum Computing är ofta den information som du vill lära inte lagrad i en enskild qubit utan att i stället lagras lokalt i alla qubits samtidigt, och därför bara genom att titta på den via en gemensam mätning (t. ex. $Z \otimes Z $ ) blir den här informationen manifest.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="6ef2c-211">I fel korrigering vill vi till exempel ofta lära sig vilket fel som har inträffat och lära mig ingenting om det tillstånd som vi försöker skydda.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="6ef2c-212">[Kod exemplet bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) visar ett exempel på hur du kan göra det med hjälp av mätningar som $Z \otimes Z \otimes \id $ och $ \id \Otimes z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="6ef2c-213">Godtyckliga Pauli-operatörer som $X \otimes Y \Otimes Z \otimes \boldone $ kan också mätas.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="6ef2c-214">Alla sådana behållna produkter av Pauli-operatörer har bara två Eigenvalues $ \pm 1 $ och båda eigenspaces utgör hälften av utrymmena i hela vektor utrymmet.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="6ef2c-215">De sammanfaller därför med de krav som anges ovan.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="6ef2c-216">I Q # returnerar sådana mätningar $j $ om mätningen ger ett resultat i eigenspace-tecknet $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="6ef2c-217">Att ha Pauli mätningar som en inbyggd funktion i Q # är till hjälp eftersom man kan mäta sådana operatörer som kräver långa kedjor av kontrollerade, icke-portar och bas omvandlingar för att beskriva den diagonala $U $ grind som krävs för att uttrycka åtgärden som en beskrivare produkt i $Z $ och $ \id $ . Genom att kunna ange att du vill göra en av dessa fördefinierade mätningar behöver du inte oroa dig för att du ska kunna omvandla din grund till att en beräknings bas mätning ger nödvändig information.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="6ef2c-218">Q # hanterar alla nödvändiga transformeringar åt dig automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="6ef2c-219">Mer information finns i [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) åtgärderna och.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="6ef2c-220">No-Kloningsing-satsen</span><span class="sxs-lookup"><span data-stu-id="6ef2c-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="6ef2c-221">Quantum-informationen är kraftfull.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-221">Quantum information is powerful.</span></span>
<span data-ttu-id="6ef2c-222">Det gör det möjligt för oss att göra fantastiska saker som faktor tal exponentiellt snabbare än de bästa kända klassiska algoritmerna, eller att effektivt simulera korrelerade Electron-system som klassiska kräver exponentiell kostnad för att simulera korrekt.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="6ef2c-223">Det finns dock begränsningar för kraften i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="6ef2c-224">En sådan begränsning anges av *satsen No-kloningsing*.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="6ef2c-225">No-Kloningsing-satsen är aptly med namnet.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="6ef2c-226">Den tillåter inte kloning av generiska Quantum-tillstånd av en Quantum-dator.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="6ef2c-227">Satsen-beviset är remarkably är enkelt.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="6ef2c-228">Det fullständiga beviset på No-kloning-satsen är lite för tekniskt för vår diskussion här, men beviset för att det inte finns några ytterligare hjälp qubits finns inom vår omfattning (hjälp qubits är qubits som används för arbets utrymme under en beräkning och är lätt att använda och hanteras i Q #, se [lånade qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="6ef2c-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="6ef2c-229">För en sådan Quantum-dator måste klonings åtgärden beskrivas av en enhetlig matris.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="6ef2c-230">Vi tillåter inte mätningar, eftersom det skulle skada det Quantum-tillstånd som vi försöker klona.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="6ef2c-231">För att simulera klonings åtgärden vill vi att den enhetliga matrisen som används för att ha den egenskap som $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="6ef2c-232">$ $ för alla tillstånd $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="6ef2c-233">Egenskapen linjärt för mat ris multiplikation innebär sedan att för alla andra Quantum-tillstånd $ \ket { \phi } $,</span><span class="sxs-lookup"><span data-stu-id="6ef2c-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="6ef2c-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-234">$$ \begin{align}</span></span>
    <span data-ttu-id="6ef2c-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="6ef2c-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="6ef2c-237">+ \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="6ef2c-238">\right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).</span><span class="sxs-lookup"><span data-stu-id="6ef2c-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="6ef2c-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="6ef2c-239">\end{align}</span></span>
$$

<span data-ttu-id="6ef2c-240">Detta ger den grundläggande intuition bakom No-Kloningsing-satsen: alla enheter som kopierar ett okänt Quantum-tillstånd måste orsaka fel på minst några av de tillstånd som den kopierar.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="6ef2c-241">Den nyckel som förutsätter att Klonaren fungerar linjärt i indata-läget kan brytas genom addition och mätning av hjälp-qubits, men sådana interaktioner läcker också information om systemet genom mätnings statistiken och förhindrar exakt kloning i sådana fall.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="6ef2c-242">För [Mer information](xref:microsoft.quantum.more-information)om ett mer fullständigt korrektur av satsen No-kloningsing finns.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="6ef2c-243">No-kloning-satsen är viktigt för att ge kvalitativ förståelse för Quantum Computing, eftersom om du skulle kunna klona Quantum-tillstånden på ett mycket bra ställe skulle du ges en Magical möjlighet att lära sig från Quantum-tillstånd.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="6ef2c-244">I själva verket kan du bryta mot Heisenbergs vaunted osäkerhets princip.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="6ef2c-245">Alternativt kan du använda en optimal klonare för att ta ett enda exempel från en komplex Quantum-distribution och lära dig allt du kan behöva lära dig mer om distributionen från bara ett exempel.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="6ef2c-246">Detta skulle vara precis som du vänder på en och samma som när du berättar en vän om resultatet med att de svarar "Ah-fördelningen av dessa mynt måste vara Bernoulli med $p = 0.512643 \ ldots $ !"</span><span class="sxs-lookup"><span data-stu-id="6ef2c-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="6ef2c-247">En sådan instruktion skulle vara icke-sensical eftersom en bit av information (resultatet av huvudena) inte kan ge de många bitar av information som krävs för att koda distributionen utan avsevärd tidigare information.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="6ef2c-248">På samma sätt kan vi inte helt klona ett Quantum-tillstånd på samma sätt som vi inte kan förbereda en ensemble av sådana mynt utan att känna till $p $ .</span><span class="sxs-lookup"><span data-stu-id="6ef2c-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="6ef2c-249">Informationen är inte kostnads fri i Quantum Computing.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="6ef2c-250">Varje qubit uppmätta ger en enskild bit av information och No-klonings satsen visar att det inte finns några bakdörr som kan utnyttjas för att komma runt den grundläggande kompromissen mellan information som vunnits om systemet och den störning som har påbörjats.</span><span class="sxs-lookup"><span data-stu-id="6ef2c-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
