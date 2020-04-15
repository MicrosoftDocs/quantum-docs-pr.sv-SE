---
title: Exempelprogram för kvantkemi
description: Utforska exempelprogram i Microsofts kvantkemibibliotek.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 5168fc8592d34a32ba67e5a0c4793aa17599fd35
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906499"
---
# <a name="quantum-chemistry-examples"></a>Exempel för kvantkemi

I begreppen för kvantkemi konstruerade vi exempel på fermion-hamiltonska värden manuellt. Vi kombinerar nu de algoritmer för kemisimulering som beskrivs i [Simulera hamiltonsk dynamik](xref:microsoft.quantum.libraries.standard.algorithms) med [kvantfasberäkning](xref:microsoft.quantum.libraries.characterization) i Canon-biblioteket. Med den här kombinationen kan vi få uppskattningar av energinivåer i den representerade molekylen, vilket är en av de viktigaste tillämpningarna av kvantkemi i en kvantdator. 

I stället för att ange termerna för det hamiltonska värdet en i taget går vi igenom några exempel som gör att vi kan utföra experiment med kvantkemi i större skala. Vi börjar med exempel som läser in ett kemiskt hamiltonskt värde som är kodat i [Broombridge-schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).

För molekyler som är för stora för att simuleras i [simulatorn med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator) går det ändå att utföra intressant vetenskap. Till exempel kan resurskostnaderna för att utföra stora kemisimuleringar fortfarande utvärderas genom riktning mot [spårningssimulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro).

Nu illustrerar vi intressanta tillämpningar av biblioteket för kemisimulering med några av de medföljande exemplen.
