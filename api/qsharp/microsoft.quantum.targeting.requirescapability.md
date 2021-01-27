---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability-användardefinierad typ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855156"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability-användardefinierad typ

Namnrymd: [Microsoft. Quantum. Target](xref:Microsoft.Quantum.Targeting)

Paket: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Compile-känt attribut som används för att markera ett anrop med de körnings funktioner som krävs.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Namngivna objekt

### <a name="level--string"></a>Nivå: [sträng](xref:microsoft.quantum.lang-ref.string)

Namnet på den körnings kapacitets nivå som krävs för anropet.
### <a name="reason--string"></a>Orsak: [sträng](xref:microsoft.quantum.lang-ref.string)

En beskrivning av varför anropet kräver denna körnings funktion.

## <a name="remarks"></a>Kommentarer

Det här attributet läggs automatiskt till callables av kompilatorn, om inte en instans av det här attributet redan finns på det anrop som kan anropas. Den bör inte användas förutom i sällsynta fall där kompilatorn inte härleder den nödvändiga funktionen korrekt.

Nedan visas en lista med namn på kapacitets nivåer, i ökande funktioner eller minskning av begränsningar:

## `"BasicQuantumFunctionality"`

Mått resultatet kan inte jämföras med likhet.

## `"BasicMeasurementFeedback"`

Mått resultat kan bara jämföras med likhets uttryck i IF-Statements villkorliga uttryck i åtgärder. Blocket i en If-instruktion som är beroende av ett resultat kan inte innehålla set-instruktioner för föränderligt-variabler som deklareras utanför blocket eller Return-instruktioner.

## `"FullComputation"`

Inga körnings begränsningar. Alla Q #-program kan köras.