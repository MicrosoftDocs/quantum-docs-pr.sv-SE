---
title: Ordlista för kvantdatorer
description: En ordlista med vanliga termer, åtgärder och objekt som används i kvantdatorer.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482207"
---
# <a name="quantum-computing-glossary"></a>Ordlista för kvantdatorer

## <a name="adjoint"></a>Angränsande

Det komplexa konjugatet för en [operation](xref:microsoft.quantum.glossary#operation). För operationer som implementerar en [enhetlig](xref:microsoft.quantum.glossary#unitary-operator) operatör är den angränsande inversen av operationen och indikeras av en dolksymbol. Om åtgärden `U` till exempel representerar den enhetliga operatorn `Adjoint U` $U$, representerar den $U^\dolk$. Mer information finns i [Angränsande](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Underordnad

En [qubit](xref:microsoft.quantum.glossary#qubit) som fungerar som tillfälligt minne för en kvantdator och tilldelas och avfördet vid behov.  Mer information finns i [Flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Sätta en klocka på statligt

En av fyra specifika maximalt [trassliga](xref:microsoft.quantum.glossary#entanglement) [kvanttillstånd](xref:microsoft.quantum.glossary#quantum-state) av två qubits. De fyra tillstånden definieras $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Ett bell-tillstånd är också känt som ett [EPR-par.](xref:microsoft.quantum.glossary#epr-pair)

## <a name="bloch-sphere"></a>Bloch sfär

En grafisk representation av en enda[qubit](xref:microsoft.quantum.glossary#qubit) [kvanttillstånd](xref:microsoft.quantum.glossary#quantum-state) som en punkt i en tredimensionell enhet sfär. Mer information finns i [Visualisera qubits och transformationer med Bloch-sfären](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Inlösbara

En [åtgärd](xref:microsoft.quantum.glossary#operation) eller [funktion](xref:microsoft.quantum.glossary#function) på språket Q# . Mer information finns i [Drift- och funktionstyper](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="clifford-group"></a>Clifford-gruppen

Den uppsättning operationer som upptar oktanterna i [Bloch sfären](xref:microsoft.quantum.glossary#bloch-sphere) och effekt permutationer av [Pauli operatörer .](xref:microsoft.quantum.glossary#pauli-operators) Dessa inkluderar verksamheten [$X $](xref:microsoft.quantum.intrinsic.x), [$Y $](xref:microsoft.quantum.intrinsic.y), $Z [$](xref:microsoft.quantum.intrinsic.z), [$H $](xref:microsoft.quantum.intrinsic.h) och $S [$](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Kontrollerade

En [kvantoperation](xref:microsoft.quantum.glossary#operation) som tar en eller [flera qubits](xref:microsoft.quantum.glossary#qubit) som möjliggörare för måloperationen. Mer information finns i [Kontrollerad](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Dirac Notation

En symbolisk stenografi som förenklar representationen av [kvanttillstånd](xref:microsoft.quantum.glossary#quantum-state), även kallad *bra-ket* notation.  *Bh-delen* representerar en radvektor, till exempel $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ och *ketdelen representerar* en kolumnvektor, \\ \\ $\ket{B} = \begin{bmatrix} B{_1} B{_2} \end{bmatrix}$. Mer information finns i [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Egenvärde

Den faktor genom vilken storleken på en [egengenvektor](xref:microsoft.quantum.glossary#eigenvector) av en viss omvandling ändras genom tillämpningen av omvandlingen.  Med tanke på en kvadratisk matris $M $ och en eigenvector $v $, sedan $Mv = cv $, där $c $ är egenvärde och kan vara ett komplext antal av alla argument. Mer information finns i [Avancerade matrisbegrepp](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Egennektor

En vektor vars riktning är oförändrad av en viss omvandling och vars storlek ändras med en faktor som motsvarar vektorns [egenvärde](xref:microsoft.quantum.glossary#eigenvalue). Med tanke på en kvadratisk matris $M $ och en egenvärde $c $, sedan $Mv = cv $, där $v $ är en egengenvektor av matrisen och kan vara ett komplext antal av alla argument. Mer information finns i [Avancerade matrisbegrepp](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Entanglement

Kvantpartiklar, såsom [qubits](xref:microsoft.quantum.glossary#qubit), kan anslutas eller *trasslat* in sig så att de inte kan beskrivas oberoende av varandra. Deras mätresultat är korrelerade även när de separeras oändligt långt borta. Entanglement är viktigt att [mäta](xref:microsoft.quantum.glossary#measurement) [tillståndet](xref:microsoft.quantum.glossary#quantum-state) i en qubit.  Mer information finns i [Avancerade matrisbegrepp](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR-par

En av fyra specifika maximalt trassliga [kvanttillstånd](xref:microsoft.quantum.glossary#quantum-state) av två [qubits](xref:microsoft.quantum.glossary#qubit). De{1} fyra tillstånden definieras $\ket{\beta_{ij}} = (\mathbb \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Ett EPR-par är också känt som ett [belltillstånd](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evolution

Hur ett [kvanttillstånd](xref:microsoft.quantum.glossary#quantum-state) förändras med tiden. Mer information finns i [Matrisexentiella](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funktion
En typ av subrutin i Q # språk som är rent klassisk (icke-quantum). Även funktioner används inom kvantalgoritmer, de kan inte agera på [qubits](xref:microsoft.quantum.glossary#qubit) eller [samtalsoperationer](xref:microsoft.quantum.glossary#operation). Mer information finns i [Drift- och funktionstyper](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="gate"></a>Gate

En arv term för en [kvantoperation](xref:microsoft.quantum.glossary#operation), baserad på begreppet klassisk logik grindar. En [kvantkrets](xref:microsoft.quantum.glossary#quantum-circuit-diagram) är ett nätverk av grindar (eller operationer), baserat på liknande koncept av klassiska logikkretsar.

## <a name="global-phase"></a>Global fas

När två [tillstånd](xref:microsoft.quantum.glossary#quantum-state) är identiska upp till en multipel av ett komplext tal $e^{i\phi}$, sägs de skilja sig från en global fas. Till skillnad från lokala faser kan globala faser inte observeras genom någon [mätning.](xref:microsoft.quantum.glossary#measurement) Mer information finns i [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard (på andra sätt)

Den Hadamard operation (även kallad Hadamard gate eller omvandla) fungerar på en enda [qubit](xref:microsoft.quantum.glossary#qubit) och sätter{0}den i en{1}jämn [superposition](xref:microsoft.quantum.glossary#superposition) av $ \ ket{0}$ eller $ $ om qubit är ursprungligen i $ \ ket $ staten. I Q#används den här åtgärden av [`H`](xref:microsoft.quantum.intrinsic.h) den fördefinierade åtgärden.

## <a name="immutable"></a>Oföränderliga

En variabel vars värde inte kan ändras. En oföränderlig variabel i Q# skapas med nyckelordet. `let` Om du vill deklarera variabler som *kan* ändras `set` använder du nyckelordet [mutable](xref:microsoft.quantum.glossary#immutable) för att deklarera och nyckelordet för att ändra värdet. 

## <a name="measurement"></a>Mått

En manipulering av en [qubit](xref:microsoft.quantum.glossary#qubit) (eller uppsättning qubits) som ger resultatet av en observation, i själva verket få en klassisk bit. Mer information finns i [The Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Föränderlig

En variabel vars värde kan ändras när det har skapats. En föränderlig variabel i Q# `mutable` deklareras med `set` nyckelordet och ändras med nyckelordet. Variabler som `let` skapas med nyckelordet är [oföränderliga](xref:microsoft.quantum.glossary#immutable) och deras värde kan inte ändras.

## <a name="namespace"></a>Namnområde

En etikett för en samling relaterade namn (t.ex. [operationer,](xref:microsoft.quantum.glossary#operation) [funktioner](xref:microsoft.quantum.glossary#function)och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type)). Till exempel namnområdet [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) etiketter alla symboler som definieras i standardbiblioteket som hjälper till med att förbereda inledande tillstånd.

## <a name="operation"></a>Åtgärd

Den grundläggande enheten för kvantutförande i Q#. Det motsvarar ungefär en funktion i C, C++ eller Python, eller en statisk metod i C# eller Java. Mer information finns i [Drift- och funktionstyper](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="operator-application"></a>Operatörsprogram

Utför en kvantoperation. Detta gäller vanligtvis en enhetlig matris på den aktuella kvanttillståndsvektorn.

## <a name="oracle"></a>Oracle

En subrutin som ger databeroende information till en kvantalgoritm vid körning. Vanligtvis är målet att tillhandahålla en [superposition](xref:microsoft.quantum.glossary#superposition) av utdata som motsvarar indata som är i superposition. Mer information finns i [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Partiell tillämpning

Anropar en [funktion](xref:microsoft.quantum.glossary#function) eller [åtgärd](xref:microsoft.quantum.glossary#operation) utan alla nödvändiga ingångar. Detta returnerar en ny [uppringningsbar](xref:microsoft.quantum.glossary#callable) som bara behöver de parametrar som saknas (indikeras av ett understreck) som ska levereras under ett framtida program. Med tanke på `MyFunc(x : int, y : int) : int {return x + y;}` funktionen kan du till exempel `let NewFunc = MyFunc(_, 3)`delvis använda den på en ny funktion . Du kan sedan anropa den nya funktionen vid `NewFunc(2)` ett senare tillfälle med den parameter som saknas som returnerar värdet *5*.  Mer information finns i [Partiellt program](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Pauli operatörer

En uppsättning av tre 2 x 2 enhetliga `Y` `Z` matriser kallas `X`, och kvantoperationer. Identitetsmatrisen, $I$, ingår ofta i uppsättningen också.  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & \\ \\ 1 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 \\ \\ & -i i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 & 0 0 \\ \\ & -1 \end{bmatrix}$.   Mer information finns i [Enstaka qubit-åtgärder](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagram över kvantkrets

En metod för att grafiskt representera sekvensen av [operationer](xref:microsoft.quantum.glossary#operation) (eller [grindar)](xref:microsoft.quantum.glossary#gate)för enkla kvantprogram, till exempel ![Provkretsdiagram](~/media/qpe.png). Mer information finns i [Kvantkretsar](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Kvantbibliotek

Samlingar av [åtgärder,](xref:microsoft.quantum.glossary#operation) [funktioner](xref:microsoft.quantum.glossary#function) och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type) för att skapa Q#-program. [Standardbiblioteket](xref:microsoft.quantum.libraries.standard.intro) installeras som standard. Andra bibliotek som är tillgängliga är [kemibiblioteket,](xref:microsoft.quantum.chemistry.concepts.intro) [biblioteket Numerics](xref:microsoft.quantum.numerics.intro) och [maskininlärningsbiblioteket](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Kvanttillstånd

Det exakta tillståndet för ett isolerat [measurement](xref:microsoft.quantum.glossary#measurement) kvantsystem, från vilket mätsannolikheter kan extraheras. I kvantdatorer använder kvantsimulatorn denna information för att simulera hur qubits reagerar på operationer. Mer information finns i [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit (qubit)

En grundläggande enhet av kvantinformation, jämförbar med *lite* i klassisk databehandling. Mer information finns i [The Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Upprepa tills-framgång

En kvantalgoritm som probabilistically lyckas. Vid fel försöker rutinen igen tills det lyckades (eller en gräns har nåtts). Mer information finns i [Upprepa till framgång (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Standardbibliotek

[Åtgärder,](xref:microsoft.quantum.glossary#operation) [funktioner](xref:microsoft.quantum.glossary#function) och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type) som installeras tillsammans med Q#-kompilatorn under installationen. Standardbiblioteksimplementeringen är agnostisk när det gäller måldatorer. Mer information finns i [Standardbibliotek](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Överlagring

Konceptet i kvantdatorer som en [qubit](xref:microsoft.quantum.glossary#qubit) är en linjär kombination av två tillstånd, $\ket{\0}$ och $\ket{\1}$, tills den [mäts](xref:microsoft.quantum.glossary#measurement).  Mer information finns i [Vad är kvantdatorer](xref:microsoft.quantum.overview.what).

## <a name="target-machine"></a>Målmaskin

Ett kompileringsmål som sänker ett abstrakt kvantprogram mot hårdvara eller simulering. Detta inkluderar vanligtvis omskrivningar för många ändamål, inklusive gate ersättning, kodning för felkorrigering, geometrisk layout och andra. Mer information finns i [Quantum simulatorer och värdprogram](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportering

En metod för att återskapa data, eller [kvanttillståndet,](xref:microsoft.quantum.glossary#quantum-state)för en [qubit](xref:microsoft.quantum.glossary#qubit) från en plats till en annan utan att fysiskt flytta qubit, med hjälp av [trassel](xref:microsoft.quantum.glossary#entanglement) och [mätning](xref:microsoft.quantum.glossary#measurement).  För mer information, se [Kvantkretsar](xref:microsoft.quantum.concepts.circuits) och [Sätta ihop allt](xref:microsoft.quantum.techniques.puttingittogether).

## <a name="tuple"></a>Tupel

En samling kommaavgränsade värden som fungerar som ett enda värde. *Typen* av tuppel definieras av de typer av värden som den innehåller. I Q#är tupplar [oföränderliga](xref:microsoft.quantum.glossary#immutable) och kan kapslas, innehålla matriser eller användas i en matris. Mer information finns i [Tuple-typer](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Enhetsoperatör

En operatör vars omvända är lika med dess [angränsande](xref:microsoft.quantum.glossary#adjoint), dvs $UU^{\dagger} = \id$.

## <a name="user-defined-type"></a>Användardefinierad typ

En samling inbyggda eller tidigare definierade typer som kan kallas en enda enhet. Mer information finns i [Användardefinierade typer](xref:microsoft.quantum.language.type-model#user-defined-types).