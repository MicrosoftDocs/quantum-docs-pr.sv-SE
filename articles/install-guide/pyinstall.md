---
title: Utveckla med Q# och Python
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: e1b8a0c68b3ac0c059c6de6e478593321764ff88
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680152"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="00d9b-102">Utveckla med Q# och Python</span><span class="sxs-lookup"><span data-stu-id="00d9b-102">Develop with Q# + Python</span></span>

<span data-ttu-id="00d9b-103">Installera QDK för att utveckla python-värdprogram för att anropa Q #-åtgärder.</span><span class="sxs-lookup"><span data-stu-id="00d9b-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="00d9b-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="00d9b-104">Pre-requisites</span></span>

    - <span data-ttu-id="00d9b-105">[Python](https://www.python.org/downloads/) 3.6 eller senare</span><span class="sxs-lookup"><span data-stu-id="00d9b-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="00d9b-106">[PIP](https://pip.pypa.io/en/stable/installing) Python-pakethanterare</span><span class="sxs-lookup"><span data-stu-id="00d9b-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="00d9b-107">.NET Core SDK 3,1 eller senare</span><span class="sxs-lookup"><span data-stu-id="00d9b-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="00d9b-108">Installera `qsharp` paketet, ett python-paket som aktiverar interop mellan Q # och python.</span><span class="sxs-lookup"><span data-stu-id="00d9b-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="00d9b-109">Installera SWEETIQ #, en kernel som används av Jupyter och python och som tillhandahåller grundläggande funktioner för att kompilera och köra frågor i Q #.</span><span class="sxs-lookup"><span data-stu-id="00d9b-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="00d9b-110">Även om du kan använda Q # med python i en IDE, rekommenderar vi starkt att du använder Visual Studio Code (VS Code) IDE för dina Q # + python-program.</span><span class="sxs-lookup"><span data-stu-id="00d9b-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="00d9b-111">Genom att använda Visual Studio Code och QDK Visual Studio Code-tillägget får du till gång till mer avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="00d9b-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="00d9b-112">Installera [vs Code](https://code.visualstudio.com/download) (Windows, Linux och Mac)</span><span class="sxs-lookup"><span data-stu-id="00d9b-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="00d9b-113">Installera [QDK-tillägget för vs Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span><span class="sxs-lookup"><span data-stu-id="00d9b-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="00d9b-114">Verifiera installationen genom att skapa ett `Hello World`-program</span><span class="sxs-lookup"><span data-stu-id="00d9b-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="00d9b-115">Skapa en minimal Q#-åtgärd genom att skapa en fil med namnet `Operation.qs` och lägg till följande kod i den:</span><span class="sxs-lookup"><span data-stu-id="00d9b-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="00d9b-116">Skapa ett Python-program med namnet `hello_world.py` som anropar åtgärden `SayHello()` Q#:</span><span class="sxs-lookup"><span data-stu-id="00d9b-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="00d9b-117">Kör programmet:</span><span class="sxs-lookup"><span data-stu-id="00d9b-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="00d9b-118">Verifiera utdata.</span><span class="sxs-lookup"><span data-stu-id="00d9b-118">Verify the output.</span></span> <span data-ttu-id="00d9b-119">Följande rader ska visas av programmet:</span><span class="sxs-lookup"><span data-stu-id="00d9b-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="00d9b-120">Du kan också använda python Jupyter Notebooks för att skriva det klassiska python-programmet och anropa Q #-åtgärder från cellerna.</span><span class="sxs-lookup"><span data-stu-id="00d9b-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="00d9b-121">Python-koden är bara ett vanligt python-program.</span><span class="sxs-lookup"><span data-stu-id="00d9b-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="00d9b-122">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="00d9b-122">What's next?</span></span>

<span data-ttu-id="00d9b-123">Nu när du har installerat Quantum Development Kit i din önskade miljö, kan du skriva och köra [ditt första kvantprogram](xref:microsoft.quantum.write-program).</span><span class="sxs-lookup"><span data-stu-id="00d9b-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
