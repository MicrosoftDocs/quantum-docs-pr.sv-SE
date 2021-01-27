---
title: Öppnar pull-begäranden
description: Lär dig hur du skickar in en GitHub pull-begäran när du är redo att bidra med kod eller dokumentation till Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: a936283f3e51da9b97b8145bad3ab765b6423458
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858457"
---
# <a name="opening-pull-requests"></a>Öppna pull-begäranden #

All dokumentation för Quantum Development Kit hanteras med git-versions kontroll systemet genom användning av flera databaser som finns på GitHub.
Med hjälp av Git och GitHub tillsammans blir det enkelt att samar beta mycket i Quantum Development Kit.
I synnerhet kan alla git-lagringsplatser klonas eller förgrenas för att göra en helt oberoende kopia av lagrings platsen.
På så sätt kan du arbeta med de verktyg och den takt som du föredrar.

När du är klar kan du skicka oss en begäran om att ta med ditt bidrag till vår databaser, med hjälp av GitHub-funktionen för _pull-begäran_ .
Sidan för varje pull-begäran innehåller information om alla ändringar som gör ditt bidrag, en lista över kommentarer om ditt bidrag och en uppsättning gransknings verktyg som andra medlemmar i communityn kan använda för att ge feedback och råd.

> [!NOTE]
> Även om en fullständig själv studie kurs om git ligger utanför den här guidens omfattning kan vi föreslå följande länkar för fler resurser på Learning git:
>
> - [Lär dig git](https://www.atlassian.com/git): en uppsättning git-självstudier från Atlassian.
> - [Versions kontroll i Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): en guide för hur du använder Visual Studio Code som ett GUI för git.
> - [GitHub Learning Lab](https://lab.github.com/): en uppsättning onlinekurser som använder git, GitHub och relaterad teknik.
> - [Visualisera git](https://git-school.github.io/visualizing-git/): ett interaktivt verktyg för visualisering av hur git-kommandon ändrar tillstånd för en lagrings plats.
> - [Versions kontroll med git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): en git-självstudie som riktar sig mot vetenskapliga data behandling.
> - [Lär dig git branchning](https://learngitbranching.js.org/): en interaktiv uppsättning förgrenings-och puzzles som hjälper dig att lära dig nya git-funktioner.

## <a name="what-is-a-pull-request"></a>Vad är en pull-begäran? ##

Efter ovanstående är det bra att ta en stund att säga vad en pull-begäran **är**.
När du arbetar med git visas alla ändringar som en _incheckning_ som beskriver hur dessa ändringar är relaterade till lagrings platsens tillstånd innan ändringarna.
Vi ritar ofta diagram där incheckningar ritas som cirklar med pilar från föregående incheckningar.

Anta att du har startat ett bidrag i en _gren_ som kallas `feature` .
Sedan kan din förgrening av **Microsoft/Quantum** se ut ungefär så här:

![En arbets gren i GitHub](~/media/git-workflow-step0.png)

Om du gör dina ändringar i din lokala lagrings plats kan du _Hämta_ ändringar från en annan lagrings plats till din för att komma igång med alla ändringar som har varit överordnade.

![Hämta och sammanfoga ändringar från en överordnad lagrings platsen](~/media/git-workflow-step1.png)

Pull-begäranden fungerar på samma sätt, men i omvänd ordning: när du öppnar en pull-begäran ber du om den överordnade lagrings platsen att hämta ditt bidrag i.

![Begär att hämta ändringarna till den ursprungliga lagrings platsen](~/media/git-workflow-step2.png)

När du öppnar en pull-begäran till någon av våra databaser, kommer GitHub att erbjuda en möjlighet för andra i communityn att se en sammanfattning av dina ändringar, kommentera dem och få förslag på hur du kan göra ett ännu bättre bidrag.

![Skärm bild av en pull-begäran i GitHub](~/media/pull-request-header.png)

Med den här processen kan vi använda GitHub-funktioner för att förbättra bidrag och underhålla en produkt med hög kvalitet för program gruppen Quantum Programming.

## <a name="how-to-make-a-pull-request"></a>Så här gör du en pull-begäran ##

Det finns två huvudsakliga sätt att göra en pull-begäran.  
För små ändringar som endast påverkar en enskild fil kan GitHub-webbgränssnittet användas för att göra en pull-begäran helt online. Navigera bara till filen som du vill redigera och Använd redigerings ikonen.  
För mer komplexa bidrag är det oftast enklare att klona lagrings platsen till din lokala dator för att förbereda en pull-begäran först.

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>Nästa steg ##

Grattis på användningen av Git för att hjälpa till med Quantum Development Kit community!
Om du vill veta mer om hur du kan bidra med kod kan du fortsätta med följande guide.

> [!div class="nextstepaction"]
> [Lär dig att bidra med kod](xref:microsoft.quantum.contributing.code)
