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
# <a name="develop-with-no-locq-and-binder"></a>Utveckla med Q# och Binder

Du kan använda Binder för att köra och dela dina Jupyter Notebook-filer online.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Använda Binder med Microsoft QDK-exempel

Så här konfigurerar du Binder för att använda Microsoft QDK-exempel automatiskt:

1. Öppna en webbläsare och kör https://aka.ms/try-qsharp.
1. På landningssidan för **Quantum Development Kit-exempel** klickar du på **Q# notebook** för att lära dig hur du använder IQ# för att skriva dina egna notebook-filer för kvanttillämpningar.

![Landningssida för QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Använda Binder med egna notebook-filer och egen lagringsplats

Om du redan har notebook-filer i en GitHub-lagringsplats kan du konfigurera Binder så att det fungerar med din lagringsplats:

1. Kontrollera att det finns en fil med namnet *Dockerfile* i roten på lagringsplatsen. Filen ska som minimum innehålla följande rader:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > Du kan kontrollera att du har den senaste versionen av IQ# i [Viktig information](xref:microsoft.quantum.relnotes).

    Mer information om hur du skapar en Dockerfile finns i [Dockerfile-referensen](https://docs.docker.com/engine/reference/builder/).

2. Öppna en webbläsare och gå till [mybinder.org](https://mybinder.org).
3. Ange namnet på din lagringsplats som **GitHub URL** (till exempel *MyName/MyRepo*), och klicka på **starta**.

![Formulär för MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Nästa steg

Du har nu konfigurerat din Binder-miljö och det är dags att skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).
