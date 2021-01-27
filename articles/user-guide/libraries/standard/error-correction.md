---
title: Fel korrigering i Q# standard biblioteken
description: Lär dig hur du använder fel när du korrigerar koder i dina Q# program samtidigt som du skyddar qubits-tillstånd.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc8e46aa22cb2575de42cfc3d4f57c43e5d3f7b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857212"
---
# <a name="error-correction"></a>Fel korrigering #

## <a name="introduction"></a>Introduktion ##

I klassisk data behandling, om en vill skydda en bit mot fel, kan det ofta räcka att representera den biten av en *logisk bit* genom att upprepa data biten.
Låt säga att $ \overline {0} = $0 är kodningen för data bit 0, där vi använder en rad ovanför etiketten 0 för att ange att den är en kodning av en bit i status 0.
Om vi på liknande sätt meddelar $ \overline {1} = $111, har vi en enkel upprepnings kod som skyddar mot ett fel i en bit-flip.
Det vill säga om någon av de tre bitarna är vänd, kan vi återställa statusen för den logiska biten genom att göra en majoritets röst.
Även om den klassiska fel korrigeringen är en mycket rikare del som det här exemplet (vi rekommenderar att du använder rad [Introduktion till kodnings teori](https://www.springer.com/us/book/9783540641339)), pekar upprepnings koden ovan redan på ett möjligt problem med att skydda Quantum-information.
Dvs. [no-kloning-satsen](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) innebär att om vi mäter varje enskild qubit och tar en majoritets röst enligt den klassiska koden ovan, har vi förlorat den exakta informationen som vi försöker skydda.

I inställningen Quantum ser vi att mätningen är problematisk. Vi kan fortfarande implementera kodningen ovan.
Det är praktiskt att göra detta för att se hur vi kan generalisera fel korrigering i Quantum-fallet.
Låt säga att $ \ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket {0} \otimes \ket {0} $ och låt $ \ket{\overline {1} } = \ket {111} $.
Efter linearitet har vi definierat vår upprepnings kod för alla indata. till exempel $ \ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} })/\sqrt {2} = (\ket {000} + \ket {111} )/\sqrt {2} $.
I synnerhet, med ett fel $X _1 $ Act på den mellersta qubit, ser vi att den korrigering som behövs i båda grenarna är exakt $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \left (X_1 \ket {000} + X_1 \ket {111} \right) \\ \\ & = \frac {1} {\sqrt {2} } \left (\ket {010} + \ket {101} \right).
\end{align} $ $

Om du vill se hur vi kan identifiera att detta är fallet utan att mäta det mycket tillstånd vi försöker skydda, är det bra att skriva ned vad de olika bit vändningarna gör till våra logiska tillstånd:

| Fel $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ |
| $X _0 $ | $ \ket {100} $ | $ \ket {011} $ |
| $X _1 $ | $ \ket {010} $ | $ \ket {101} $ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ |

För att skydda det tillstånd som vi kodar måste vi kunna särskilja de tre felen från varandra och från identiteten $ \boldone $ utan att skilja mellan $ \ket{\overline {0} } $ och $ \ket{\overline {1} } $.
Om vi t. ex. mäter $Z _0 $ får vi ett annat resultat för $ \ket{\overline {0} } $ och $ \ket{\overline {1} } $ i No-Error-fallet, så att komprimerar det kodade läget.
Å andra sidan kan du överväga att mäta $Z _0 Z_1 $, pariteten för de två första bitarna i varje beräknings grund tillstånd.
Kom ihåg att varje mätning av en Pauli-operatör kontrollerar vilken eigenvalue som det tillstånd som mäts motsvarar, så för varje tillstånd $ \ket{\psi} $ i tabellen ovan kan vi beräkna $Z _0 Z_1 \ket{\psi} $ för att se om vi får $ \pm\ket{\psi} $.
Observera att $Z _0 Z_1 \ket {000} = \ket {000} $ och att $Z _0 Z_1 \ket {111} = \ket {111} $, så att den här mätningen gör samma sak i både kodade tillstånd.
Å andra sidan $Z _0 Z_1 \ket {100} =-\ket {100} $ och $Z _0 Z_1 \ket {011} =-\ket {011} $, så resultatet av att mäta $Z _0 Z_1 $ visar användbar information om vilket fel som har inträffat.

För att framhäva detta upprepas tabellen ovan, men du kan lägga till resultaten från Mät $Z _0 Z_1 $ och $Z _1 Z_2 $ på varje rad.
Vi betecknar resultaten av varje mätning genom tecknet för det eigenvalue som observeras, antingen $ + $ eller $-$, som motsvarar respektive Q# `Result` `Zero` `One` respektive.

| Fel $E $ | $E \ket{\overline {0} } $ | $E \ket{\overline {1} } $ | Resultat av $Z _0 Z_1 $ | Resultat av $Z _1 Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket {000} $ | $ \ket {111} $ | $+$ | $+$ |
| $X _0 $ | $ \ket {100} $ | $ \ket {011} $ | $-$ | $+$ |
| $X _1 $ | $ \ket {010} $ | $ \ket {101} $ | $-$ | $-$ |
| $X _2 $ | $ \ket {001} $ | $ \ket {110} $ | $+$ | $-$ |

Det innebär att resultaten av de två mätningarna unikt avgör vilken bit-flip-fel som inträffade, men utan att avslöja någon information om vilket tillstånd vi kodade.
Vi kallar dessa resultat en *Syndrome* och refererar till processen för att mappa en Syndrome tillbaka till det fel som orsakade *återställningen*.
I synnerhet betonar vi att återställningen är en *klassisk* härlednings process som tar sig in i den Syndrome som inträffat, och returnerar en recept för att åtgärda eventuella fel som kan ha inträffat.

> [!NOTE]
> Bit-flip-koden ovan kan endast korrigeras mot enstaka fel i en bit. det vill säga en `X` åtgärd som agerar på en enda qubit.
> `X`Om du använder mer än en qubit mappas $ \ket{\overline {0} } $ till $ \ket{\overline {1} } $ efter återställningen.
> På samma sätt kommer du att använda en fas vändning `Z` -åtgärd för att mappa $ \ket{\overline {1} } $ till $-\ket{\overline {1} } $ och därmed mappa $ \ket{\overline{+}} $ till $ \ket{\overline {-} } $.
> Ofta kan koder skapas för att hantera större antal fel och för att hantera $Z $-fel samt $X $-fel.

Insikter om att vi kan beskriva mätningar i en Quantum-fel korrigering som fungerar på samma sätt i alla kod stater, är grunden för den *stabiliseringsbaserade formaliteten*.
Q#Canon innehåller ett ramverk för att beskriva kodning i och avkodning från stabiliserings koder och för att beskriva hur en återställning av fel uppstår.
I det här avsnittet beskriver vi det här ramverket och dess program till några vanliga Quantum Error-felkorrigerings koder.

> [!TIP]
> En fullständig introduktion till stabiliserings-och stabiliserings funktionen ligger utanför det här avsnittets omfattning.
> Vi refererar till läsare som är intresserade av att lära sig mer till [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-no-locq"></a>Motsvarar fel korrigerings koder i Q# ##

För att hjälpa till att ange fel som korrigerar koder Q# ger Canon flera olika användardefinierade typer:

- <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister>`= Qubit[]`: Anger att ett register över qubits ska tolkas som kod block för en felkorrigerande kod.
- <xref:Microsoft.Quantum.ErrorCorrection.Syndrome>`= Result[]`: Anger att en matris med mått resultat ska tolkas som Syndrome mätt i ett kodblock.
- <xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn>`= (Syndrome -> Pauli[])`: Anger att en *klassisk* funktion ska användas för att tolka en Syndrome och returnera en korrigering som ska tillämpas.
- <xref:Microsoft.Quantum.ErrorCorrection.EncodeOp>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Anger att en åtgärd tar qubits som representerar data tillsammans med nya Ancilla-qubits för att skapa ett kodblock av en felkorrigerande kod.
- <xref:Microsoft.Quantum.ErrorCorrection.DecodeOp>`= (LogicalRegister => (Qubit[], Qubit[]))`: Om en åtgärd är indelad i ett kod block av ett fel korrigeras koden i data qubits och Ancilla-qubits som används för att representera Syndrome-information.
- <xref:Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp>`= (LogicalRegister => Syndrome)`: Anger en åtgärd som ska användas för att extrahera Syndrome-information från ett kodblock utan att störa det tillstånd som skyddas av koden.

Dessutom tillhandahåller Canon <xref:Microsoft.Quantum.ErrorCorrection.QECC> typen för att samla in de andra typerna som krävs för att definiera en kod för Quantum-fel korrigering. Associerad med varje stabiliserings-Quantum-kod är kod längden $n $, antalet $k $ för logiska qubits och minsta avstånd $d $, som ofta grupperas tillsammans i notationen ⟦ $n $, $k $, $d $ ⟧. Funktionen definierar t. ex. <xref:Microsoft.Quantum.ErrorCorrection.BitFlipCode> ⟦ 3, 1, 1 ⟧ bit flip Code:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Observera att `QECC` typen *inte* innehåller någon återställnings funktion.
Detta gör att vi kan ändra den återställnings funktion som används i korrigerande fel utan att ändra definitionen för själva koden. den här funktionen är särskilt användbar när du införlivar feedback från karakteriserings mätningar i modellen som antas av återställningen.

När en kod har definierats på det här sättet kan vi använda <xref:Microsoft.Quantum.ErrorCorrection.Recover> åtgärden för att återställa från fel:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Vi utforskar detta mer detaljerat i [kod exemplet bit flip](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code).

Från bit-flip-koden Q# tillhandahålls Canon med implementeringar av den [qubit perfekta koden](https://arxiv.org/abs/quant-ph/9602019), och [koden för sju qubit](https://arxiv.org/abs/quant-ph/9705052), som båda kan åtgärda ett godtyckligt qubit-fel.
