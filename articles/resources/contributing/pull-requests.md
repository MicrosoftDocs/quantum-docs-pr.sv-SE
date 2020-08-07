---
title: Öppnar pull-begäranden
description: Lär dig hur du skickar in en GitHub pull-begäran när du är redo att bidra med kod eller dokumentation till Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e04e6502e0a6005dfdf0f93450bf3ffd5aaa672
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866935"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="f078a-103">Öppna pull-begäranden</span><span class="sxs-lookup"><span data-stu-id="f078a-103">Opening Pull Requests</span></span> #

<span data-ttu-id="f078a-104">All dokumentation för Quantum Development Kit hanteras med git-versions kontroll systemet genom användning av flera databaser som finns på GitHub.</span><span class="sxs-lookup"><span data-stu-id="f078a-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="f078a-105">Med hjälp av Git och GitHub tillsammans blir det enkelt att samar beta mycket i Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="f078a-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="f078a-106">I synnerhet kan alla git-lagringsplatser klonas eller förgrenas för att göra en helt oberoende kopia av lagrings platsen.</span><span class="sxs-lookup"><span data-stu-id="f078a-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="f078a-107">På så sätt kan du arbeta med de verktyg och den takt som du föredrar.</span><span class="sxs-lookup"><span data-stu-id="f078a-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="f078a-108">När du är klar kan du skicka oss en begäran om att ta med ditt bidrag till vår databaser, med hjälp av GitHub-funktionen för _pull-begäran_ .</span><span class="sxs-lookup"><span data-stu-id="f078a-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="f078a-109">Sidan för varje pull-begäran innehåller information om alla ändringar som gör ditt bidrag, en lista över kommentarer om ditt bidrag och en uppsättning gransknings verktyg som andra medlemmar i communityn kan använda för att ge feedback och råd.</span><span class="sxs-lookup"><span data-stu-id="f078a-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="f078a-110">Även om en fullständig själv studie kurs om git ligger utanför den här guidens omfattning kan vi föreslå följande länkar för fler resurser på Learning git:</span><span class="sxs-lookup"><span data-stu-id="f078a-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="f078a-111">[Lär dig git](https://www.atlassian.com/git): en uppsättning git-självstudier från Atlassian.</span><span class="sxs-lookup"><span data-stu-id="f078a-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="f078a-112">[Versions kontroll i Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): en guide för hur du använder Visual Studio Code som ett GUI för git.</span><span class="sxs-lookup"><span data-stu-id="f078a-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="f078a-113">[GitHub Learning Lab](https://lab.github.com/): en uppsättning onlinekurser som använder git, GitHub och relaterad teknik.</span><span class="sxs-lookup"><span data-stu-id="f078a-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="f078a-114">[Visualisera git](https://git-school.github.io/visualizing-git/): ett interaktivt verktyg för visualisering av hur git-kommandon ändrar tillstånd för en lagrings plats.</span><span class="sxs-lookup"><span data-stu-id="f078a-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="f078a-115">[Versions kontroll med git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): en git-självstudie som riktar sig mot vetenskapliga data behandling.</span><span class="sxs-lookup"><span data-stu-id="f078a-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="f078a-116">[Lär dig git branchning](https://learngitbranching.js.org/): en interaktiv uppsättning förgrenings-och puzzles som hjälper dig att lära dig nya git-funktioner.</span><span class="sxs-lookup"><span data-stu-id="f078a-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="f078a-117">Vad är en pull-begäran?</span><span class="sxs-lookup"><span data-stu-id="f078a-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="f078a-118">Efter ovanstående är det bra att ta en stund att säga vad en pull-begäran **är**.</span><span class="sxs-lookup"><span data-stu-id="f078a-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="f078a-119">När du arbetar med git visas alla ändringar som en _incheckning_ som beskriver hur dessa ändringar är relaterade till lagrings platsens tillstånd innan ändringarna.</span><span class="sxs-lookup"><span data-stu-id="f078a-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="f078a-120">Vi ritar ofta diagram där incheckningar ritas som cirklar med pilar från föregående incheckningar.</span><span class="sxs-lookup"><span data-stu-id="f078a-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="f078a-121">Anta att du har startat ett bidrag i en _gren_ som kallas `feature` .</span><span class="sxs-lookup"><span data-stu-id="f078a-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="f078a-122">Sedan kan din förgrening av **Microsoft/Quantum** se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="f078a-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![En arbets gren i GitHub](~/media/git-workflow-step0.png)

<span data-ttu-id="f078a-124">Om du gör dina ändringar i din lokala lagrings plats kan du _Hämta_ ändringar från en annan lagrings plats till din för att komma igång med alla ändringar som har varit överordnade.</span><span class="sxs-lookup"><span data-stu-id="f078a-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![Hämta och sammanfoga ändringar från en överordnad lagrings platsen](~/media/git-workflow-step1.png)

<span data-ttu-id="f078a-126">Pull-begäranden fungerar på samma sätt, men i omvänd ordning: när du öppnar en pull-begäran ber du om den överordnade lagrings platsen att hämta ditt bidrag i.</span><span class="sxs-lookup"><span data-stu-id="f078a-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![Begär att hämta ändringarna till den ursprungliga lagrings platsen](~/media/git-workflow-step2.png)

<span data-ttu-id="f078a-128">När du öppnar en pull-begäran till någon av våra databaser, kommer GitHub att erbjuda en möjlighet för andra i communityn att se en sammanfattning av dina ändringar, kommentera dem och få förslag på hur du kan göra ett ännu bättre bidrag.</span><span class="sxs-lookup"><span data-stu-id="f078a-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![Skärm bild av en pull-begäran i GitHub](~/media/pull-request-header.png)

<span data-ttu-id="f078a-130">Med den här processen kan vi använda GitHub-funktioner för att förbättra bidrag och underhålla en produkt med hög kvalitet för program gruppen Quantum Programming.</span><span class="sxs-lookup"><span data-stu-id="f078a-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="f078a-131">Så här gör du en pull-begäran</span><span class="sxs-lookup"><span data-stu-id="f078a-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="f078a-132">Det finns två huvudsakliga sätt att göra en pull-begäran.</span><span class="sxs-lookup"><span data-stu-id="f078a-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="f078a-133">För små ändringar som endast påverkar en enskild fil kan GitHub-webbgränssnittet användas för att göra en pull-begäran helt online.</span><span class="sxs-lookup"><span data-stu-id="f078a-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="f078a-134">Navigera bara till filen som du vill redigera och Använd redigerings ikonen.</span><span class="sxs-lookup"><span data-stu-id="f078a-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="f078a-135">För mer komplexa bidrag är det oftast enklare att klona lagrings platsen till din lokala dator för att förbereda en pull-begäran först.</span><span class="sxs-lookup"><span data-stu-id="f078a-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="f078a-136">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f078a-136">Next steps</span></span> ##

<span data-ttu-id="f078a-137">Grattis på användningen av Git för att hjälpa till med Quantum Development Kit community!</span><span class="sxs-lookup"><span data-stu-id="f078a-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="f078a-138">Om du vill veta mer om hur du kan bidra med kod kan du fortsätta med följande guide.</span><span class="sxs-lookup"><span data-stu-id="f078a-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f078a-139">Lär dig att bidra med kod</span><span class="sxs-lookup"><span data-stu-id="f078a-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
