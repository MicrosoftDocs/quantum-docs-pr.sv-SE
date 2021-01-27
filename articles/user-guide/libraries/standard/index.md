---
title: Introduktion till Microsoft Q#-standardbibliotek
description: Lär dig mer om Microsoft Q#-standardbibliotek som definierar de åtgärder, funktioner och datatyper som används i kvantprogram.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 58e271fefba84e45c5558eeee066bc37c22bf63b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858304"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Introduktion till Q#-standardbiblioteken

Q# stöds av en rad olika användbara åtgärder, funktioner och användardefinierade typer som utgör Q#-*standardbiblioteken*.
Det [`Microsoft.Quantum.Development.Kit`-NuGet-paket](https://www.nuget.org/packages/microsoft.quantum.development.kit) som installeras under [installation och validering](xref:microsoft.quantum.install) tillhandahåller Q#-kompilatorn och delar av det standardbibliotek som implementeras av måldatorerna.
[`Microsoft.Quantum.Standard`-paketet](https://www.nuget.org/packages/microsoft.quantum.standard) tillhandahåller den del av de Q#-standardbibliotek som är portabla mellan måldatorerna.

De symboler som definieras av Q#-standardbiblioteken definieras mycket mer detaljerat i [API-dokumentationen](xref:microsoft.quantum.apiref-intro).

I följande avsnitt beskriver vi de viktigaste delarna i varje del av standardbiblioteket och ger viss kontext för hur varje funktion kan användas i praktiken.
