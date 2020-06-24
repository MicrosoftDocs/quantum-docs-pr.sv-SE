---
title: Bibliotek för kvantmaskininlärning
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276171"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introduktion till Quantum Machine Learning

## <a name="framework-and-goals"></a>Ramverk och mål

Quantum encoding och bearbetning av information är ett kraftfullt alternativ till klassisk Machine Learning Quantum-klassificerare, särskilt kodar data i Quantum-register som är koncisa i förhållande till antalet funktioner, som systematiskt använder Quantum entanglement som beräknings resurs och använder Quantum-mått för klass härledning.
Krets centrerad Quantum-klassificerare är en relativt enkel Quantum-lösning som kombinerar data kodning med en snabbt Entangling/disentangling Quantum-krets följt av mått för att härleda klass etiketter för data exempel.
Målet är att säkerställa klassisk karakterisering och lagring av ämnes kretsar, samt hybrid-och klassisk utbildning för krets parametrarna, även för mycket stora funktions utrymmen.

## <a name="classifier-architecture"></a>Klassificerings arkitektur

Klassificering är en övervakad maskin inlärnings uppgift där målet är att härleda klass etiketter $ \{ y_1, y_2, \ldots, y_d \} $ av vissa data exempel. "Tränings data uppsättning" är en samling exempel $ \mathcal{D} = \{ (x, y)} $ med kända fördefinierade etiketter. Här $x $ är ett data exempel och $y $ är dess kända etikett som kallas "övnings etikett".
I likhet med traditionella metoder består Quantum klassificering av tre steg:
- data kodning
- förberedelse av ett klassificerings tillstånd
- mått på grund av måttets Probabilistic karaktär måste dessa tre steg upprepas flera gånger. Måttet kan visas som en Quantum-motsvarighet till icke-linjär aktivering.
Både kodningen och bearbetningen av klassificerings statusen görs med hjälp av *Quantum-kretsar*. Även om kodnings kretsen vanligt vis är data driven och parameter fri, innehåller klassificerings kretsen en tillräckligt stor uppsättning parametrar. 

I den föreslagna lösningen består klassificerings kretsen av en qubit rotation och två qubit kontrollerade rotationer. De lär sig parametrarna här är rotations vinklarna. Rotations-och kontrollerade rotations grindarna har visat sig vara *universella* för Quantum-beräkning, vilket innebär att en enhetlig vikt mat ris kan delas upp i en tillräckligt lång krets som består av sådana grindar.

![Multilayer Perceptron vs. krets-inriktad klassificerare](~/media/DLvsQCC.png)

Vi kan jämföra den här modellen med en Multilayer-Perceptron för att få en bättre förståelse för den grundläggande strukturen. I Perceptron är $p (y | x, \theta) $ parametrized med den mängd vikter som är $ \theta $ som fastställer de linjära funktionerna som ansluter icke-linjära aktiverings funktioner (neurons). Dessa parametrar kan tränas för att skapa modellen. På output-lagret kan vi få sannolikheten för ett sampel som tillhör en klass med icke-linjära aktiverings funktioner som SOFTMAX. I den kretsbaserade klassificeraren är förväntaren parametrized i rotations vinkeln för qubit och två qubit kontrollerade rotationer för modell kretsen. På liknande sätt kan dessa parametrar tränas av en hybrid Quantum/klassisk version av brantaste-algoritmen för övertoning. För att beräkna utdata, i stället för att använda icke-linjära aktiverings funktioner, erhålls sannolikheten för klassen genom att läsa upprepade mätningar över en speciell qubit efter den kontrollerade rotationen. För att koda de klassiska data i ett Quantum-tillstånd använder vi en kontrollerbar kodnings krets för förberedelse av tillstånd.

Vår arkitektur utforskar relativt lite-kretsar som därför måste vara *snabbt Entangling* för att kunna samla in alla korrelationer mellan data funktionerna i alla intervall. Ett exempel på den mest användbara Entangling krets-komponenten visas på bilden nedan. Även om en krets med den här geometrin bara består av $3 n + 1 $ grindar, säkerställer den enhetliga vikt mat ris som den beräknar betydande kors samtal mellan $2 ^ n $-funktioner.

![Snabbt Entangling Quantum-krets på 5 qubits (med två cykliska lager).](~/media/5-qubit-qccc.png)

Kretsen i exemplet ovan består av 6 engångs-qubit-grindar $ (G_1, \ldots, G_5; G_ {16} ) $ och 10 2-qubits Gates $ (G_6, \ldots, G_ {15} ) $. Förutsatt att varje port har definierats med en enkel parameter kan vi använda 16 parametrar, medan dimensionen för 5-qubit Hilbert-utrymmet är 32. Sådan krets geometri kan enkelt generaliseras till alla $n $-qubit-register, när $n $ är udda, vilket ger kretsar med $3 n + 1 $ parametrar för $2 ^ n $-dimensionellt funktions utrymme.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Klassificerings utbildning som en övervakad utbildnings uppgift

Utbildning av en klassificerings modell omfattar att hitta optimala värden för dess operativa parametrar, så att de maximerar det genomsnittliga sannolikheten för att kunna härleda rätt utbildnings etiketter i övnings exemplen.
Här gäller endast skapar med två nivå klassificering, d.v.s. $d = $2 och bara två klasser med etiketterna $y _1, y_2 $.

> [!NOTE]
> Ett allmänt sätt att generalisera våra metoder för att använda ett godtyckligt antal klasser är att ersätta qubits med qudits, d.v.s. Quantum units med $d $ bas tillstånd och det tvåvägs måttet med $d $-Way-mätning.

### <a name="likelihood-as-the-training-goal"></a>Sannolikhet för utbildnings målet

Med en inlärtd Quantum-krets $U (\theta) $, där $ \theta $ är en Vector med parametrar och som anger den slutliga mätningen med $M $, är det genomsnittliga sannolikheten att den korrekta etikettens härledning är $ $ \begin{align} \mathcal{L} (\theta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, y_1) \In\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $ där $P (M = y | z) $ är sannolikheten att mäta $y $ i Quantum State $z $.
Här är det tillräckligt för att förstå att sannolikhets funktionen $ \mathcal{L} (\theta) $ är smidig i $ \theta $ och dess derivat i $ \ theta_j $ kan beräknas av i stort sett samma Quantum-protokoll som används för att beräkna sannolikhets funktionen. Detta möjliggör optimering av $ \mathcal{L} (\theta) $ med tonings brantaste.

### <a name="classifier-bias-and-training-score"></a>Klassificerings resultat för klassificering och utbildning

Med några av de mellanliggande (eller slutliga) värdena för parametrarna i $ \theta $, måste vi identifiera ett enkelt reellt värde $b $ known som *klassificering av klassificerare* . Etikettens härlednings regel fungerar på följande sätt: 
- Ett exempel på $x $ tilldelas etikett $y _2 $ om och endast om $P (M = y_2 | U (\theta) x) + b > $0,5 (regel 1) (annars tilldelas etiketten $y _1 $)

Tydligt $b $ måste vara i intervallet $ (-0,5, + 0,5) $ för att vara meningsfull.

En utbildnings väska $ (x, y) \in \mathcal{D} $ betraktas som en *felklassificering* med förskjutningen $b $ om etiketten som härleds till $x $ per regel 1 faktiskt skiljer sig från $y $. Det totala antalet felklassificeringar är *inlärnings poängen* för klassificeraren med hänsyn till bias $b $. Den *optimala* klassificerings bias $b $ minimerar utbildnings poängen. Det är enkelt att se att den beräknade sannolikheten $ \{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \} $, den optimala klassificeraren kan hittas av binär sökning i intervall $ (-0,5, + 0,5) $ genom att göra högst $ \ log_2 (| \mathcal{D} |) $ steg.

### <a name="reference"></a>Referens

Den här informationen bör vara tillräckligt stor för att börja spela med koden. Men om du vill lära dig mer om den här modellen läser du det ursprungliga förslaget: [ *"kretsbaserade Quantum-klassificerare", Maria Schuld, Alex Bocharov, krysta Svore och Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
