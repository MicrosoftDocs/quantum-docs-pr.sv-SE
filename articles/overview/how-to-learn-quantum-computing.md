---
title: Hur lär man sig kvantberäkning med Q#?
description: ''
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.learn
ms.openlocfilehash: 53682ae8ab9cb31fa0de68832cb3574aa4e30216
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529966"
---
# <a name="how-to-learn-quantum-computing"></a>Hur lär man sig kvantberäkning?

Få vägledning om hur du lär dig mer om kvantberäkning och skriv dina första program. Den här guiden är inte heltäckande, men en bra plats att börja på.

## <a name="getting-started-overview"></a>Komma igång: Översikt

I [Kom igång med Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome) får du en översikt på hög nivå av kvantberäkning med Q#, inklusive självstudier där du skriver ditt första Q#-program, komma igång-guider och en introduktion till Q#-kvantbiblioteken för att utveckla kvantprogram.

## <a name="learning-the-basics-what-do-you-need-to-know"></a>Lära sig grunderna: Vad behöver du kunna?

Du behöver inte kunna kvantfysik för att lära dig mer om Q# och kvantberäkning, eller börja skriva kvantprogram.

De här begreppen ger dig en bra introduktion till den grundläggande kunskap som du behöver ha för att börja koda kvantprogram.  

* [Grundläggande kvantmekanik](xref:microsoft.quantum.concepts.intro): Vi sade nyss att du inte behöver kunna kvantfysik för att börja koda (och det är sant!). Men vissa grundläggande begrepp inom kvantmekanik och dess matematiska notation är användbara om du ska förstå kvantprogrammering.

* **Linjär algebra (vektorer och matriser)** : Inom kvantberäkning representeras kvanttillstånd av vektorer, där kvantåtgärderna är linjära omvandlingar som tillämpas på dessa vektorer.  Här är en [Jupyter Notebook-självstudie om linjär algebra](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra).  Du kan också läsa mer om linjär algebra i vår begreppsguide om [vektorer och matriser](xref:microsoft.quantum.concepts.vectors).

* **Komplex aritmetik**: Koefficienterna för kvanttillståndsvektorer är komplexa tal. Du kan förstå några grundläggande kvantberäkningsbegrepp utan dem, men du kommer inte långt innan du behöver lägga till dem i din kvantverktygslåda.  Här är en [Jupyter Notebook-självstudie om komplex aritmetik](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic) som förklarar en del av den matematiska bakgrund som krävs när man arbetar med kvantberäkning. 

Nu när du har grunderna kan du börja lära dig att skriva kvantprogram.  Det finns flera sätt att gå vidare på:

## <a name="do-the-quantum-katas"></a>Använd Quantum Katas

[Quantum Katas](xref:microsoft.quantum.overview.katas) är vår serie med öppen källkod som innehåller självstudier i egen takt. Du lär dig både de olika delarna inom kvantberäkning och Q#-programmering på samma gång.  Varje Kata hänvisar till ytterligare utbildningsmaterial som du kan använda för att lära dig de kvantberäkningsbegrepp som behövs för att slutföra övningen.  

## <a name="dive-into-the-theory"></a>Fördjupa dig i teorin

Du kanske vill ta en djupare titt på teorin inom kvantmekanik och kvantberäkning. Här finns en lista med användbart material:

* Börja med vår guide till [kvantberäkningsbegrepp](xref:microsoft.quantum.concepts.intro), en sammanställning av grundläggande begrepp inom kvantberäkning.
* I _Learn Quantum Computing with Python and Q#_ (Sarah C. Kaiser och Christopher E. Granade) finns en utmärkt introduktion för personer som har lite eller ingen erfarenhet av kvantmekanik, men viss programmeringsbakgrund.
* _Quantum Computation and Quantum Information_ (Michael A. Nielsen, Isak L. Chuang) är den mest citerade texten inom fältet för kvantberäkning och anses vara standardtexten om ämnet. Boken förutsätter minimalt med tidigare erfarenhet av kvantmekanik och datorvetenskap. Den är ett utmärkt val för både läsare som vill ha en grundlig introduktion till ämnet och för läsare som söker efter referenser till avancerade begrepp.
* MIT OpenCourseWare har en utmärkt [onlinekurs](https://www.youtube.com/watch?v=lZ3bPUKo5zc&list=PLUl4u3cNGP61-9PEhRognw5vryrSEVLPr) med Allan Adams som lär dig grunderna i kvantmekanik. Den är perfekt för utvecklare som vill ha en bättre förståelse för den underliggande fysiken.

## <a name="join-the-quantum-community"></a>Gå med i kvantcommunityn

Du behöver inte vara ensam när du lär dig detta, det finns en stor community med amatörer och experter som är villiga att hjälpa dig. Var inte rädd för att ställa frågor!

* Om du har frågor om Q# eller kvantberäkning, tveka inte utan gå till webbplatsen Quantum Computing StackExchange. Om du inte hittar något svar på din fråga kan du alltid ställa en ny. 
* I [Q#-bloggen](https://devblogs.microsoft.com/qsharp/) och [Microsoft Quantum-bloggen](https://cloudblogs.microsoft.com/quantum/) kan du hålla dig uppdaterad med de senaste nyheterna och resurserna om Q#.
* I [Q#-communityn](https://qsharp.community/) och [Awesome Q#](https://project-awesome.org/ebraminio/awesome-qsharp) kan du söka efter fler resurser och material.

 Om du ska vara lärare i en kurs om kvantberäkning kan du få hjälp i [Microsoft Quantum Network](https://info.microsoft.com/LearnMoreAboutMicrosoftQuantumNetwork.html).  

