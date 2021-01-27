---
title: Läser in klassiska data
description: Lär dig hur du läser in en egen data uppsättning för att träna en klassificerings modell med Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856456"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="016f1-103">Läs in och klassificera dina egna data uppsättningar</span><span class="sxs-lookup"><span data-stu-id="016f1-103">Load and classify your own datasets</span></span>

<span data-ttu-id="016f1-104">I den här korta självstudien ska vi lära dig hur du läser in din egen data uppsättning för att träna en klassificerings modell med Quantum Development Kit (QDK).</span><span class="sxs-lookup"><span data-stu-id="016f1-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="016f1-105">Vi rekommenderar starkt att du använder ett standardiserat serialiserat format, till exempel [JSON-filer](https://en.wikipedia.org/wiki/JSON) , för att lagra dina data.</span><span class="sxs-lookup"><span data-stu-id="016f1-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="016f1-106">Sådana format ger hög kompatibilitet med olika ramverk som python och .NET-eko systemet.</span><span class="sxs-lookup"><span data-stu-id="016f1-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="016f1-107">Vi rekommenderar särskilt att du använder vår mall för att läsa in data, så att du kan kopiera och klistra in koden direkt från exemplen.</span><span class="sxs-lookup"><span data-stu-id="016f1-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="016f1-108">Mall för att läsa in dina data uppsättningar</span><span class="sxs-lookup"><span data-stu-id="016f1-108">Template for loading your datasets</span></span>

<span data-ttu-id="016f1-109">Anta att vi har en tränings data uppsättning $ (x, y) $ med storlek $N = $2 där varje instans $x _i $ $x $ har tre funktioner: $x _ {I1} $, $x _ {I2} $ och $x _ {i3} $.</span><span class="sxs-lookup"><span data-stu-id="016f1-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="016f1-110">Verifierings data uppsättningen har samma struktur.</span><span class="sxs-lookup"><span data-stu-id="016f1-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="016f1-111">Dessa datsets kan representeras av en `data.json` fil som liknar följande:</span><span class="sxs-lookup"><span data-stu-id="016f1-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a><span data-ttu-id="016f1-112">Exempel som använder mallen</span><span class="sxs-lookup"><span data-stu-id="016f1-112">Example using the template</span></span>

<span data-ttu-id="016f1-113">Anta att vi har en liten data uppsättning med höjd och vikt för olika katter och hundar.</span><span class="sxs-lookup"><span data-stu-id="016f1-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="016f1-114">Den här data uppsättningen är mycket liten för att träna en modell, men det räcker att Visa processen för att läsa in en data uppsättning.</span><span class="sxs-lookup"><span data-stu-id="016f1-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="016f1-115">Höjd (m)</span><span class="sxs-lookup"><span data-stu-id="016f1-115">Height (m)</span></span> | <span data-ttu-id="016f1-116">Weight (kg)</span><span class="sxs-lookup"><span data-stu-id="016f1-116">Weight (kg)</span></span> | <span data-ttu-id="016f1-117">Animalie</span><span class="sxs-lookup"><span data-stu-id="016f1-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="016f1-118">0,54</span><span class="sxs-lookup"><span data-stu-id="016f1-118">0.54</span></span>      | <span data-ttu-id="016f1-119">30</span><span class="sxs-lookup"><span data-stu-id="016f1-119">30</span></span>         | <span data-ttu-id="016f1-120">Hunden</span><span class="sxs-lookup"><span data-stu-id="016f1-120">Dog</span></span>    |
| <span data-ttu-id="016f1-121">0,30</span><span class="sxs-lookup"><span data-stu-id="016f1-121">0.30</span></span>      | <span data-ttu-id="016f1-122">8</span><span class="sxs-lookup"><span data-stu-id="016f1-122">8</span></span>          | <span data-ttu-id="016f1-123">Katt</span><span class="sxs-lookup"><span data-stu-id="016f1-123">Cat</span></span>    |
| <span data-ttu-id="016f1-124">0,91</span><span class="sxs-lookup"><span data-stu-id="016f1-124">0.91</span></span>      | <span data-ttu-id="016f1-125">44</span><span class="sxs-lookup"><span data-stu-id="016f1-125">44</span></span>         | <span data-ttu-id="016f1-126">Hunden</span><span class="sxs-lookup"><span data-stu-id="016f1-126">Dog</span></span>    |
| <span data-ttu-id="016f1-127">0,86</span><span class="sxs-lookup"><span data-stu-id="016f1-127">0.86</span></span>      | <span data-ttu-id="016f1-128">31</span><span class="sxs-lookup"><span data-stu-id="016f1-128">31</span></span>          | <span data-ttu-id="016f1-129">Hunden</span><span class="sxs-lookup"><span data-stu-id="016f1-129">Dog</span></span>    |
| <span data-ttu-id="016f1-130">0,32</span><span class="sxs-lookup"><span data-stu-id="016f1-130">0.32</span></span>      | <span data-ttu-id="016f1-131">5</span><span class="sxs-lookup"><span data-stu-id="016f1-131">5</span></span>         | <span data-ttu-id="016f1-132">Katt</span><span class="sxs-lookup"><span data-stu-id="016f1-132">Cat</span></span>    |
| <span data-ttu-id="016f1-133">0,25</span><span class="sxs-lookup"><span data-stu-id="016f1-133">0.25</span></span>      | <span data-ttu-id="016f1-134">4</span><span class="sxs-lookup"><span data-stu-id="016f1-134">4</span></span>          | <span data-ttu-id="016f1-135">Katt</span><span class="sxs-lookup"><span data-stu-id="016f1-135">Cat</span></span>    |

<span data-ttu-id="016f1-136">Processen är:</span><span class="sxs-lookup"><span data-stu-id="016f1-136">The process is:</span></span>

- <span data-ttu-id="016f1-137">Först måste vi separera data uppsättningen till utbildning och verifiering.</span><span class="sxs-lookup"><span data-stu-id="016f1-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="016f1-138">I det här fallet kan vi bara ta de tre första exemplen för utbildning och resten av exemplen för verifiering.</span><span class="sxs-lookup"><span data-stu-id="016f1-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="016f1-139">I allmänhet är det en bra idé att slumpmässigt testa inlärnings-och validerings data uppsättningen för att undvika oönskade kompensationer i tränings data.</span><span class="sxs-lookup"><span data-stu-id="016f1-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="016f1-140">För det andra måste vi tilldela en numerisk etikett till varje klass.</span><span class="sxs-lookup"><span data-stu-id="016f1-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="016f1-141">Observera att för tillfället QML-biblioteket endast admits binära klassificerings problem.</span><span class="sxs-lookup"><span data-stu-id="016f1-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="016f1-142">Vi kommer att tilldela etiketten 0 till klassen `Dog` och siffran 1 till klassen `Cat` .</span><span class="sxs-lookup"><span data-stu-id="016f1-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="016f1-143">Slutligen fyller vi mallen med hjälp av data från vår data uppsättning.</span><span class="sxs-lookup"><span data-stu-id="016f1-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="016f1-144">Observera att för stora data uppsättningar bör du skapa ett litet skript för att automatiskt generera mallen från din specifika data uppsättning.</span><span class="sxs-lookup"><span data-stu-id="016f1-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="016f1-145">Det här skriptet beror på data uppsättningens ursprungliga format.</span><span class="sxs-lookup"><span data-stu-id="016f1-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="016f1-146">För vår data uppsättning `data.json` är filen:</span><span class="sxs-lookup"><span data-stu-id="016f1-146">For our dataset the `data.json` file is:</span></span>

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a><span data-ttu-id="016f1-147">Läsa in data</span><span class="sxs-lookup"><span data-stu-id="016f1-147">Loading the data</span></span>

<span data-ttu-id="016f1-148">När du har serialiserat dina data som en JSON-fil kan du läsa in dem i med hjälp av JSON-bibliotek som ingår i det valda värd språket.</span><span class="sxs-lookup"><span data-stu-id="016f1-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="016f1-149">Python</span><span class="sxs-lookup"><span data-stu-id="016f1-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="016f1-150">Python tillhandahåller det [inbyggda `json` paketet](https://docs.python.org/3.7/library/json.html) för att arbeta med JSON-serialiserade data:</span><span class="sxs-lookup"><span data-stu-id="016f1-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="016f1-151">C#</span><span class="sxs-lookup"><span data-stu-id="016f1-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="016f1-152">.NET Core Platform tillhandahåller [ `System.Text.Json` paketet](https://www.nuget.org/packages/System.Text.Json) för att arbeta med JSON-serialiserade data:</span><span class="sxs-lookup"><span data-stu-id="016f1-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="016f1-153">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="016f1-153">Next steps</span></span>

<span data-ttu-id="016f1-154">Nu är du redo att börja köra dina egna experiment med dina egna data uppsättningar.</span><span class="sxs-lookup"><span data-stu-id="016f1-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="016f1-155">Prova olika klassificerare och data uppsättningar och bidra till communityn som delar dina resultat!</span><span class="sxs-lookup"><span data-stu-id="016f1-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
