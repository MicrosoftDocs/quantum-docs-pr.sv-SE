---
title: Magiska kommandon för IQ#
description: 'Sidan snabb referens för SWEETIQ # Magic-kommandon med Q # Jupyter Notebooks'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431027"
---
# <a name="iq-magic-commands"></a>Magiska kommandon för IQ#

### <a name="general"></a>Allmänt

- `%config`: Anger eller hämtar konfigurations inställningar.
- `%estimate`: Kör en specifik funktion eller åtgärd på QuantumSimulator-mål datorn.
- `%lsmagic`: Returnerar en lista med alla tillgängliga Magic-kommandon.
- `%package`: Ger möjlighet att läsa in ett NuGet-paket.
- `%performance`: Rapporterar aktuella prestanda mått för denna kernel.
- `%simulate`: Kör en specifik funktion eller åtgärd på QuantumSimulator-mål datorn.
- `%toffoli`: Kör en specifik funktion eller åtgärd på ToffoliSimulator Simulator mål datorn.
- `%who`: Innehåller åtgärder relaterade till den aktuella arbets ytan.
- `%workspace`: Returnerar en lista över alla åtgärder och funktioner som definierats i den aktuella sessionen, antingen interaktivt eller har lästs in från den aktuella arbets ytan.

### <a name="chemistry"></a>Kemiska

- `%chemistry.broombridge`: Läser in och returnerar Broombridge för det elektroniska strukturs problemet från en specifik. yaml-fil.
- `%chemistry.encode`: Kodar en fermion-Hamiltonian till ett format som kan förbrukas av Q #.
- `%chemistry.fh.add_terms`: Lägger till villkor till en fermion-Hamiltonian.
- `%chemistry.fh.load`: Läser in fermion-Hamiltonian för ett elektroniskt struktur problem. Problemet läses in från en fil eller skickas som ett argument.
- `%chemistry.inputstate.load`: Läser in Broombridge elektroniskt struktur problem och returnerar valt indatamängds tillstånd.

### <a name="from-microsoftquantumkatas-package"></a>Från Microsoft. Quantum. Katas-paket

- `%kata`: Kör ett enda test och rapporterar om testet lyckades.
- `%check_kata`: Kontrollerar referens implementeringen för ett enskilt Kata-test.
    Mer specifikt ersätter den referens implementeringen för en enskild uppgift i cellen och rapporterar om testet lyckades.
