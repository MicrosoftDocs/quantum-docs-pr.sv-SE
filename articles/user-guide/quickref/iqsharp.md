---
title: I Q# Magic-kommandon
description: Sidan snabb referens för att I Q# Magic-kommandon med Q# Jupyter-anteckningsböcker
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: fb7b5543ef9222e6bab2b1cbbc7e3ebb54863438
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867989"
---
# <a name="ino-locq-magic-commands"></a>I Q# Magic-kommandon

### <a name="general"></a>Allmänt

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Gör det möjligt att ställa in eller fråga konfigurations alternativ.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Kör en specifik funktion eller åtgärd på ResourcesEstimator-mål datorn.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Returnerar en lista med alla tillgängliga Magic-kommandon.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Ger möjlighet att läsa in ett NuGet-paket.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Rapporterar aktuella prestanda mått för denna kernel.
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Kör en specifik funktion eller åtgärd på QuantumSimulator-mål datorn.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Kör en specifik funktion eller åtgärd på ToffoliSimulator-mål datorn.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Visar en lista över de Q# åtgärder som är tillgängliga i den aktuella sessionen.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Innehåller åtgärder relaterade till den aktuella arbets ytan.

### <a name="azure-quantum-integration"></a>Azure Quantum-integrering

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Ansluter till en Azure Quantum-arbetsyta eller visar aktuell anslutnings status.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Kör ett jobb i en Azure Quantum-arbetsyta.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Visar en lista med jobb på den aktuella Azure Quantum-arbetsytan.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Visar resultat för ett jobb på den aktuella Azure Quantum-arbetsytan.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Visar status för ett jobb på den aktuella Azure Quantum-arbetsytan.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Skickar ett jobb till en Azure Quantum-arbetsyta.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Anger eller visar det aktiva körnings målet för Q# jobb överföring i en Azure Quantum-arbetsyta.

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
