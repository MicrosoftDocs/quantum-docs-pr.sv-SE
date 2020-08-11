---
title: Introduktion till kvantberäkning
description: Lär dig mer om kvantberäkning, vad kvantdatorer kan utföra och hur du lär dig kvantberäkning.
author: bradben
ms.author: bradben
ms.date: 05/05/2020
ms.topic: overview
uid: microsoft.quantum.overview.introduction
no-loc:
- Q#
- $$v
ms.openlocfilehash: 59cb595ac207d6e84358fc6ba742e0e0019c76f9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866987"
---
# <a name="introduction-to-quantum-computing-and-the-quantum-development-kit"></a>Introduktion till kvantberäkning och Quantum Development Kit

Microsoft Quantum Development Kit (QDK) är en uppsättning verktyg med öppen källkod som hjälper utvecklare att lära sig kvantalgoritmer och skriva kvantprogram. Kvantdatorer har potentialen att lösa några av världens största utmaningar – inom miljö, jordbruk, sjukvård, energi, klimat, materialvetenskap och andra områden som ligger i framtiden.  

Vissa av dessa problem är svårlösta även för de mest kraftfulla datorerna. Kvantteknik har precis börjat påverka databeräkningsvärlden men kan komma att ändra vårt sätt att betrakta beräkning i grunden.

## <a name="what-is-quantum-computing"></a>Vad är kvantberäkning?

I dag syftar ordet ”kvant” på den minsta möjliga diskreta enheten för fysiska egenskaper, vanligtvis gällande egenskaper hos partiklar på eller under atomnivå. Kvantdatorer använder faktiska kvantpartiklar, artificiella atomer eller kollektiva egenskaper hos kvantpartiklar som beräkningsenheter. Dessa maskiner är stora, komplexa och dyra.

Kvantdatorer drar nytta av kvantfysikens unika egenskaper och tillämpar dem på beräkning. De introducerar nya begrepp till traditionella programmeringsmetoder via fenomen inom kvantfysik såsom superposition, sammanflätning och kvantinterferens.

## <a name="what-can-a-quantum-computer-do"></a>Vad kan en kvantdator göra?

Kvantdatorer är inte superdatorer som kan göra allt snabbare, men det finns några områden som kvantdatorer är mycket lämpade för.

- [Kvantsimulering](xref:microsoft.quantum.overview.introduction#quantum-simulation)
- [Kryptografi](xref:microsoft.quantum.overview.introduction#cryptography-and-shors-algorithm)
- [Sök](xref:microsoft.quantum.overview.introduction#search-and-grovers-algorithm)
- [Optimering](xref:microsoft.quantum.overview.introduction#quantum-inspired-computing-and-optimization)
- [Maskininlärning](xref:microsoft.quantum.overview.introduction#quantum-machine-learning)

## <a name="quantum-simulation"></a>Kvantsimulering

Eftersom kvantdatorer använder kvantfenomen inom beräkning passar de bra för modellering av andra kvantsystem. Fotosyntes, supraledning och komplexa molekylära formationer är exempel på kvantmekanismer som kvantprogram kan simulera.

## <a name="cryptography-and-shors-algorithm"></a>Kryptografi och Shors algoritm

År 1994 visade Peter Shor att en skalbar kvantdator skulle kunna bräcka populära krypteringstekniker, till exempel RSA-algoritmen. Klassisk kryptografi är beroende av svårigheten att lösa problem såsom heltalsfaktorisering eller diskreta logaritmer. Många av dessa kan lösas på effektivare sätt med hjälp av kvantdatorer.

## <a name="search-and-grovers-algorithm"></a>Sökning och Grovers algoritm

År 1996 utvecklade Lov Grover en kvantalgoritm som gjorde lösningen på ostrukturerade datasökningar betydligt snabbare. Sökningen kunde köras med färre steg än vad som var möjligt med klassiska algoritmer.

## <a name="quantum-inspired-computing-and-optimization"></a>Kvantinspirerad beräkning och optimering

Kvantinspirerade algoritmer använder kvantprinciper för att ge högre hastighet och noggrannhet, men de implementeras i klassiska datorsystem. Den här metoden gör att utvecklare kan utnyttja kraften hos nya kvantmetoder redan i dag utan att vänta på att kvantmaskinvara, som fortfarande är en ny bransch, ska bli tillgänglig.

Optimering är processen för att hitta den bästa lösningen på ett problem baserat på önskat resultat och gällande begränsningar. Faktorer som kostnad, kvalitet eller produktionstid väger in vid viktiga beslut inom branscher och forskning. Kvantinspirerade optimeringsalgoritmer som körs på dagens klassiska datorer kan hitta lösningar som hittills inte varit möjliga. Utöver optimering av trafikflödet för att minska trafikstockning går det att hantera flygterminaler, paketleveranser, schemaläggning av jobb med mera. Tack vare genombrott inom materialvetenskapen kommer det att finnas nya energikällor, batterier med större kapacitet samt lättare och starkare material.

> [!NOTE]
> Läs mer om hur Microsofts kvantinspirerade beräkning används inom [materialvetenskap](https://cloudblogs.microsoft.com/quantum/2020/01/21/oti-lumionics-accelerating-materials-design-microsoft-azure-quantum/), [riskhantering](https://cloudblogs.microsoft.com/quantum/2019/05/22/microsoft-quantum-collaborates-with-willis-towers-watson-to-transform-risk-management-solutions/) och [medicin](https://blogs.microsoft.com/blog/2018/05/18/microsoft-quantum-helps-case-western-reserve-university-advance-mri-research/).

## <a name="quantum-machine-learning"></a>Kvantmaskininlärning

Maskininlärning på klassiska datorer är i full färd med att revolutionera både vetenskap och företagsvärlden. Den höga beräkningskostnaden för att träna modeller bromsar dock områdets utveckling och omfattning. I den här delen av kvantmaskininlärning lär du dig hur du utformar och implementerar kvantprogramvara som möjliggör maskininlärning som körs snabbare än med klassiska datorer.

I Quantum Development Kit ingår [biblioteket för kvantmaskininlärning](xref:microsoft.quantum.machine-learning.concepts.intro), som ger dig möjlighet att köra kvantbaserade/klassiska hybridinlärningsexperiment. Biblioteket innehåller exempel och självstudier samt de verktyg som behövs för att implementera en ny kvantbaserad/klassisk hybridalgoritm, den kretsbaserade kvantklassificeraren, för att lösa övervakade klassificeringsproblem.

## <a name="no-locq-and-the-microsoft-quantum-development-kit-qdk"></a>Q# och Microsoft Quantum Development Kit (QDK)

Q# är Microsofts programmeringsspråk med öppen källkod för utveckling och körning av kvantalgoritmer. Det ingår i [QDK](https://docs.microsoft.com/quantum/), en komplett development kit för Q# som du kan använda med standardmässiga verktyg och språk för att utveckla kvantprogram som du kan köra i olika miljöer, inklusive den inbyggda kvantsimulatorn med fullständigt tillstånd.

Det finns tillägg för Visual Studio och VS Code samt paket som ska användas med Python och Jupyter Notebook.

QDK innehåller ett standardbibliotek och specialiserade bibliotek för kemi, maskininlärning och tal.

Dokumentationen omfattar en Q#-språkguide, självstudier och exempelkod som hjälper dig att komma igång snabbt samt innehållsrika artiklar med mer ingående information om begrepp inom kvantberäkning.  

## <a name="microsoft-quantum-hardware-partners"></a>Microsofts kvantmaskinvarupartner

Microsoft samarbetar med kvantmaskinvaruföretag för att ge utvecklare molnåtkomst till kvantmaskinvara. Genom att dra nytta av [Azure Quantum](https://azure.microsoft.com/services/quantum/)-plattformen och språket Q# kan utvecklare utforska kvantalgoritmer och köra sina kvantprogram på olika typer av kvantmaskinvara.

Både [IonQ](https://ionq.com/news/november-4-2019-microsoft-partnership) och [Honeywell](https://www.honeywell.com/en-us/newsroom/news/2019/11/the-future-of-quantum-computing) använder **fångad jon**-baserade processorer är enskilda joner är fångade i ett elektroniskt fält, medan [QCI](https://quantumcircuits.com/news-and-publications/quantum-circuits-partners-with-microsoft-on-azure-quantum) använder supraledande kretsar.

## <a name="next-steps"></a>Nästa steg

[Viktiga begrepp inom kvantberäkning](xref:microsoft.quantum.overview.understanding)
[Snabbstarter](xref:microsoft.quantum.welcome)