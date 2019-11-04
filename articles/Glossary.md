---
title: Ord lista för Quantum Computing | Microsoft Docs
description: Ord lista för Quantum-termer
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ce15fee2be68d41f0b806be50320b562a749c3b7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442544"
---
# <a name="quantum-computing-glossary"></a>Ord lista för Quantum Computing

|Period|Definition|
|-------------|----------|
|Angränsande|Den komplexa konjugats transponeren för åtgärden. För åtgärder som implementerar en enhetlig operatör är det intilliggande inversen till åtgärden.|
|Anropningsbara|Åtgärder och funktioner kallas gemensamt för *callables*.|
|Standard|Åtgärder och funktioner som definieras i Q # bygger på den logik som definierats i inledning. Standard biblioteks implementeringen är oberoende med avseende på mål datorer.|
|Clifford-grupp|Den uppsättning åtgärder som upptar octants för Bloch-sfären. Dessa omfattar: `X`, `Y`, `Z`, `H` och `S`|
|Styr|En Quantum-åtgärd som tar en eller flera qubits som aktiveringar för mål åtgärden.|
|Dirac-notation|En stenografisk representation av Quantum-tillstånd. Mer information finns i avsnittet [Dirac notation](xref:microsoft.quantum.concepts.dirac) .|
|Eigenvalues och Eigenvectors|Mer information finns i [avsnittet avancerad matris](xref:microsoft.quantum.concepts.matrix-advanced) .|
|EPR-par|Kallas även för [klock status](https://en.wikipedia.org/wiki/Bell_state)|
|Utveckling|Hur statusen ändras med tiden. Se avsnittet <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> ett exempel. |
|Funktion|Rent klassiska rutiner på språket Q #|
| <a id="global-phase"></a>Global fas | Två tillstånd som är identiska med en multipel av ett komplext tal $e ^ {i\phi} $ har sagts upp i en global fas. Till skillnad från lokala faser går det inte att observera globala faser genom eventuella mått. Mer information finns i [Pauli-mått](xref:microsoft.quantum.concepts.pauli) . |
|Mått|Hämta en klassisk bit från en qubit (eller en uppsättning qubits). Mer information finns i avsnittet [qubit Concepts](xref:microsoft.quantum.concepts.qubit) .|
|Föränderlig|En variabel vars värde kan ändras efter att det har skapats.|
|Namnområde|En etikett för en samling relaterade namn (vanligt vis drift, funktioner och typer). Till exempel kan namn området [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) etiketter alla symboler som definierats i standard biblioteket som hjälper till att förbereda de ursprungliga tillstånden.|
|Åtgärd|Den grundläggande enheten för Quantum-körning i Q #. Det är ungefär samma sak som en funktion i C, C++ eller Python, eller en statisk metod i C# eller Java.|
|Operatörs program|Utföra en Quantum-åtgärd. Detta använder vanligt vis en enhetlig matris till den aktuella läges vektorn. Mer information finns i [Introduktion till Quantum-koncept](xref:microsoft.quantum.concepts.intro) .|
|Oracle|En subrutin som tillhandahåller data beroende information till en Quantum-algoritm vid körning. Målet är vanligt vis att ge en superposition av utdata som motsvarar indata som är i position.   |
|Partiellt program|Anropa en funktion eller åtgärd utan alla nödvändiga parametrar. Returnerar en ny uppringning som bara behöver de saknade parametrarna som anges under ett framtida program.|
|Pauli-operatörer|`X`, `Y` och `Z` Quantum-grindar.|
|Inledning|Uppsättningen primitiva och klassiska åtgärder och funktioner som definieras av varje enskild måldator, i stället för på Q #-nivå.|
|Quantum-krets|En representation av ett program för en Quantum-dator. Mer information finns i avsnittet <xref:microsoft.quantum.concepts.circuits>.|
|Quantum-tillstånd|En representation av qubits i systemet. Detta är vanligt vis betecknat som en komplex kolumn vektor. Mer information finns i <xref:microsoft.quantum.concepts.vectors>. |
|qubit|Enhet för Quantum Storage. Mer information finns i avsnittet <xref:microsoft.quantum.concepts.qubit>.|
|Upprepa-tills-lyckades|En Quantum-algoritm som probabilistically lyckas. Vid ett haveri försök att genomföra rutinen igen förrän det lyckades (eller en gräns har nåtts). |
|Program varu stack|Den fullständiga uppsättningen av klassiska program och Quantum-program samt de kompilatorer, simulatorer och körningar som krävs för att använda en Quantum-dator. Mer information finns i avsnittet <xref:microsoft.quantum.concepts.software-stack>. |
|Måldator|Ett Compilation Target som sänker ett abstrakt Quantum-program mot maskin vara eller simulering. Detta omfattar vanligt vis åter skrivningar för många olika sätt, inklusive porttyp, kodning för fel korrigering, geometrisk layout och andra.|
|Tupel|Kommaavgränsade typer grupperas tillsammans med parentes. |
|Användardefinierad typ|Samling inbyggda eller tidigare definierade typer som kan kallas en enskild enhet.|

