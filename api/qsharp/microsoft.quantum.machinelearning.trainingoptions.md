---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions-användardefinierad typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732291"
---
# <a name="trainingoptions-user-defined-type"></a>TrainingOptions-användardefinierad typ

Namnrymd: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Paketfilerna [](https://nuget.org/packages/)


En samling alternativ som ska användas i träna Quantum-klassificerare.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Namngivna objekt

### <a name="learningrate--double"></a>Learningrate ligger: [dubbel](xref:microsoft.quantum.lang-ref.double)

Den inlärnings takt med vilken övertoningar ska skalas om när modell parametrar uppdateras under inlärnings steg.
### <a name="tolerance--double"></a>Tolerans: [dubbel](xref:microsoft.quantum.lang-ref.double)

Den ungefärliga tolerans som ska användas när du förbereder exempel i Quantum-tillstånd.
### <a name="minibatchsize--int"></a>MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)

Antalet prover som ska användas i varje minibatch för utbildning.
### <a name="nmeasurements--int"></a>NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Antalet gånger för att mäta varje klassificerings resultat för att uppskatta sannolikheten för klassificering.
### <a name="maxepochs--int"></a>MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)

Det maximala antalet epoker för att träna varje modell för.
### <a name="maxstalls--int"></a>MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)

Det maximala antalet gånger som en utbildnings värde är tillåten till bås (ungefär noll toning) innan det går.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mängden stoppade stoppade modeller innan en uppdatering görs igen.
### <a name="scoringperiod--int"></a>ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)

Det antal tonings steg som ska tas mellan Poäng poängen.
För bästa precision anger du 1.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [sträng](xref:microsoft.quantum.lang-ref.string) -> [enhet](xref:microsoft.quantum.lang-ref.unit)

En funktion som kan användas för att ge utförlig feedback.

## <a name="remarks"></a>Kommentarer

Denna UDT ska inte skapas direkt, utan bör istället anges genom @"microsoft.quantum.machinelearning.defaulttrainingoptions" att anropa och sedan använda `w/` operatorn för att åsidosätta olika standardvärden.

Om du till exempel vill använda 100 000-mått och högst 8 utbildnings epoker:

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Referenser

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)