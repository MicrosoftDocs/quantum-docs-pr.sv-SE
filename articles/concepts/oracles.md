---
title: Kvantorakel
description: Lär dig hur du arbetar med och definierar Quantum Oracles, svarta Box-åtgärder som används som inmatade i en annan algoritm.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
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
ms.openlocfilehash: 747c08df110f1f10efe552628d15e3500509b690
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269566"
---
# <a name="quantum-oracles"></a><span data-ttu-id="2d864-103">Quantum Oracle</span><span class="sxs-lookup"><span data-stu-id="2d864-103">Quantum Oracles</span></span>

<span data-ttu-id="2d864-104">En Oracle-$O $ är en "svart box"-åtgärd som används som inmatad till en annan algoritm.</span><span class="sxs-lookup"><span data-stu-id="2d864-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="2d864-105">Ofta definieras sådana åtgärder med hjälp av en klassisk funktion $f: \\ {0, 1 \\ } ^ n \to \\ {0, 1 \\ } ^ m $ som tar en $n $ -bitars binär indata och producerar en $m $ -bitars binär utdata.</span><span class="sxs-lookup"><span data-stu-id="2d864-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="2d864-106">Det gör du genom att tänka på en viss binär Indatatyp $x = (x_ {0 } , x_ {1 } , \dots, x_ {n-1 } ) $.</span><span class="sxs-lookup"><span data-stu-id="2d864-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="2d864-107">Vi kan märka qubit tillstånd som $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1 } } \otimes \cdots \otimes \ket{x_ {n-1 } } $.</span><span class="sxs-lookup"><span data-stu-id="2d864-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="2d864-108">Vi kan först försöka definiera $O $ så att $O \ket {x } = \ket{f (x)} $, men det har ett par problem.</span><span class="sxs-lookup"><span data-stu-id="2d864-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="2d864-109">Först, $f $ kan ha en annan storlek på indata och utdata ($n \ne m $ ), som att tillämpa $O $ skulle ändra antalet qubits i registreringen.</span><span class="sxs-lookup"><span data-stu-id="2d864-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="2d864-110">Den andra, även om $n = m $ , kan inte funktionen vara inverteras: om $f (x) = f (y) $ för vissa $x \ne y $ , $O \ket {x } = O \ket {y $, } $O ^ \dagger o \ket {x } \ne o ^ \dagger O \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="2d864-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="2d864-111">Det innebär att vi inte kan skapa den angränsande åtgärden $O ^ \dagger $ , och Oracles måste ha ett angränsande definierat.</span><span class="sxs-lookup"><span data-stu-id="2d864-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="2d864-112">Definiera en Oracle genom att påverka beräknings bas staterna</span><span class="sxs-lookup"><span data-stu-id="2d864-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="2d864-113">Vi kan hantera båda dessa problem genom att introducera ett andra register över $m $ qubits för att hålla vårt svar.</span><span class="sxs-lookup"><span data-stu-id="2d864-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="2d864-114">Därefter definierar vi resultatet av Oracle i alla beräknings grund lägen: för alla $x \in \\ {0, 1 \\ } ^ n $ och $y \in \\ {0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="2d864-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="2d864-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-115">$$ \begin{align}</span></span>
    <span data-ttu-id="2d864-116">O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="2d864-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="2d864-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-117">\end{align}</span></span>
$$

<span data-ttu-id="2d864-118">Nu $O = O ^ \dagger $ , vilket innebär att vi har löst båda de tidigare problemen.</span><span class="sxs-lookup"><span data-stu-id="2d864-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="2d864-119">Om du vill se att $O = O ^ {\dagger } $, Observera att $O ^ 2 = \boldone $ sedan $a \oplus b \oplus b = a $ för alla $a, b \in \{ 0, 1 \} $.</span><span class="sxs-lookup"><span data-stu-id="2d864-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="2d864-120">Därför bör $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.</span><span class="sxs-lookup"><span data-stu-id="2d864-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="2d864-121">Det är viktigt att definiera en Oracle på det här sättet för varje beräknings grund tillstånd $ \ket{x } \ket{y } $ och även definiera hur $O $ fungerar för alla andra tillstånd.</span><span class="sxs-lookup"><span data-stu-id="2d864-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="2d864-122">Detta följer omedelbart från det faktum att $O $ , precis som alla Quantum-åtgärder, är linjärt i det tillstånd som det fungerar på.</span><span class="sxs-lookup"><span data-stu-id="2d864-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="2d864-123">Överväg Hadamard-åtgärden, till exempel, som definieras av $H \ket{0 } = \ket { +} $ och $H \ket{1 } = \ket { -} $.</span><span class="sxs-lookup"><span data-stu-id="2d864-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="2d864-124">Om vi vill veta hur $H $ agerar på $ \ket { +} $ kan vi använda den $H $ linjär,</span><span class="sxs-lookup"><span data-stu-id="2d864-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="2d864-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-125">$$ \begin{align}</span></span>
<span data-ttu-id="2d864-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (H \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="2d864-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="2d864-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-127">\end{align}</span></span>
$$

<span data-ttu-id="2d864-128">Om du definierar vår Oracle $ -$O kan vi på samma sätt använda att alla tillstånd $ \ket { \psi } $ på $n + m $ qubits kan skrivas som</span><span class="sxs-lookup"><span data-stu-id="2d864-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="2d864-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-129">$$ \begin{align}</span></span>
<span data-ttu-id="2d864-130">\ket { \psi } & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="2d864-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="2d864-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-131">\end{align}</span></span>
$$

<span data-ttu-id="2d864-132">där $ \alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m \to \mathbb{C } $ representerar koefficienterna för tillstånd $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="2d864-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="2d864-133">Därför</span><span class="sxs-lookup"><span data-stu-id="2d864-133">Thus,</span></span>

<span data-ttu-id="2d864-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-134">$$ \begin{align}</span></span>
<span data-ttu-id="2d864-135">O \ket { \psi } & = O \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \in \\ {0, 1 \\ } ^ n, y \in \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="2d864-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="2d864-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="2d864-137">Fas Oracle</span><span class="sxs-lookup"><span data-stu-id="2d864-137">Phase oracles</span></span>
<span data-ttu-id="2d864-138">Alternativt kan vi koda $f $ till en Oracle-$O $ genom att använda en _fas_ baserat på inmatat för att $O $ .</span><span class="sxs-lookup"><span data-stu-id="2d864-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="2d864-139">Vi kan till exempel definiera $O $ som $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="2d864-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="2d864-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="2d864-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-141">\end{align}</span></span>
<span data-ttu-id="2d864-142">$ $ Om en fas i Oracle agerar i ett register inlednings vis i ett beräknings bas tillstånd $ \ket{x } $, är den här fasen en global fas och kan därför inte ändras.</span><span class="sxs-lookup"><span data-stu-id="2d864-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="2d864-143">Men en sådan Oracle kan vara en mycket kraftfull resurs om den tillämpas på en överposition eller som en kontrollerad åtgärd.</span><span class="sxs-lookup"><span data-stu-id="2d864-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="2d864-144">Anta till exempel att en fas orcale $O _f $ för en qubit funktion $f $ .</span><span class="sxs-lookup"><span data-stu-id="2d864-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="2d864-145">Sedan $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="2d864-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0))} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.</span><span class="sxs-lookup"><span data-stu-id="2d864-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="2d864-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="2d864-147">\end{align}</span></span>
$$

<span data-ttu-id="2d864-148">I allmänhet kan båda vyerna i Oracle utökas för att representera klassiska funktioner som returnerar reella tal i stället för bara en enda bit.</span><span class="sxs-lookup"><span data-stu-id="2d864-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="2d864-149">Att välja det bästa sättet att implementera en Oracle är beroende av hur den här Oracle kommer att användas inom en specifik algoritm.</span><span class="sxs-lookup"><span data-stu-id="2d864-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="2d864-150">Till exempel är [Deutsch-Jozsa-algoritmen](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) beroende av den Oracle som implementerats på det första sättet, medan [algoritmen för Grover är](https://en.wikipedia.org/wiki/Grover's_algorithm) beroende av den Oracle som implementerats på det andra sättet.</span><span class="sxs-lookup"><span data-stu-id="2d864-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="2d864-151">För mer information, föreslår vi diskussionen i [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="2d864-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
