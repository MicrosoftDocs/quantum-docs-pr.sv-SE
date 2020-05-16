---
title: Ord lista för Quantum Computing
description: En ord lista med vanliga termer, åtgärder och objekt som används i Quantum Computing.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: cbc473eb14d8afd255a7072475dc054e18b98e3e
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426712"
---
# <a name="quantum-computing-glossary"></a>Ord lista för Quantum Computing

## <a name="adjoint"></a>Angränsande

Den komplexa konjugats transponeren för en [åtgärd](xref:microsoft.quantum.glossary#operation). För åtgärder som implementerar en [enhetlig](xref:microsoft.quantum.glossary#unitary-operator) operator är det intilliggande är inversen till åtgärden och anges av en Dagger symbol. Om åtgärden till exempel `U` representerar den enhetliga operatören $U $, `Adjoint U` representerar $U ^ \dagger $. Mer information finns i [angränsande](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

En [qubit](xref:microsoft.quantum.glossary#qubit) som fungerar som temporärt minne för en Quantum-dator och allokeras och avallokeras efter behov.  Mer information finns i [flera qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Klock status

Ett av fyra olika maximally [Entangled](xref:microsoft.quantum.glossary#entanglement) [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) för två qubits. De fyra tillstånden definieras $ \ket{\ beta_ {}} = (\mathbb{I} \otimes X ^ iZ ^ j) (\ket {00} + \ket {11} )/\sqrt {2} $. En klock status kallas även för ett [EPR-par](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Bloch-sfär

En grafisk representation av ett[qubit](xref:microsoft.quantum.glossary#qubit) [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) som en punkt i ett tredimensionellt enhets klot. Mer information finns i [visualisera qubits och omvandlingar med hjälp av Bloch-sfären](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Anropningsbara

En [funktion](xref:microsoft.quantum.glossary#operation) eller [funktion](xref:microsoft.quantum.glossary#function) på språket Q #. Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Clifford-grupp

Den uppsättning åtgärder som upptar octants för Bloch- [sfären](xref:microsoft.quantum.glossary#bloch-sphere) och [Pauli-operatörernas-operatorer](xref:microsoft.quantum.glossary#pauli-operators). Detta omfattar åtgärderna [$X $](xref:microsoft.quantum.intrinsic.x), [$Y $](xref:microsoft.quantum.intrinsic.y), [$Z $](xref:microsoft.quantum.intrinsic.z), [$H $](xref:microsoft.quantum.intrinsic.h) och [$S $](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Styr

En Quantum- [åtgärd](xref:microsoft.quantum.glossary#operation) som tar en eller flera [qubits](xref:microsoft.quantum.glossary#qubit) som aktiveringar för mål åtgärden. Mer information finns i [kontrollerade och närliggande aktiviteter](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Dirac-notation

Ett symboliskt kort som fören klar åter givningen av [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state), även kallat *bra-ket* notation.  *Bra* -delen representerar en rad vektor, till exempel $ \bra{A} = \begin{bmatrix} a {_1} & a {_2} \end{bmatrix} $ och *ket* -delen representerar en kolumn vektor, $ \ket{B} = \begin{bmatrix} B {_1} \\ \\ B {_2} \end{bmatrix} $. Mer information finns i [Dirac notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Den faktor enligt vilken storleken på en [eigenvector](xref:microsoft.quantum.glossary#eigenvector) för en specifik omvandling ändras av omvandlingens program.  Med en fyrkantig matris $M $ och en eigenvector $v $ och sedan $Mv = ka $, där $c $ är eigenvalue och kan vara ett komplext antal argument. Mer information finns i [avancerade mat ris koncept](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

En Vector vars riktning är oförändrad av en specifik omvandling och vars storlek ändras av en faktor som motsvarar den Vectorns [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue). Med en fyrkantig matris $M $ och en eigenvalue $c $ och sedan $Mv = ka $, där $v $ är en eigenvector i matrisen och kan vara ett komplext antal argument. Mer information finns i [avancerade mat ris koncept](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Entanglement

Quantum-partiklar, till exempel [qubits](xref:microsoft.quantum.glossary#qubit), kan vara anslutna eller *Entangled* så att de inte kan beskrivas oberoende av varandra. Deras mått resultat korreleras även om de avgränsas oändligt långt bort. Entanglement är viktigt för [measuring](xref:microsoft.quantum.glossary#measurement) att mäta [status](xref:microsoft.quantum.glossary#quantum-state) för en qubit.  Mer information finns i [avancerade mat ris koncept](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>EPR-par

Ett av fyra olika maximally Entangled [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) för två [qubits](xref:microsoft.quantum.glossary#qubit). De fyra tillstånden definieras $ \ket{\ beta_ {}} = (\mathbb {1} \Otimes X ^ iz ^ j) (\ket {00} + \ket {11} )/\sqrt {2} $. Ett EPR-par kallas även för [klock status](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Utveckling

Hur ett [Quantum-tillstånd](xref:microsoft.quantum.glossary#quantum-state) ändras med tiden. Mer information finns i [matriss exponentieller](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funktion
En typ av subrutin på det Q #-språk som är helt Klassiskt (icke-Quantum). Medan Functions används i Quantum-algoritmer, kan de inte agera på [qubits](xref:microsoft.quantum.glossary#qubit) -eller anrops [åtgärder](xref:microsoft.quantum.glossary#operation). Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>Gate

En äldre term för en Quantum- [åtgärd](xref:microsoft.quantum.glossary#operation)baserat på begreppet klassiska Logic-grindar. En [Quantum-krets](xref:microsoft.quantum.glossary#quantum-circuit-diagram) är ett nätverk av portar (eller åtgärder), baserat på liknande koncept av klassiska Logic-kretsar.

## <a name="global-phase"></a>Global fas

När två [tillstånd](xref:microsoft.quantum.glossary#quantum-state) är identiska med en multipel av ett komplext tal $e ^ {i\phi} $, sägs de vara olika upp till en global fas. Till skillnad från lokala faser går det inte att observera globala faser genom något [mätbart mätbart](xref:microsoft.quantum.glossary#measurement)behov. Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

Hadamard-åtgärden (kallas även Hadamard-grind eller transformering) fungerar på en enda [qubit](xref:microsoft.quantum.glossary#qubit) och placerar den i ett jämnt [överplacerat](xref:microsoft.quantum.glossary#superposition) $ \ket {0} $ eller $ \ket {1} $ om qubit är inlednings vis i $ \ket {0} $ State. I Q # tillämpas den här åtgärden av den fördefinierade [`H`](xref:microsoft.quantum.intrinsic.h) åtgärden.

## <a name="immutable"></a>Inte kan ändras

En variabel vars värde inte kan ändras. En oföränderlig variabel i Q # skapas med hjälp av `let` nyckelordet. Om du vill deklarera variabler som *kan* ändras använder du nyckelordet [föränderligt](xref:microsoft.quantum.glossary#immutable) för att deklarera och `set` nyckelordet för att ändra värdet. 

## <a name="measurement"></a>Mått

En manipulering av en [qubit](xref:microsoft.quantum.glossary#qubit) (eller en uppsättning qubits) som ger resultatet av en observation, och som hämtar en klassisk bit. Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Föränderlig

En variabel vars värde kan ändras efter att det har skapats. En föränderligt-variabel i Q # deklareras med hjälp av `mutable` nyckelordet och modifieras med hjälp av `set` nyckelordet. Variabler som skapas med `let` nyckelordet är [oföränderliga](xref:microsoft.quantum.glossary#immutable) och deras värde kan inte ändras.

## <a name="namespace"></a>Namnområde

En etikett för en samling relaterade namn (t. ex. [åtgärder](xref:microsoft.quantum.glossary#operation), [funktioner](xref:microsoft.quantum.glossary#function)och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type)). Till exempel märks namn området [Microsoft. Quantum. Preparation](xref:microsoft.quantum.preparation) med alla symboler som definierats i standard biblioteket som hjälper till att förbereda de ursprungliga tillstånden.

## <a name="operation"></a>Åtgärd

Den grundläggande enheten för Quantum-körning i Q #. Det är ungefär detsamma som en funktion i C, C++ eller python, eller en statisk metod i C# eller Java. Mer information finns i [åtgärder och funktioner](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>Operatörs program

Utföra en Quantum-åtgärd. Detta använder vanligt vis en enhetlig matris till den aktuella Quantum-delläges vektorn.

## <a name="oracle"></a>Oracle

En subrutin som tillhandahåller data beroende information till en Quantum-algoritm vid körning. Målet är vanligt vis att ge en [superposition](xref:microsoft.quantum.glossary#superposition) av utdata som motsvarar indata som är i position. Mer information finns i [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Partiellt program

Anropa en [funktion](xref:microsoft.quantum.glossary#function) eller [åtgärd](xref:microsoft.quantum.glossary#operation) utan alla nödvändiga indata. Detta returnerar en ny [uppringning](xref:microsoft.quantum.glossary#callable) som bara behöver de parametrar som saknas (vilket indikeras av ett under streck) som ska levereras under ett framtida program. Till exempel `MyFunc(x : int, y : int) : int {return x + y;}` kan du använda funktionen för att delvis tillämpa den på en ny funktion `let NewFunc = MyFunc(_, 3)` . Du kan sedan anropa den nya funktionen vid ett senare tillfälle med den saknade parametern `NewFunc(2)` som returnerar värdet *5*.  Mer information finns i [partiellt program](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Pauli-operatörer

En uppsättning med tre 2 x 2-matriser som kallas `X` , `Y` och Quantum- `Z` åtgärder. Identitets mat ris, $I $, ingår ofta även i uppsättningen.  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix} $, $X = \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{bmatrix} $, $Y = \begin{bmatrix} 0 &-i \\ \\ & 0 \end{bmatrix} $, $Z = \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix} $.   Mer information finns i [åtgärder med en qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagram över Quantum-krets

En metod för att grafiskt representera en sekvens med [åtgärder](xref:microsoft.quantum.glossary#operation) (eller [portar](xref:microsoft.quantum.glossary#gate)) för enkla Quantum-program, till exempel ett ![ krets diagram ](~/media/qpe.png) . Mer information finns i [Quantum-kretsar](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Quantum-bibliotek

Samlingar med [åtgärder](xref:microsoft.quantum.glossary#operation), [funktioner](xref:microsoft.quantum.glossary#function) och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type) för att skapa Q #-program. [Standard biblioteket](xref:microsoft.quantum.libraries.standard.intro) installeras som standard. Andra tillgängliga bibliotek är [kemi-biblioteket](xref:microsoft.quantum.chemistry.concepts.intro), det [numeriska biblioteket](xref:microsoft.quantum.numerics.intro) och [Machine Learning-biblioteket](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Quantum-tillstånd

Det exakta läget för ett isolerat Quantum-system, från vilket [mått](xref:microsoft.quantum.glossary#measurement) sannolikheter kan extraheras. I Quantum Computing använder Quantum Simulator den här informationen för att simulera hur qubits reagerar på åtgärder. Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

En grundläggande enhet med Quantum-information som motsvarar en *bit* i klassisk data behandling. Mer information finns i [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Upprepa-tills-lyckades

En Quantum-algoritm som probabilistically lyckas. Vid fel försöker rutinen igen tills den lyckades (eller så har en gräns nåtts). Mer information finns i [Upprepa tills lyckad (ru: er)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Standardbibliotek

[Åtgärder](xref:microsoft.quantum.glossary#operation), [funktioner](xref:microsoft.quantum.glossary#function) och [användardefinierade typer](xref:microsoft.quantum.glossary#user-defined-type) som installeras tillsammans med Q #-kompilatorn under installationen. Standard biblioteks implementeringen är oberoende med avseende på mål datorer. Mer information finns i [standard bibliotek](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superposition

Konceptet i Quantum Computing som en [qubit](xref:microsoft.quantum.glossary#qubit) är en linjär kombination av två tillstånd, $ \ket{\0} $ och $ \ket{\1} $, tills den [mäts](xref:microsoft.quantum.glossary#measurement).  Mer information finns i [förstå Quantum Computing](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Måldator

Ett Compilation Target som sänker ett abstrakt Quantum-program mot maskin vara eller simulering. Detta omfattar vanligt vis åter skrivningar för många olika sätt, inklusive porttyp, kodning för fel korrigering, geometrisk layout och andra. Mer information finns i [Quantum Simulators och värd program](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportering

En metod för att återskapa data eller Quantum- [tillstånd](xref:microsoft.quantum.glossary#quantum-state)för en [qubit](xref:microsoft.quantum.glossary#qubit) från en plats till en annan utan att fysiskt flytta qubit, med hjälp av [entanglement](xref:microsoft.quantum.glossary#entanglement) och [mätning](xref:microsoft.quantum.glossary#measurement).  Mer information finns i [Quantum-kretsar](xref:microsoft.quantum.concepts.circuits) och respektive Kata vid [Quantum Katas](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Tupel

En samling kommaavgränsade värden som fungerar som ett enda värde. *Typen* av en tupel definieras av de typer av värden som den innehåller. I Q # är tupler [oföränderliga](xref:microsoft.quantum.glossary#immutable) och kan kapslas, innehålla matriser eller användas i en matris. Mer information finns i [tuple-typer](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Enhetlig operatör

En operator vars motsatta värde är lika med den [angränsande](xref:microsoft.quantum.glossary#adjoint), d.v.s. $uu ^ {\dagger} = \id $.

## <a name="user-defined-type"></a>Användardefinierad typ

En samling inbyggda eller tidigare definierade typer som kan kallas en enda enhet. Mer information finns i [användardefinierade typer](xref:microsoft.quantum.guide.types#user-defined-types).