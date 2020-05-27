---
title: Så här fungerar kvantberäkning
description: Vad är kvantdatorer och hur använder de principerna för kvantmekanik?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
ms.openlocfilehash: 65fa85a80021124444fd352f9492d03cbefcb859
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433018"
---
# <a name="understanding-quantum-computing"></a>Så här fungerar kvantberäkning

Inom kvantberäkning används principerna för kvantmekanik till att bearbeta information. Därför kräver kvantberäkning en annan metod än klassisk beräkning.  Ett exempel på skillnaden är den processor som används i kvantdatorer.  Medan klassiska datorer använder de välbekanta kiselbaserade kretsarna använder kvantdatorer kvantmaterial såsom atomer, joner, fotoner eller elektroner.  

Kvantmaterial beter sig utefter kvantmekanikens lagar med begrepp såsom probabilistisk beräkning, superposition och sammanflätning. Dessa begrepp utgör grunden för kvantalgoritmer som utnyttjar kraften hos kvantberäkning till att lösa komplexa problem. I den här artikeln beskrivs några av de centrala begreppen inom kvantmekanik som kvantberäkning bygger på.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Fågelperspektiv på kvantmekanik

Kvantmekanik, som även kallas kvantteori, är en gren inom fysiken som handlar om partiklar på eller under atomnivå. På kvantnivå slutar dock många vedertagna mekaniklagar att gälla. Superposition, kvantmätning och sammanflätning är tre fenomen som är centrala vad gäller kvantberäkning.  

### <a name="superposition-vs-binary-computing"></a>Superposition kontra binär beräkning

Tänk dig att du motionerar i vardagsrummet. Du vrider på kroppen så långt du kan åt vänster och sedan åt höger. Nu försöker du vrida dig åt både vänster och höger samtidigt. Det lyckas du inte med (åtminstone inte utan gå itu).  Det står klart att du inte kan befinna dig i båda dessa tillstånd samtidigt – det går inte att titta åt vänster och höger på samma gång.

Om du är en kvantpartikel har du dock en viss sannolikhet att *titta åt vänster* OCH en viss sannolikhet att *titta åt höger* tack vare ett fenomen som heter **superposition** (det kallas även **koherens**).

En kvantpartikel såsom en elektron har egna egenskaper som motsvarar att ”titta åt vänster eller åt höger”, till exempel **spinn**, som är antingen uppåt eller nedåt. För att likna detta vid klassisk binär beräkning kan vi kalla det för 1 eller 0. När en kvantpartikel är i tillståndet superposition är den en linjär kombination av ett oändligt antal tillstånd mellan 1 och 0, men du vet inte vilket tillstånd den kommer få förrän du faktiskt observerar den. Detta leder oss till nästa fenomen: **kvantmätning**.

### <a name="quantum-measurement"></a>Kvantmätning

Anta att din vän tittar förbi och vill ta en bild på dig när du motionerar. Det blir sannolikt en suddig bild på ett mellantillstånd av dig när du vrider dig helt åt vänster eller höger.

Om du är en kvantpartikel händer däremot något intressant. Oavsett var du befinner dig när bilden tas kommer den alltid att visa dig helt åt vänster eller helt åt höger – inte något mittemellan.

Det här beror på att när en kvantpartikel observeras eller mäts så **kollapsar** superpositionstillståndet (detta kallas även **dekoherens**) och partikeln får det klassiska binära tillståndet som är antingen 1 eller 0.

Det här binära tillståndet är användbart eftersom det går att göra många saker med 1:or och 0:or. Men när en kvantpartikel har mätts och kollapsat behåller den det tillståndet för alltid (precis som på din bild) och kommer alltid att vara 1 eller 0. Som du kommer att se senare finns det dock åtgärder inom kvantberäkning som kan ”återställa” en partikel tillbaka till ett superpositionstillstånd så att den på nytt kan användas för kvantberäkningar.

### <a name="entanglement"></a>Sammanflätning

Kanske det mest intressanta fenomenet inom kvantmekanik är möjligheten att två eller fler kvantpartiklar **sammanflätas** med varandra. När partiklar sammanflätas bildar de ett enskilt system så att kvanttillståndet för en partikel inte kan beskrivas oberoende av kvanttillståndet för de andra partiklarna. Det innebär att åtgärder eller processer som du tillämpar på en partikel även motsvaras hos de andra partiklarna.

Utöver detta ömsesidiga beroende kan partiklar upprätthålla den här kopplingen även om de separeras över otroligt stora avstånd, om det så gäller ljusår. Effekterna av kvantmätning gäller även för sammanflätade partiklar – när en partikel mäts och kollapsar så kollapsar även den andra partikeln. Eftersom det finns en korrelation mellan de sammanflätade kvantbitarna ger mätning av tillståndet hos en kvantbit information om tillståndet hos den andra kvantbiten. Just denna egenskap är mycket användbar inom kvantberäkning.

### <a name="qubits-and-probability"></a>Kvantbitar och sannolikhet

Klassiska datorer lagrar och bearbetar information i bitar, som kan ha tillståndet 1 eller 0 men aldrig båda. Motsvarigheten inom kvantberäkning är **kvantbiten**, som representerar tillståndet för en kvantpartikel. På grund av superposition kan kvantbitar antingen vara 1 eller 0 eller vad som helst mellan dessa. Beroende på en kvantbits konfiguration har den en viss *sannolikhet* att kollapsa till 1 eller 0. Kvantbitens sannolikhet att kollapsa åt ettdera hållet avgörs av **kvantinterferens**. 

Kommer du ihåg din vän som skulle ta en bild på dig? Anta att kameran har specialfilter som kallas *interferensfilter*. Om vännen väljer filtret *70/30* och börjar ta bilder kommer du att titta åt vänster på 70 procent av bilderna och åt höger på 30 procent. Filtret orsakar interferens för kamerans normala tillstånd, vilket påverkar sannolikheten hos dess beteende.

På liknande sätt påverkar kvantinterferens tillståndet hos en kvantbit på så sätt att den ändrar sannolikheten att ett visst resultat sker under mätning. Det är vid detta probabilistiska tillstånd som kvantberäkning kommer väl till pass.

Med exempelvis två bitar på en klassisk dator kan varje bit lagra 1 eller 0. Sammanlagt kan då fyra möjliga värden lagras – **00**, **01**, **10** och **11** – men endast ett av dessa åt gången. När två kvantbitar är i superposition kan dock varje kvantbit vara 1 eller 0 eller *båda dessa*, vilket gör att du kan representera samma fyra värden samtidigt. Med tre kvantbitar kan du representera åtta värden, med fyra kvantbitar 16 värden och så vidare.

## <a name="summary"></a>Sammanfattning

Dessa begrepp skrapar bara på ytan av kvantmekaniken, men de är viktiga när du lär dig hur kvantberäkning fungerar.

- **Superposition** – möjligheten för kvantpartiklar att ha en kombination av alla möjliga tillstånd.
- **Kvantmätning** – att observera en kvantpartikel i superposition, vilket ger upphov till ett av de möjliga tillstånden.
- **Sammanflätning** – möjligheten för kvantpartiklar att korrelera sina mätningsresultat med varandra.
- **Kvantbit** – den grundläggande informationsenheten inom kvantberäkning. En kvantbit representerar en kvantpartikel i superposition med alla de möjliga tillstånden.
- **Interferens** – ett inneboende beteende hos en kvantbit som kommer av att superposition påverkar sannolikheten att den kollapsar åt ettdera hållet.

## <a name="next-steps"></a>Efterföljande moment

> [!div class="nextstepaction"]
> [Kvantdatorer och kvantsimulatorer](xref:microsoft.quantum.overview.simulators)
