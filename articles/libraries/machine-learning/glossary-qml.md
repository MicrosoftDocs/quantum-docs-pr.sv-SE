---
title: Quantum Machine Learning-bibliotek
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
ms.openlocfilehash: f9b33a607a892179795d0700ba3080f9a24ab94a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909780"
---
# <a name="quantum-machine-learning-glossary"></a>Quantum Machine Learning-ordlista

Utbildning av en krets-centrerad Quantum-klassificerare är en process med många rörliga delar som kräver samma (eller något större) mängd kalibrering per utvärderings version och fel som utbildning av traditionella klassificerare. Här definierar vi huvud begreppen och ingredienserna i den här utbildnings processen.

## <a name="trainingtesting-schedules"></a>Utbildnings-/testnings scheman

I samband med klassificerings träning beskriver ett *schema* en delmängd av data exempel i en övergripande utbildning eller testnings uppsättning. Ett schema definieras vanligt vis som en samling av exempel index.

## <a name="parameterbias-scores"></a>Parameter/bias-Poäng

Med hänsyn till en kandidat parameter vektor och en klassificerings kompensation mäts deras *validerings Poäng* i förhållande till det valda verifierings schemat och uttrycks av ett antal felklassificeringar som räknas över alla exempel i schemat.

## <a name="hyperparameters"></a>Hyperparametrar

Modell inlärnings processen styrs av vissa fördefinierade värden som kallas för mina *parametrar*:

### <a name="learning-rate"></a>Inlärnings pris

Det är en av nyckelns egenskaper. Den definierar hur mycket aktuell Stochastic gradient-uppskattning påverkar parametern Update. Storleken på parameter uppdaterings förändring är proportionell mot inlärnings takten. Lägre inlärnings frekvens värden leder till långsammare parameter utveckling och långsammare konvergens, men alltför stora värden för LR kan bryta konvergensen helt eftersom övertonings brantaste aldrig allokeras till ett visst lokalt minimum. Medan inlärnings takten justeras anpassningsbart av utbildningen i viss utsträckning, är det viktigt att välja ett bra initialt värde för det. Ett vanligt standard start värde för inlärnings pris är 0,1. Att välja det bästa värdet för inlärnings takt är en bra bild (se till exempel Section 4,3 av Goodfellow et al., "djup inlärning", MIT Press, 2017).

### <a name="minibatch-size"></a>Minibatch-storlek

Definierar hur många data exempel som används för en enskild uppskattning av Stochastic-toning. Större värden av minibatch-storlek leder vanligt vis till mer robust och mer enkel och mer högfärgad konvergens, men kan eventuellt sakta ned inlärnings processen, eftersom kostnaden för en övertoning är proportionell mot minimatch-storleken. Ett vanligt standardvärde för minibatch-storleken är 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Utbildnings epoker, tolerans, gridlocks

"Epok" syftar på ett komplett steg genom de schemalagda tränings data.
Det maximala antalet epoker per utbildnings tråd (se nedan) bör vara ett tak. Inlärnings tråden definieras för att avslutas (med de bästa kända kandidat parametrarna) när det maximala antalet epoker har körts. En sådan utbildning skulle dock upphöra tidigare när klassificerings schemats klassificerings schema sjunker under en vald tolerans. Anta till exempel att toleransen för avvikelser är 0,01 (1%). om verifierings uppsättningen av 2000-prov visas färre än 20 felklassificeringar har tolerans nivån uppnåtts. En utbildnings tråd avslutas också för tidigt om validerings poängen för kandidat modellen inte har visat någon förbättring över flera på varandra följande epoker (en gridlock). Logiken för gridlock-avslutningen är för närvarande hårdkodad.

### <a name="measurements-count"></a>Antal mätningar

Uppskatta inlärnings-och validerings poängen och komponenterna i Stochastic-övertoningen på en Quantum-enhets mängder för att uppskatta Quantum State-överlappningar som kräver flera mätningar av lämplig observables. Antalet mätningar ska skalas som $O (1/\ Epsilon ^ 2) $ där $ \epsilon $ är det önskade uppskattnings felet.
Som en tumregel kan det första antalet mätningar vara cirka $1/\ mbox {tolerans} ^ 2 $ (se definitionen av toleransen i föregående stycke). Du skulle behöva ändra mätnings antalet uppåt om tonings brantaste verkar vara alltför oförutsägbart och konvergensen för svår att uppnå.

### <a name="training-threads"></a>Utbildnings trådar

Sannolikhets funktionen för klassificeraren är mycket sällan konvex, vilket innebär att det vanligt vis har en mängd lokala OPTIMA i parameter utrymmet som kan variera avsevärt beroende på kvalitet. Eftersom SGD-processen kan konvergera enbart till en särskilt optimal, är det viktigt att utforska flera inledande parameter vektorer. Vanliga metoder i Machine Learning är att initiera sådana start vektorer slumpmässigt. API: et API för träning accepterar en godtycklig matris av sådana start vektorer, men den underliggande koden utforskar dem i tur och ordning. På en dator med flera kärnor eller i själva verket för en parallell data behandling är det lämpligt att utföra flera anrop till API: n # utbildnings-API parallellt med olika parameter initieringar i anropen.

#### <a name="how-to-modify-the-hyperparameters"></a>Ändra de båda parametrarna

I QML-biblioteket är det bästa sättet att ändra de båda parametrarna genom att åsidosätta standardvärdena för UDT- [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions). För att göra detta anropar vi den med funktionen [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) och använder operatorn `w/` för att åsidosätta standardvärdena. Om du till exempel vill använda 100 000-mått och en inlärnings grad på 0,01:
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
