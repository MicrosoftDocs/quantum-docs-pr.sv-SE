---
title: Utforma din egen klassificerare med QDK
description: Lär dig grunderna för att utforma krets modeller för den koncentriska klassificeraren i Quantum-kretsen.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909729"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="f6b5d-103">Utforma din egen klassificerare</span><span class="sxs-lookup"><span data-stu-id="f6b5d-103">Design your own classifier</span></span>

<span data-ttu-id="f6b5d-104">I den här guiden får du lära dig de grundläggande begreppen bakom utformningen av krets modeller för den koncentriska klassificeraren i Quantum-kretsen.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="f6b5d-105">Precis som i klassisk djup inlärning finns det ingen allmän regel för att välja en speciell arkitektur.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="f6b5d-106">Beroende på problemet kommer vissa arkitekturer att fungera bättre än andra.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="f6b5d-107">Men det finns vissa begrepp som kan vara användbara när du utformar kretsen:</span><span class="sxs-lookup"><span data-stu-id="f6b5d-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="f6b5d-108">Ett stort antal parametrar innebär en mer flexibel modell som kan vara lämplig för att rita komplexa klassificerings gränser, men det kan också vara mer känsligt för överanpassning.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="f6b5d-109">Entangling-portar mellan qubits är nödvändiga för att avbilda korrelationer mellan Quantum-funktionerna.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="f6b5d-110">Så här skapar du en klassificerare med Q\#</span><span class="sxs-lookup"><span data-stu-id="f6b5d-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="f6b5d-111">För att bygga en klassificerare ska vi kombinera parametrized kontrollerade rotationer i vår krets modell.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="f6b5d-112">För att göra det kan vi använda typen [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) som definierats i biblioteket Quantum Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="f6b5d-113">Den här typen accepterar fyra argument som avgör: indexet för mål-qubit, matrisen med index-qubits, rotations axeln och index för den associerade parametern i matrisen med parametrar som definierar modellen.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="f6b5d-114">Nu ska vi se ett exempel på en klassificerare.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="f6b5d-115">I [exemplen på halv måne](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)kan vi hitta följande klassificerare som definierats i filen `Training.qs`.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

<span data-ttu-id="f6b5d-116">Vad vi definierar här är en funktion som returnerar en matris med `ControlledRotation` element, som tillsammans med en matris med parametrar och en förskjutning definierar våra [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span><span class="sxs-lookup"><span data-stu-id="f6b5d-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="f6b5d-117">Den här typen är grundläggande i Quantum Machine Learning-biblioteket och definierar klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="f6b5d-118">Den krets som definieras i funktionen ovan är en del av en klassificerare där varje exempel i data uppsättningen innehåller två funktioner.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="f6b5d-119">Därför behöver vi bara två qubits.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="f6b5d-120">Den grafiska åter givningen av kretsen är:</span><span class="sxs-lookup"><span data-stu-id="f6b5d-120">The graphical representation of the circuit is:</span></span>

 ![Exempel på krets modell](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="f6b5d-122">Använd biblioteks funktionerna för att skriva lager med portar</span><span class="sxs-lookup"><span data-stu-id="f6b5d-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="f6b5d-123">Anta att vi har en data uppsättning med 784-funktioner per instans, t. ex. bilder på 28 × 28 pixlar som MNIST-datauppsättningen.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="f6b5d-124">I det här fallet blir kretsens bredd tillräckligt stor så att skrivning av varje enskild grind blir en möjlig men opraktisk uppgift.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="f6b5d-125">Detta är anledningen till att Quantum Machine Learning-biblioteket innehåller en uppsättning verktyg som automatiskt genererar lager av parametrized-rotationer.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="f6b5d-126">Till exempel returnerar funktionen [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) en matris med okontrollerade qubit rotationer längs en viss axel, med en rotation för varje qubit i registret, varje parametrized med en annan modell parameter.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="f6b5d-127">`LocalRotationsLayer(4, X)` returnerar till exempel följande port uppsättning:</span><span class="sxs-lookup"><span data-stu-id="f6b5d-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Lokalt rotations skikt](~/media/local_rotations_layer.PNG)

<span data-ttu-id="f6b5d-129">Vi rekommenderar att du utforskar [API-referenece för Quantum Machine Learning-biblioteket](xref:microsoft.quantum.machinelearning) för att identifiera alla verktyg som är tillgängliga för att effektivisera krets designen.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-129">We recommend you to explore the [API referenece of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6b5d-130">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f6b5d-130">Next steps</span></span>

 <span data-ttu-id="f6b5d-131">Prova olika strukturer i exemplen som tillhandahålls av exemplen.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="f6b5d-132">Ser du ändringar i modellens prestanda?</span><span class="sxs-lookup"><span data-stu-id="f6b5d-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="f6b5d-133">I nästa självstudie [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load)får du lära dig hur du läser in data uppsättningar för att testa och utforska nya arkitekturer i klassificeraren.</span><span class="sxs-lookup"><span data-stu-id="f6b5d-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
