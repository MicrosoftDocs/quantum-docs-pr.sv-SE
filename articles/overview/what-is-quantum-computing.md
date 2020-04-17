---
title: Vad är kvantberäkning?
description: En introduktion till kvantberäkningsfunktioner, algoritmer och maskinvara och Microsofts Quantum Development Kit (QDK).
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 668df50882272bfa56541f178e2f4d5fb35efcf5
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906788"
---
# <a name="what-is-quantum-computing"></a>Vad är kvantberäkning?

Det finns några problem som är så svåra och så otroligt omfattande att även om alla superdatorer i världen skulle arbeta med problemet, skulle det ändå ta längre tid än vad som finns i universum att lösa dem.

Kvantdatorer skulle kunna lösa några av planetens största utmaningar – inom miljö, jordbruk, sjukvård, energi, klimat, materialvetenskap och problem som vi ännu inte ens kan föreställa oss. Effekten av kvantdatorer kommer att vara lika omfattande som när transistorn uppfanns 1947, vilket banade väg för dagens digitala ekonomi.

Kvantberäkning utnyttjar det unika beteendet i kvantfysik i en ny och kraftfull beräkningsmodell. Teorin för kvantfysik innebär att det kan finnas en kvantnivå i en superposition i flera klassiska tillstånd. Och de olika tillstånden påverkar varandra som vågor i en tidvattensbassäng.  Aggregationstillståndet efter en mätning ”minimeras” till ett av de klassiska tillstånden. 

Om du därefter upprepar samma mätning får du samma klassiska resultat.  Kvantsammanflätning inträffar när partiklar interagerar på ett sätt som gör att de båda kvanttillstånden inte kan beskrivas fristående från varandra, även om partiklarna är fysiskt åtskilda.  

Vid kvantberäkning lagras information i aggregationstillstånd och använder sin superposition och sammanflätning till att utföra kvantåtgärder som beräknar informationen. Därigenom tar man tillvara och lär sig programmering av kvantinterferens.

Kvantberäkning kan låta skrämmande, men med rätt resurser kan du börja skapa kvantprogram redan i dag.

## <a name="the-qubit"></a>Kvantbiten

Kvantberäkningen definierar beräkningsbegrepp som återspeglar kvantbeteendet.  Kvantberäkning börjar med en kvantbit.  I kvantberäkning är en kvantbit – **qubit** – en enhet med kvantinformation, liknande en klassisk bit. Där klassiska bitar innehåller ett enda binärt värde av 0 eller 1, kan tillståndet för en kvantbit vara i en **superposition** med 0 och 1 samtidigt.  

Att mäta en kvantbit ändrar kvantbitens tillstånd. Med mätningen går kvantbiten från att vara i superposition till ett av de klassiska tillstånden.  

Flera kvantbitar kan också vara **sammanflätade**. När vi mäter en sammanflätad kvantbit får vi även veta de andra kvantbitarnas tillstånd.

## <a name="quantum-algorithms"></a>Kvantalgoritmer

Kvantalgoritmer är utformade att dra nytta av karaktären och beteendet hos kvantbitar för att göra klassiska algoritmer snabbare, eller för att få helt nya sätt att utforma fysiska system på.  Dessa algoritmer utnyttjar hur kvantbitar kodar information och den parallella användningen med flera sammanflätade kvantbitar i superposition.  

Klassiska datorer kodar information i bitar, där varje bit kodar två möjliga värden, 0 eller 1.  En kvantbit kodar två värden samtidigt, 0 och 1.  Två klassiska bitar kodar ett av fyra möjliga värden (00, 01, 10, 11), medan två kvantbitar kodar en superposition för dessa fyra tillstånd samtidigt – även om vi endast kan hämta ett av dessa värden vid mätningen. Fyra kvantbitar kodar en superposition av 16 värden samtidigt, och så vidare exponentiellt.  100 kvantbitar kan koda mer information än vad som finns tillgängligt i de största datorsystemen i dag.  

När flera sammanflätade kvantbitar agerar sammanhängande, kan de dessutom bearbeta flera alternativ samtidigt. Sammanflätade kvantbitar kan bearbeta information under en bråkdel av den tid det annars skulle ta, även av de snabbaste system som inte är kvantsystem.

Att dra nytta av dessa kvantattribut har varit målet under flera årtionden av forskning inom kvantalgoritmer och man har tagit fram flera innovativa tekniker som har visat sig kunnat lösa problem på en bråkdel av den tid det tar att lösa dem på ett klassiskt sätt.  

En av de mest berömda kvantalgoritmerna är _Shors algoritm_ för faktorisering, vilket gör att det klassiska olösbara felet vid faktorisering av ett stort tal till två primtal blir tillräckligt snabbt för att kunna utmana traditionell kryptografi.

På den mer konstruktiva sidan kan algoritmer för säker distribution av kryptografiska nycklar utföras med kvantbitsegenskaperna superposition, kvantsammanflätning och **ingen kloning**, vilket innebär att det inte går att kopiera kvantbitar utan identifiering.

_Grovers algoritm_ är en metod för kvantalgoritmer som ger en kvadratisk ökad hastighet vid sökning av ostrukturerade data.

## <a name="quantum-hardware"></a>Kvantmaskinvara

På klassiska datorer motsvarar bitar spänningsnivåerna i kiselkretsar. Maskinvara för kvantberäkning kan implementeras av många olika fysiska realiseringar av kvantbitar: fångade joner, supraledare, neutrala atomer, elektronspinn, ljuspolarisation och topologiska kvantbitar. Kvantmaskinvara är en växande teknik. Kvantbitar är känsliga av naturen och sammanhållningen minskar när de interagerar med miljön. Systemet måste kunna balansera återgivningen i systemet med skalbarhet. Ju större skala (dvs. antalet kvantbitar), desto högre är felfrekvensen.

Microsoft utvecklar en kvantdator som baseras på topologiska kvantbitar. Vi tror att en topologisk kvantbit kommer att påverkas mindre av förändringar i dess miljö, vilket minskar risken för extern felkorrigering. Funktionen i topologiska kvantbitar ger ökad stabilitet och motståndskraft mot miljöstörningar, vilket innebär att de är enklare att skala och kan vara tillförlitliga längre.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Kvantberäkning – en komplett maskinvaru- och programvarustack

Microsofts kvantprogram är unikt eftersom vi fokuserar på skalning av varje komponent i systemet för att ge en verklig kvanteffekt. Den här omfattande metoden innefattar:

* skapa en kvantdator med hjälp av tillförlitliga, skalbara och feltoleranta topologiska kvantbitar, 
* skapa ett unikt kryogeniskt kontrollplan med låg effekt och värmeavledning, 
* utveckla en komplett programvarustack som aktiverar programmering i kvantdatorn och som kontrollerar systemet i stor skala.

Quantum Development Kit (QDK) med öppen källkod har lanserats för att göra det enklare att utveckla kvantprogram och algoritmer. Vårt avancerade programmeringsspråk Q#, hanterar utmaningarna vid kvantprogrammering.  Vi har utformat Q# som ett kvantfokuserat programmeringsspråk på hög nivå som är fokuserat på algoritm- och programutveckling. Q#-kompileraren är integrerad i en programstack där en kvantalgoritm kan kompileras till de primitiva åtgärderna i en kvantdator.  Upp till en viss skala (antal kvantbitar), kan kvantberäkning simuleras på en klassisk dator. Med hjälp av simulering kan du börja skriva kvantprogram redan i dag som kan köras på kvantmaskinvara i morgon.  Vi har också kompletterat Q# med exempel, bibliotek och övningar som gör det enkelt att komma igång med kvantprogrammering redan i dag. 

## <a name="next-steps"></a>Nästa steg

* [Vad kan kvantdatorer göra?](xref:microsoft.quantum.overview.computers)
* [Kom igång med Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
* Läs mer om [kvantberäkningsbegrepp](xref:microsoft.quantum.concepts.intro)
