---
title: Introduktion till Quantum Machine Learning-paketet | Microsoft Docs
description: Introduktion till Quantum Machine Learning-paketet
author: QuantumWriter
ms.author: alexeib@microsoft.com
ms.date: 12/5/2019
ms.topic: article
uid: microsoft.quantum.machine-learning.concepts.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2f8884fafd6370e4f70ec93e6fc8617c34c29431
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868856"
---
# <a name="introduction-to-the-quantum-machine-learning-library"></a><span data-ttu-id="b7c86-103">Introduktion till Quantum Machine Learning-biblioteket</span><span class="sxs-lookup"><span data-stu-id="b7c86-103">Introduction to the Quantum Machine Learning Library</span></span>

<span data-ttu-id="b7c86-104">Quantum Machine Learning-biblioteket är ett API, skrivet i Q#, som ger dig möjlighet att köra kvantbaserade/klassiska hybridexperiment för maskininlärning.</span><span class="sxs-lookup"><span data-stu-id="b7c86-104">The Quantum Machine Learning Library is an API, written in Q#, that gives you the ability to run hybrid quantum/classical machine learning experiments.</span></span> <span data-ttu-id="b7c86-105">Med biblioteket kan du:</span><span class="sxs-lookup"><span data-stu-id="b7c86-105">The library gives you the ability to:</span></span>

- <span data-ttu-id="b7c86-106">Läsa in dina egna data och klassificera med kvantsimulatorer</span><span class="sxs-lookup"><span data-stu-id="b7c86-106">Load your own data to classify with quantum simulators</span></span>

- <span data-ttu-id="b7c86-107">Använd exempel och självstudier för att bekanta dig med kvantmaskininlärning</span><span class="sxs-lookup"><span data-stu-id="b7c86-107">Use samples and tutorials to get introduced to the field of quantum machine learning</span></span>

<span data-ttu-id="b7c86-108">Du kan förvänta dig låga prestanda jämfört med aktuella klassiska ramverk för maskininlärning (kom ihåg att allt körs ovanpå simuleringen av en kvantenhet som beräkningsmässigt redan är mycket dyr).</span><span class="sxs-lookup"><span data-stu-id="b7c86-108">You can expect low performance compared to current classical machine learning frameworks (remember that everything is running on top of the simulation of a quantum device that is already computationally expensive).</span></span>

<span data-ttu-id="b7c86-109">Syftet med det här dokumentet är:</span><span class="sxs-lookup"><span data-stu-id="b7c86-109">The purpose of this documentation is:</span></span>

- <span data-ttu-id="b7c86-110">En kortfattad introduktion till maskininlärningsverktyg (skrivna i Q\#) för kvant-/klassisk maskininlärning.</span><span class="sxs-lookup"><span data-stu-id="b7c86-110">A concise introduction to machine learning tools (written in Q\#) for hybrid quantum/classical learning.</span></span>
- <span data-ttu-id="b7c86-111">Introducera maskininlärningskoncept och särskilt deras realisering i kvantkretscentrerade klassificerare (kallas även sekventiella kvantklassificerare).</span><span class="sxs-lookup"><span data-stu-id="b7c86-111">Introduce machine learning concepts and specifically their realization in quantum circuit centric classifiers (also known as quantum sequential classifiers).</span></span>
- <span data-ttu-id="b7c86-112">Tillhandahålla en serie självstudier om grunderna för att börja använda verktygen som finns i biblioteket.</span><span class="sxs-lookup"><span data-stu-id="b7c86-112">Provide a set of tutorials on the basics to start using the tools provided by the library.</span></span>
- <span data-ttu-id="b7c86-113">Beskriva inlärnings- och valideringsmetoderna för sådana klassificerare och hur de översätts till specifika Q\#-åtgärder som tillhandahålls av biblioteket.</span><span class="sxs-lookup"><span data-stu-id="b7c86-113">Discuss the training and validation methods for such classifiers and how they translate into specific Q\# operations provided by the library.</span></span>

<span data-ttu-id="b7c86-114">Modellen som implementeras i det här biblioteket baseras på det klassiska kvantinlärningsschemat som presenteras i [Kretsbaserade kvantklassificerare](https://arxiv.org/abs/1804.00633)</span><span class="sxs-lookup"><span data-stu-id="b7c86-114">The model implemented in this library is based on the quantum-classical training scheme presented in [Circuit-centric quantum classifiers](https://arxiv.org/abs/1804.00633)</span></span>
