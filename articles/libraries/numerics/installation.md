---
title: Installation och validering av numeriska bibliotek | Microsoft Docs
description: Installation och validering av numeriska bibliotek
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184635"
---
# <a name="numerics-library-installation-and-validation"></a>Installation och validering av numeriska bibliotek

Quantum Development Kit har stöd för numeriska funktioner via [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet-paketet.

**Visual Studio-> = 2019:** Om du använder Visual Studio 2019 eller senare kan du lägga till det numeriska paketet med hjälp av NuGet Package Manager.
Det gör du genom att välja "hantera NuGet-paket..." från meny alternativet "Project" i Visual Studio.

På fliken Bläddra söker du efter paket namnet "Microsoft. Quantum. numeric"

> [!NOTE]
> Se till att kryssa för "inkludera för hands version"

Detta visar de paket som är tillgängliga för nedladdning.
Om du hovrar över "Microsoft. Quantum. numeric", visar en nedåtriktad pil till höger om versions numret.
Klicka på pilen för att installera det numeriska paketet.

Mer information finns i UI- [guiden för paket hanteraren](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Du kan också använda Package Manager-konsolen för att lägga till ett numeriskt bibliotek i projektet via kommando rads gränssnittet.

![](~/media/vs2017-nuget-console-menu.png)

Kör följande från Package Manager-konsolen:

```
Install-Package Microsoft.Quantum.Numerics
```

Mer information finns i Guide till [Package Manager-konsolen](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Kommando rad eller Visual Studio Code:** Med hjälp av kommando raden i sin egen eller från Visual Studio Code, kan du använda kommandot `dotnet` för att lägga till NuGet-paket referens i projektet:

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a>Verifiera installationen

Precis som resten av Quantum Development Kit, innehåller det numeriska biblioteket exempel som hjälper dig att komma igång så snabbt som möjligt.
Om du vill testa installationen med hjälp av dessa exempel klonar du [huvud exempel lagrings platsen](https://github.com/Microsoft/Quantum) och kör sedan ett av exemplen.

Så här kör du [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) exemplet:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```