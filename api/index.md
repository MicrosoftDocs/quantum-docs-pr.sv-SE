---
uid: microsoft.quantum.standardlibsintro
title: Q#-standardbibliotek för Microsoft Quantum
description: Referensdokumentation till Q#-standardbiblioteket för Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999087"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="88dd0-103">Q#-standardbibliotek</span><span class="sxs-lookup"><span data-stu-id="88dd0-103">Q# standard libraries</span></span> #

<span data-ttu-id="88dd0-104">Q# stöds av olika användbara åtgärder, funktioner och användardefinierade typer som utgör Q#-*standardbiblioteket*.</span><span class="sxs-lookup"><span data-stu-id="88dd0-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="88dd0-105">Q#-standardbiblioteket är uppdelat i två huvuddelar:</span><span class="sxs-lookup"><span data-stu-id="88dd0-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="88dd0-106">**Inledning**: Åtgärder och funktioner som definieras som en del av måldatorn och kompileraren, vanligtvis i klassiskt inbyggd .NET-kod.</span><span class="sxs-lookup"><span data-stu-id="88dd0-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="88dd0-107">I allmänhet kan olika måldatorer ha olika implementeringar av inledningen som är lämpliga för de olika systemen.</span><span class="sxs-lookup"><span data-stu-id="88dd0-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="88dd0-108">**Kanoniskt**: Åtgärder och funktioner som definieras i Q# bygger på den logik som definierats i inledningen.</span><span class="sxs-lookup"><span data-stu-id="88dd0-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="88dd0-109">Den kanoniska implementeringen är inte beroende av måldatorerna.</span><span class="sxs-lookup"><span data-stu-id="88dd0-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="88dd0-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="88dd0-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>