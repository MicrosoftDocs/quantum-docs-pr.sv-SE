---
title: Bidrags exempel till Microsoft QDK
description: Lär dig hur du bidrar med exempel kod till Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.samples
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0c940a4cf228c694a899988f469158b1bb6e2425
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847590"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a>Bidra till exempel i Quantum Development Kit

Om du är intresse rad av att bidra med kod till [exempel lagrings platsen](https://github.com/Microsoft/Quantum), tack för att du gör miljön Quantum Development en bättre plats!

## <a name="the-quantum-development-kit-samples-repository"></a>Exempel databasen för Quantum Development Kit

För att hjälpa dig att förbereda ditt bidrag för att få ut så mycket som möjligt, är det bra att ta en titt på hur lagrings platsen upprättas:

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

Det vill säga att exemplen i [Microsoft/Quantum-lagringsplatsen](https://github.com/microsoft/Quantum) är uppdelade efter ämnes område i olika mappar som `algorithms/` , `arithmetic/` eller `characterization/` .
I mappen för varje ämnes område består varje exempel av en enda mapp som samlar in allt som en användare behöver för att utforska och använda det exemplet.

## <a name="how-samples-are-structured"></a>Hur exempel struktureras

Vi tittar på de filer som utgör varje mapp, låt oss ta en titt på [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/chsh-game) exemplet.

| Fil              | Description                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q# projekt som används för att bygga exemplet med .NET Core SDK |
| `Game.qs`         | Q# funktioner och funktioner för exemplet                 |
| `Host.cs`         | C#-värd program som används för att köra exemplet                     |
| `host.py`         | Python-värdprogram som används för att köra exemplet                 |
| `README.md`       | Dokumentation om vad exemplet gör och hur det används    |

Alla exempel har inte exakt samma uppsättning filer (t. ex. vissa exempel kan vara C#-endast, andra kanske inte har en python-värd, eller så kan vissa exempel kräva att auxillary-datafiler fungerar).

## <a name="anatomy-of-a-helpful-readme-file"></a>Beskrivning av en användbar README-fil

En särskilt viktig fil, men är `README.md` filen, eftersom det är det som användarna behöver för att komma igång med ditt exempel!

Varje `README.md` ska börja med vissa metadata som hjälper docs.Microsoft.com/samples att hitta ditt bidrag.

> [!div class="nextstepaction"]
> [Se hur chsh-spel återges](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Dessa metadata tillhandahålls som ett [yaml-huvud](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) som anger vilka språk som exemplet täcker (vanligt vis är detta, `qsharp` `csharp` och `python` ) och vilka produkter som exemplet täcker (vanligt vis `qdk` ).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample`Nyckeln i rubriken krävs för att exemplet ska visas på docs.Microsoft.com/samples.
> På samma sätt `product` är och `language` nycklarna kritiska för att hjälpa användarna att hitta och köra ditt exempel.

Därefter är det bra att ge en kort introduktion som säger vad ditt nya exempel gör:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Användare av exemplet kommer också att uppskatta vad de behöver för att köra det (t. ex.: användare behöver bara själva Quantum Development Kit eller behöver de ytterligare program vara som node.js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Med allt det på plats kan du tala om för användarna hur de ska köra exemplet:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Slutligen är det bra att berätta för användarna vad varje fil i exemplet gör och var de kan gå till mer information:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Se till att använda absoluta URL: er här eftersom exemplet visas på en annan URL när du återger på docs.microsoft.com/samples!
