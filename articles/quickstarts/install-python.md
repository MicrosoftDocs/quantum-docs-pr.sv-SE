---
title: Utveckla med Q# och Python
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274147"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="6a6f0-102">Utveckla med Q# och Python</span><span class="sxs-lookup"><span data-stu-id="6a6f0-102">Develop with Q# and Python</span></span>

<span data-ttu-id="6a6f0-103">Installera QDK:n om du vill utveckla Python-värdprogram som anropar Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="6a6f0-104">Krav</span><span class="sxs-lookup"><span data-stu-id="6a6f0-104">Prerequisites</span></span>

    - <span data-ttu-id="6a6f0-105">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="6a6f0-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="6a6f0-106">[PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare</span><span class="sxs-lookup"><span data-stu-id="6a6f0-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="6a6f0-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="6a6f0-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="6a6f0-108">Installera `qsharp`-paketet, vilket är ett Python-paket som ger interoperabilitet mellan Q# och Python.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="6a6f0-109">Installera IQ#, vilket är en kernel som främst används av Jupyter och Python och som innehåller grundläggande funktioner för att kompilera och köra Q#-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="6a6f0-110">Om du får ett felmeddelande under `dotnet iqsharp install`-steget, öppnar du ett nytt terminalfönster och försöker igen.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="6a6f0-111">Om det fortfarande inte fungerar kan du försöka hitta det installerade `dotnet-iqsharp`-verktyget (i Windows, `dotnet-iqsharp.exe`) och köra:</span><span class="sxs-lookup"><span data-stu-id="6a6f0-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="6a6f0-112">där `/path/to/dotnet-iqsharp` ersätts med den absoluta sökvägen till `dotnet-iqsharp`-verktyget i filsystemet.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="6a6f0-113">Den finns vanligtvis under `.dotnet/tools` i användarprofilens mapp.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="6a6f0-114">Även om du kan använda Q# med Python i en IDE, rekommenderar vi starkt att du använder IDE:n i Visual Studio Code (VS Code) till dina Q# + Python-program.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="6a6f0-115">När du använder Visual Studio Code och QDK-tillägget för Visual Studio Code, får du tillgång till fler funktioner.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="6a6f0-116">Installera [VS Code](https://code.visualstudio.com/download) (Windows, Linux och Mac)</span><span class="sxs-lookup"><span data-stu-id="6a6f0-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="6a6f0-117">Installera [QDK-tillägget för VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="6a6f0-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="6a6f0-118">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="6a6f0-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="6a6f0-119">Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:</span><span class="sxs-lookup"><span data-stu-id="6a6f0-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="6a6f0-120">Skapa ett Python-program med namnet `hello_world.py` som anropar åtgärden `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="6a6f0-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="6a6f0-121">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="6a6f0-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="6a6f0-122">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-122">Verify the output.</span></span> <span data-ttu-id="6a6f0-123">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="6a6f0-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="6a6f0-124">Du kan också använda Python Jupyter Notebooks till att skriva klassiska Python-program och anropa Q#-åtgärder från cellerna.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="6a6f0-125">Python-koden är bara ett vanligt Python-program.</span><span class="sxs-lookup"><span data-stu-id="6a6f0-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6a6f0-126">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="6a6f0-126">Next steps</span></span>

<span data-ttu-id="6a6f0-127">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="6a6f0-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
