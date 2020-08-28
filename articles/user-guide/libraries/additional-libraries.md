---
title: Använda ytterligare Q# bibliotek
description: Lär dig hur du lägger till ytterligare Q# bibliotek i dina Quantum-program.
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: 39bf7dc52f4670a6e4536efc437d001c96f9584a
ms.sourcegitcommit: 11bd357baeb6ab53a402882979e75964d0869b57
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "88992147"
---
# <a name="using-additional-no-locq-libraries"></a>Använda ytterligare Q# bibliotek

Quantum Development Kit innehåller ytterligare domänfunktionalitet med _NuGet-paket_ som kan läggas till i dina Q# projekt.

| Q# Bibliotek  | NuGet-paket | Anteckningar |
|---------|---------|--------|
| [Q# standard bibliotek](xref:microsoft.quantum.libraries.standard.intro) | [**Microsoft. Quantum. standard**](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | Ingår som standard |
| [Bibliotek för kvantkemi](xref:microsoft.quantum.chemistry.concepts.intro) | [**Microsoft.Quantum.Chemistry**](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [Bibliotek för kvantmatematik](xref:microsoft.quantum.numerics.intro) | [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [Bibliotek för kvantmaskininlärning](xref:microsoft.quantum.libraries.machine-learning.intro) | [**Microsoft.Quantum.MachineLearning**](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

När du har installerat Quantum Development Kit för användning med din önskade miljö och ditt värd språk kan du enkelt lägga till bibliotek i enskilda Q# projekt utan någon ytterligare installation.

> [!NOTE]
> Vissa Q# bibliotek kan fungera bra med ytterligare verktyg som fungerar tillsammans Q# med dina program eller som integreras med dina värd program.
> [Installations anvisningarna för kemi Library](xref:microsoft.quantum.chemistry.concepts.installation) beskriver till exempel hur du använder [ **Microsoft. Quantum. kemi** -paketet](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) tillsammans med NWChem-plattformen för beräknings kemi och hur du installerar `qdk-chem` kommando rads verktygen för att arbeta med Quantum kemi-data.

## <a name="no-locq-applications-or-net-interopability"></a>[Q# program eller .NET-interop](#tab/tabid-csproj)

**Kommando tolk eller Visual Studio-kod:** Med hjälp av kommando tolken på egen hand eller i Visual Studio Code kan du använda `dotnet` kommandot för att lägga till en NuGet-paket referens i projektet.
Om du till exempel vill lägga till paketet [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) kör du följande kommando:

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

**Visual Studio:** Om du använder Visual Studio 2019 eller senare kan du lägga till ytterligare Q# paket med NuGet Package Manager.
Så här läser du in ett paket: 
1. Öppna ett projekt i Visual Studio och välj **Hantera NuGet-paket...** från **projekt** -menyn.

2. Klicka på **Bläddra**, Välj **Inkludera för hands version** och Sök efter paket namnet "Microsoft. Quantum. numeric". Detta visar de paket som är tillgängliga för nedladdning.

3. Hovra över **Microsoft. Quantum. numeric** och klicka på pilen som pekar nedåt till höger om versions numret för att installera det numeriska paketet.

Mer information finns i UI- [guiden för paket hanteraren](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Du kan också använda Package Manager-konsolen för att lägga till ett numeriskt bibliotek i projektet via kommando rads gränssnittet.

![Använda Package Manager-konsolen från kommando tolken](~/media/vs2017-nuget-console-menu.png)

Kör följande från Package Manager-konsolen:

```
Install-Package Microsoft.Quantum.Numerics
```

Mer information finns i Guide till [Package Manager-konsolen](https://docs.microsoft.com/nuget/tools/package-manager-console).

## <a name="ino-locq-notebooks"></a>[I Q# antecknings böcker](#tab/tabid-notebook)

Du kan göra ytterligare paket tillgängliga för användning i en I- Q# anteckningsbok med hjälp av [ `%package` kommandot Magic](xref:microsoft.quantum.iqsharp.magic-ref.package).
Om du till exempel vill lägga till paketet [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) för användning I en i Q# -anteckningsbok, kör du följande kommando i en Notebook-cell:

```
%package Microsoft.Quantum.Numerics
```

Efter det här kommandot är paketet tillgängligt för alla celler i antecknings boken.
Om du vill göra paketet tillgängligt från Q# kod i den aktuella arbets ytan läser du in arbets ytan igen när du har lagt till ditt paket:

```
%workspace reload
```

## <a name="python-interoperability"></a>[Python-interoperabilitet](#tab/tabid-python)


Du kan göra ytterligare paket tillgängliga för användning i ett python-värdprogram med hjälp av- [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp-core/qsharp.packages.packages) metoden.
Om du till exempel vill lägga till paketet [**Microsoft. Quantum. numeric**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) för användning I en i Q# -anteckningsbok kör du följande python-kod:

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

Efter det här kommandot kommer paketet att göras tillgängligt för all Q# kod som kompileras med `qsharp.compile` .
Om du vill göra paketet tillgängligt från Q# kod i den aktuella arbets ytan läser du in arbets ytan igen när du har lagt till ditt paket:

```python
qsharp.reload()
```

***
