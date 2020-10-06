---
title: I Q# Magic-kommandon
description: Sidan snabb referens för att I Q# Magic-kommandon med Q# Jupyter-anteckningsböcker
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4549afb84bf0084160079e3cef3a7f94dffcda3e
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771338"
---
# <a name="ino-locq-magic-commands"></a>I Q# Magic-kommandon

### <a name="general"></a>Allmänt

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Gör det möjligt att ställa in eller fråga konfigurations alternativ.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Kör en specifik funktion eller åtgärd på ResourcesEstimator-mål datorn.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returnerar en lista med alla tillgängliga Magic-kommandon.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen): Visar en lista över namn områden som har öppnats och deras alias.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Ger möjlighet att läsa in ett NuGet-paket.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Rapporterar aktuella prestanda mått för denna kernel.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Ger möjlighet att visa eller lägga till Q# projekt referenser. 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Kör en specifik funktion eller åtgärd på QuantumSimulator-mål datorn.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Kör en specifik funktion eller åtgärd på ToffoliSimulator-mål datorn.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Visar en lista över de Q# åtgärder som är tillgängliga i den aktuella sessionen.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Innehåller åtgärder relaterade till den aktuella arbets ytan.

### <a name="azure-quantum-integration"></a>Azure Quantum-integrering

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Ansluter till en Azure Quantum-arbetsyta eller visar aktuell anslutnings status.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Skickar ett jobb till en Azure Quantum-arbetsyta och väntar på att slutföras.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Visar en lista med jobb på den aktuella Azure Quantum-arbetsytan.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Visar resultat för ett jobb på den aktuella Azure Quantum-arbetsytan.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Visar status för ett jobb på den aktuella Azure Quantum-arbetsytan.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Skickar ett jobb till en Azure Quantum-arbetsyta.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Anger eller visar det aktiva körnings målet för Q# jobb sändningen i en Azure Quantum-arbetsyta.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Kemi (från Microsoft. Quantum. kemi-paketet)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Läser in och returnerar Broombridge för det elektroniska strukturs problemet från en specifik. yaml-fil.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Kodar en fermion-Hamiltonian till ett format som kan förbrukas av Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Lägger till villkor till en fermion-Hamiltonian.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Läser in fermion-Hamiltonian för ett elektroniskt struktur problem. Problemet läses in från en fil eller skickas som ett argument.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Läser in Broombridge elektroniskt struktur problem och returnerar valt indatamängds tillstånd.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (från Microsoft. Quantum. Katas-paket)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Kör ett enda test och rapporterar om testet lyckades.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Kontrollerar referens implementeringen för ett enskilt Kata-test.
    Mer specifikt ersätter den referens implementeringen för en enskild uppgift i cellen och rapporterar om testet lyckades.
