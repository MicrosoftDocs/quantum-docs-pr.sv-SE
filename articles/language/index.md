---
title: Q#-programmeringsspråket | Microsoft Docs
description: Q#-programmeringsspråket
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442473"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="7514a-103">Q#-programmeringsspråket</span><span class="sxs-lookup"><span data-stu-id="7514a-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="7514a-104">Introduktion</span><span class="sxs-lookup"><span data-stu-id="7514a-104">Introduction</span></span>

<span data-ttu-id="7514a-105">En naturlig modell för kvantberäkning är att behandla kvantdatorn som en coprocessor, liknande den som används för GPU, FPGA och andra kompletterande processorer.</span><span class="sxs-lookup"><span data-stu-id="7514a-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="7514a-106">Den primära kontrollogiken kör en klassisk kod på en klassisk ”värddator”.</span><span class="sxs-lookup"><span data-stu-id="7514a-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="7514a-107">När det är lämpligt och nödvändigt kan värdprogrammet anropa en subrutin som körs på den kompletterande processorn.</span><span class="sxs-lookup"><span data-stu-id="7514a-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="7514a-108">När subrutinen är slutförd får värdprogrammet åtkomst till subrutinens resultat.</span><span class="sxs-lookup"><span data-stu-id="7514a-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="7514a-109">Q# (Q Sharp) är ett domänspecifikt programmeringsspråk som används till att uttrycka kvantalgoritmer.</span><span class="sxs-lookup"><span data-stu-id="7514a-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="7514a-110">Det används till att skriva subrutiner som körs på en kompletterande kvantprocessor, under kontroll av ett klassiskt värdprogram och en dator.</span><span class="sxs-lookup"><span data-stu-id="7514a-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="7514a-111">Innan kvantprocessorer är mer tillgängliga, körs Q#-subrutinerna på en simulator.</span><span class="sxs-lookup"><span data-stu-id="7514a-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="7514a-112">Q# innehåller en liten uppsättning primitiva typer, samt två sätt (matriser och tupplar) för att skapa nya, strukturerade typer.</span><span class="sxs-lookup"><span data-stu-id="7514a-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="7514a-113">Den har stöd för en grundläggande procedurmodell för att skriva program, med loopar och if/then-instruktioner.</span><span class="sxs-lookup"><span data-stu-id="7514a-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="7514a-114">De högsta nivåkonstruktionerna i Q# är användardefinierade typer, åtgärder och funktioner.</span><span class="sxs-lookup"><span data-stu-id="7514a-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="7514a-115">I följande avsnitt beskrivs:</span><span class="sxs-lookup"><span data-stu-id="7514a-115">The following sections detail:</span></span>
- [<span data-ttu-id="7514a-116">Typmodellen</span><span class="sxs-lookup"><span data-stu-id="7514a-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="7514a-117">Uttryck</span><span class="sxs-lookup"><span data-stu-id="7514a-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="7514a-118">Instruktioner</span><span class="sxs-lookup"><span data-stu-id="7514a-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="7514a-119">Filstruktur</span><span class="sxs-lookup"><span data-stu-id="7514a-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="7514a-120">Konventioner</span><span class="sxs-lookup"><span data-stu-id="7514a-120">Conventions</span></span>

<span data-ttu-id="7514a-121">Vi försöker säkerställa att vanliga skiljetecken används konsekvent i alla situationer.</span><span class="sxs-lookup"><span data-stu-id="7514a-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="7514a-122">Vi tänker oss att det blir enklare att lära sig Q# när dessa tecken alltid betyder samma sak, och att samma begrepp alltid representeras på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="7514a-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="7514a-123">Mer specifikt:</span><span class="sxs-lookup"><span data-stu-id="7514a-123">Specifically:</span></span>

- <span data-ttu-id="7514a-124">Semikolon, `;`, används för att avsluta en instruktion eller ett direktiv som bara består av en rad.</span><span class="sxs-lookup"><span data-stu-id="7514a-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="7514a-125">Det används inte i något annat syfte.</span><span class="sxs-lookup"><span data-stu-id="7514a-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="7514a-126">Kommatecknet, `,`, används till att avgränsa element i en sekvens.</span><span class="sxs-lookup"><span data-stu-id="7514a-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="7514a-127">Det används för tuppelliteraler, matrisliteraler, argumentlistor, tuppeldefinitioner och typlistor.</span><span class="sxs-lookup"><span data-stu-id="7514a-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="7514a-128">**I en ändring från tidigare versioner, stöds `;` inte längre som en matrisliteral avgränsare.**</span><span class="sxs-lookup"><span data-stu-id="7514a-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="7514a-129">Kolontecknet, `:`, används för att inleda en typanteckning.</span><span class="sxs-lookup"><span data-stu-id="7514a-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="7514a-130">Den används främst i anropningsbara signaturer.</span><span class="sxs-lookup"><span data-stu-id="7514a-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="7514a-131">Eftersom kolontecknet alltid startar en typunderskrift, använder den tredelade villkorsstyrda operatorn som startas i 0,3 en lodrät stapel, `|`, till att avgränsa värden för sant och falskt. Det innebär att Q# använder `cond ? tval | fval` i stället för kolon som avgränsare på samma sätt som i C.</span><span class="sxs-lookup"><span data-stu-id="7514a-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
