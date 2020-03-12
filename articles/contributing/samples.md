---
title: Bidrags exempel till Microsoft QDK
description: Lär dig hur du bidrar med exempel kod till Microsoft Quantum Development Kit (QDK).
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024159"
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

Det vill säga att exemplen i [Microsoft/Quantum-lagringsplatsen](https://github.com/microsoft/Quantum) är uppdelade efter ämnes område i olika mappar, till exempel `algorithms/`, `arithmetic/`eller `characterization/`.
I mappen för varje ämnes område består varje exempel av en enda mapp som samlar in allt som en användare behöver för att utforska och använda det exemplet.

## <a name="how-samples-are-structured"></a>Hur exempel struktureras

Titta på de filer som utgör varje mapp, låt oss ta del av [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) exemplet.

| Fil              | Beskrivning                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | Q #-projekt som används för att bygga exemplet med .NET Core SDK |
| `Game.qs`         | Q #-åtgärder och-funktioner för exemplet                 |
| `Host.cs`         | C#värd programmet som används för att köra exemplet                     |
| `host.py`         | Python-värdprogram som används för att köra exemplet                 |
| `README.md`       | Dokumentation om vad exemplet gör och hur det används    |

Alla exempel har inte exakt samma uppsättning filer (t. ex. vissa exempel kan vara C#-bara, andra kanske inte har en python-värd eller vissa exempel kan kräva att auxillary-datafiler fungerar).

## <a name="anatomy-of-a-helpful-readme-file"></a>Beskrivning av en användbar README-fil

En särskilt viktig fil, men är `README.md`-filen, eftersom det är det som användarna behöver för att komma igång med ditt exempel!

Varje `README.md` bör inledas med vissa metadata som hjälper docs.microsoft.com/samples att hitta ditt bidrag.

> [!div class="nextstepaction"]
> [Se hur chsh-spel återges](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

Dessa metadata tillhandahålls som ett [yaml-huvud](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) som anger vilka språk som exemplet täcker (vanligt vis är det `qsharp`, `csharp`och `python`) och vilka produkter som exemplet täcker (vanligt vis `qdk`).

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> `page_type: sample` nyckel i sidhuvudet krävs för att exemplet ska visas på docs.microsoft.com/samples.
> På samma sätt är `product` och `language`s nycklar kritiska för att hjälpa användarna att hitta och köra ditt exempel.

Därefter är det bra att ge en kort introduktion som säger vad ditt nya exempel gör:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

Användare av exemplet kommer också att uppskatta vad de behöver för att köra det (t. ex.: användare behöver bara själva Quantum Development Kit eller behöver de ytterligare program vara som Node. js?):

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

Med allt det på plats kan du tala om för användarna hur de ska köra exemplet:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

Slutligen är det bra att berätta för användarna vad varje fil i exemplet gör och var de kan gå till mer information:

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> Se till att använda absoluta URL: er här eftersom exemplet visas på en annan URL när du återger på docs.microsoft.com/samples!
