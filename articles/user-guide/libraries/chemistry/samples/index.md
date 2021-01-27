---
title: Exempelprogram för kvantkemi
description: Utforska exempelprogram i Microsofts kvantkemibibliotek.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: conceptual
uid: microsoft.quantum.chemistry.examples
no-loc:
- Q#
- $$v
ms.openlocfilehash: b2a8740f9c94ca733e24012aaf5c80b15b731c2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858925"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="47584-103">Exempel för kvantkemi</span><span class="sxs-lookup"><span data-stu-id="47584-103">Quantum chemistry examples</span></span>

<span data-ttu-id="47584-104">I begreppen för kvantkemi konstruerade vi exempel på fermion-hamiltonska värden manuellt.</span><span class="sxs-lookup"><span data-stu-id="47584-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="47584-105">Vi kombinerar nu de algoritmer för kemisimulering som beskrivs i [Simulera hamiltonsk dynamik](xref:microsoft.quantum.libraries.standard.algorithms) med [kvantfasberäkning](xref:microsoft.quantum.libraries.characterization) i Canon-biblioteket.</span><span class="sxs-lookup"><span data-stu-id="47584-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="47584-106">Med den här kombinationen kan vi få uppskattningar av energinivåer i den representerade molekylen, vilket är en av de viktigaste tillämpningarna av kvantkemi i en kvantdator.</span><span class="sxs-lookup"><span data-stu-id="47584-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="47584-107">I stället för att ange termerna för det hamiltonska värdet en i taget går vi igenom några exempel som gör att vi kan utföra experiment med kvantkemi i större skala.</span><span class="sxs-lookup"><span data-stu-id="47584-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="47584-108">Vi börjar med exempel som läser in ett kemiskt hamiltonskt värde som är kodat i [Broombridge-schemat](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span><span class="sxs-lookup"><span data-stu-id="47584-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="47584-109">För molekyler som är för stora för att simuleras i [simulatorn med fullständigt tillstånd](xref:microsoft.quantum.machines.full-state-simulator) går det ändå att utföra intressant vetenskap.</span><span class="sxs-lookup"><span data-stu-id="47584-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="47584-110">Till exempel kan resurskostnaderna för att utföra stora kemisimuleringar fortfarande utvärderas genom riktning mot [spårningssimulatorn](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span><span class="sxs-lookup"><span data-stu-id="47584-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="47584-111">Nu illustrerar vi intressanta tillämpningar av biblioteket för kemisimulering med några av de medföljande exemplen.</span><span class="sxs-lookup"><span data-stu-id="47584-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>
