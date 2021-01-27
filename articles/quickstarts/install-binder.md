---
title: Utveckla med Q# och Binder
description: Lär dig hur du skapar ett Q#-program med Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856715"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="261fe-103">Utveckla med Q# och Binder</span><span class="sxs-lookup"><span data-stu-id="261fe-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="261fe-104">Du kan använda Binder för att köra och dela dina Jupyter Notebook-filer online.</span><span class="sxs-lookup"><span data-stu-id="261fe-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="261fe-105">Använda Binder med Microsoft QDK-exempel</span><span class="sxs-lookup"><span data-stu-id="261fe-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="261fe-106">Så här konfigurerar du Binder för att använda Microsoft QDK-exempel automatiskt:</span><span class="sxs-lookup"><span data-stu-id="261fe-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="261fe-107">Öppna en webbläsare och kör https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="261fe-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="261fe-108">På landningssidan för **Quantum Development Kit-exempel** klickar du på **Q# notebook** för att lära dig hur du använder IQ# för att skriva dina egna notebook-filer för kvanttillämpningar.</span><span class="sxs-lookup"><span data-stu-id="261fe-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Landningssida för QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="261fe-110">Använda Binder med egna notebook-filer och egen lagringsplats</span><span class="sxs-lookup"><span data-stu-id="261fe-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="261fe-111">Om du redan har notebook-filer i en GitHub-lagringsplats kan du konfigurera Binder så att det fungerar med din lagringsplats:</span><span class="sxs-lookup"><span data-stu-id="261fe-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="261fe-112">Kontrollera att det finns en fil med namnet *Dockerfile* i roten på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="261fe-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="261fe-113">Filen ska som minimum innehålla följande rader:</span><span class="sxs-lookup"><span data-stu-id="261fe-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="261fe-114">Du kan kontrollera att du har den senaste versionen av IQ# i [Viktig information](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="261fe-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="261fe-115">Mer information om hur du skapar en Dockerfile finns i [Dockerfile-referensen](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="261fe-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="261fe-116">Öppna en webbläsare och gå till [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="261fe-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="261fe-117">Ange namnet på din lagringsplats som **GitHub URL** (till exempel *MyName/MyRepo*), och klicka på **starta**.</span><span class="sxs-lookup"><span data-stu-id="261fe-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formulär för MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="261fe-119">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="261fe-119">Next steps</span></span>

<span data-ttu-id="261fe-120">Du har nu konfigurerat din Binder-miljö och det är dags att skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="261fe-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
