---
title: Q#-standardbibliotek – introduktion | Microsoft Docs
description: Q#-standardbibliotek – introduktion
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 547f4f6066e3ead627cd2a5970b1555999e988bb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056389"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Introduktion till Q#-standardbiblioteken #

Q# stöds av en rad olika användbara åtgärder, funktioner och användardefinierade typer som utgör Q#-*standardbibliotek*.
Det [`Microsoft.Quantum.Development.Kit` NuGet-paket](https://www.nuget.org/packages/microsoft.quantum.development.kit) som installerades under [installation och validering](xref:microsoft.quantum.install) tillhandahåller Q#-kompilatorn och delar av det standardbibliotek som implementeras av måldatorerna.
[`Microsoft.Quantum.Standard`-paketet](https://www.nuget.org/packages/microsoft.quantum.standard) tillhandahåller den del av de Q#-standardbibliotek som är portabla mellan måldatorerna.

De symboler som definieras av Q#-standardbiblioteken definieras mycket mer detaljerat i [API-dokumentationen](xref:microsoft.quantum.standardlibsintro).

I följande avsnitt beskriver vi de viktigaste delarna i varje del av standardbiblioteket och ger viss kontext för hur varje funktion kan användas i praktiken.
