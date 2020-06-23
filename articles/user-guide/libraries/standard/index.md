---
title: Introduktion till Microsoft Q#-standardbibliotek
description: Lär dig mer om Microsoft Q#-standardbibliotek som definierar de åtgärder, funktioner och datatyper som används i kvantprogram.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273812"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Introduktion till Q#-standardbiblioteken #

Q# stöds av en rad olika användbara åtgärder, funktioner och användardefinierade typer som utgör Q#-*standardbibliotek*.
Det [`Microsoft.Quantum.Development.Kit` NuGet-paket](https://www.nuget.org/packages/microsoft.quantum.development.kit) som installerades under [installation och validering](xref:microsoft.quantum.install) tillhandahåller Q#-kompilatorn och delar av det standardbibliotek som implementeras av måldatorerna.
[`Microsoft.Quantum.Standard`-paketet](https://www.nuget.org/packages/microsoft.quantum.standard) tillhandahåller den del av de Q#-standardbibliotek som är portabla mellan måldatorerna.

De symboler som definieras av Q#-standardbiblioteken definieras mycket mer detaljerat i [API-dokumentationen](xref:microsoft.quantum.standardlibsintro).

I följande avsnitt beskriver vi de viktigaste delarna i varje del av standardbiblioteket och ger viss kontext för hur varje funktion kan användas i praktiken.
