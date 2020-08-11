---
title: Introduktion till Microsoft Q#-standardbibliotek
description: Lär dig mer om Microsoft Q#-standardbibliotek som definierar de åtgärder, funktioner och datatyper som används i kvantprogram.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868482"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="52ae4-103">Introduktion till Q#-standardbiblioteken</span><span class="sxs-lookup"><span data-stu-id="52ae4-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="52ae4-104">Q# stöds av en rad olika användbara åtgärder, funktioner och användardefinierade typer som utgör Q#-*standardbiblioteken*.</span><span class="sxs-lookup"><span data-stu-id="52ae4-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="52ae4-105">Det [`Microsoft.Quantum.Development.Kit`-NuGet-paket](https://www.nuget.org/packages/microsoft.quantum.development.kit) som installeras under [installation och validering](xref:microsoft.quantum.install) tillhandahåller Q#-kompilatorn och delar av det standardbibliotek som implementeras av måldatorerna.</span><span class="sxs-lookup"><span data-stu-id="52ae4-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="52ae4-106">[`Microsoft.Quantum.Standard`-paketet](https://www.nuget.org/packages/microsoft.quantum.standard) tillhandahåller den del av de Q#-standardbibliotek som är portabla mellan måldatorerna.</span><span class="sxs-lookup"><span data-stu-id="52ae4-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="52ae4-107">De symboler som definieras av Q#-standardbiblioteken definieras mycket mer detaljerat i [API-dokumentationen](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="52ae4-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="52ae4-108">I följande avsnitt beskriver vi de viktigaste delarna i varje del av standardbiblioteket och ger viss kontext för hur varje funktion kan användas i praktiken.</span><span class="sxs-lookup"><span data-stu-id="52ae4-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
