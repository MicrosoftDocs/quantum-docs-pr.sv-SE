---
title: Bibliotek för kvantmaskininlärning
description: Lär dig hur Machine Learning används på Quantum Systems
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: e2f4a4a63eef40474856426b3b29652b5d3053b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854022"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introduktion till Quantum Machine Learning

## <a name="framework-and-goals"></a>Ramverk och mål

Quantum encoding och bearbetning av information är ett kraftfullt alternativ till klassisk Machine Learning Quantum-klassificerare. I synnerhet gör det möjligt för oss att koda data i Quantum-register som är koncisa i förhållande till antalet funktioner, som systematiskt använder Quantum entanglement som beräknings resurs och använder Quantum-mätning för klass härledning.
Krets centrerad Quantum-klassificerare är en relativt enkel Quantum-lösning som kombinerar data kodning med en snabbt Entangling/disentangling Quantum-krets följt av mått för att härleda klass etiketter för data exempel.
Målet är att säkerställa klassisk karakterisering och lagring av ämnes kretsar, samt hybrid-och klassisk utbildning för krets parametrarna, även för mycket stora funktions utrymmen.

## <a name="classifier-architecture"></a>Klassificerings arkitektur

Klassificering är en övervakad maskin inlärnings uppgift där målet är att härleda klass etiketter $ \{ y_1, y_2, \ldots, y_d \} $ av vissa data exempel. "Tränings data uppsättning" är en samling exempel $ \mathcal{D} = \{ (x, y)} $ med kända fördefinierade etiketter. Här $x $ är ett data exempel och $y $ är dess kända etikett som kallas "övnings etikett".
I likhet med traditionella metoder består Quantum klassificering av tre steg:
- data kodning
- förberedelse av ett klassificerings tillstånd
- mått på grund av måttets Probabilistic karaktär måste dessa tre steg upprepas flera gånger. Både kodningen och bearbetningen av klassificerings statusen görs med hjälp av *Quantum-kretsar*. Även om kodnings kretsen vanligt vis är data driven och parameter fri, innehåller klassificerings kretsen en tillräckligt stor uppsättning parametrar. 

I den föreslagna lösningen består klassificerings kretsen av en qubit rotation och två qubit kontrollerade rotationer. De lär sig parametrarna här är rotations vinklarna. Rotations-och kontrollerade rotations grindarna har visat sig vara *universella* för Quantum-beräkning, vilket innebär att en enhetlig vikt mat ris kan delas upp i en tillräckligt lång krets som består av sådana grindar.

I den föreslagna versionen stöds endast en krets följt av en beräkning med en frekvens.
Det innebär att lösningen är en Quantum analog av en support vektor dator med en mindre grad polynom kernel.

![Multilayer Perceptron vs. krets-inriktad klassificerare](~/media/DLvsQCC.png)

En enkel Quantum klassificerare-design kan jämföras med en vanlig SVM-lösning (support Vector Machine). Den här härledningen för ett data exempel $x $ i händelse av SVM görs med ett optimalt kernel-formulär $ \sum \ alpha_j k (x_j, x) $ där $k $ är en viss kernel-funktion.

Som kontrast använder en Quantum-klassificeraren $p (y │ x, U (\theta)) = 〈 U (\theta) x | M | U (\theta) x 〉 $, som liknar sprit men tekniskt ganska annorlunda. Det innebär att när en enkel amplitud-kodning används, $p (y │ x, U (\theta)) $ är en kvadratisk form i amplituderna för $x $, men koefficienterna för det här formuläret har inte längre lärts oberoende. de sammanställs i stället från mat ris elementen i krets $U (\theta) $, som vanligt vis har betydligt mindre lärt parametrar $ \theta $ än dimensionerna i Vector $x $. Polynom graden av $p (y │ x, U (\theta)) $ i de ursprungliga funktionerna kan höjas till $2 ^ l $ genom att använda en Quantum produkt kodning på $l $ kopior av $x $.

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

Förutom kod exemplet som visas i nästa steg kan du också börja utforska Quantum-klassificeringen i [den här självstudien](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification) 
