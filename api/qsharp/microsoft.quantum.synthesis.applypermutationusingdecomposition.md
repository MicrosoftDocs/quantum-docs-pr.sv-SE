---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 5b25ef3327bbca2dfdbe8fa876f3f797dddf77e8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192136"
---
# <a name="applypermutationusingdecomposition-operation"></a>ApplyPermutationUsingDecomposition-åtgärd

Namnrymd: [Microsoft. Quantum. syntes](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Permutes amplituderna i ett Quantum-tillstånd med en permutation med hjälp av nedbrytnings syntes.

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Beskrivning

I den här proceduren implementeras sammanfattnings metoden för nedbrytning.  Indatamängden är en permutation $ \pi $ över $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, som representerar en $n $-variabel omvänd boolesk funktion.
Algoritmen utför upprepat följande steg för varje variabel index $i $:

1. Compute $ ((\ pi_l, \ pi_r), \pi ') $ så att avbildningarna av $ \ pi_l $ och $ \ pi_r $ inte ändrar bitar i deras element i andra index än $i $ och bilder av $ \pi $ ändra inte bit $i $ i sina element.
2. Ställ in $ \pi \leftarrow \pi $ och Härled sanningen-tabeller från $ \ pi_l $ och $ \ pi_r $ baserat på element som inte är fasta punkter.

När du har tillämpat de här stegen för alla variabel index, blir den återstående permutationen $ \pi $ identiteten, och baserat på de insamlade sanningen-tabellerna och indexen, kan en använda sanningen-tabellens kontrollerade @"microsoft.quantum.intrinsic.x" åtgärder med hjälp av @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" åtgärden.

Variabeln order är $0, \dots, n-$1.  En anpassad variabel ordning kan anges i åtgärden @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .

## <a name="input"></a>Indata

### <a name="perm--int"></a>behörighet: [int](xref:microsoft.quantum.lang-ref.int)[]

En permutation av $2 ^ n $ elementen börjar från 0.


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

En lista med $n $ qubits som permutationen tillämpas på.



## <a name="output--unit"></a>Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referenser

- [*Alexis de Vos*, *Yvan van Rentergem*, adv. i matematik. 2 (2), 2008, PP. 183--200](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [*Mathias Soeken*, *Lisa Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of symbolisk beräkning 73 (2016), sid. 1--26](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a>Se även

- [Microsoft. Quantum. syntes. ApplyPermutationUsingDecompositionWithVariableOrder](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [Microsoft. Quantum. syntes. ApplyPermutationUsingTransformation](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)