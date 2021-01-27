---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: Funktionen BigEndianAsLittleEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843374"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="8a0d9-102">Funktionen BigEndianAsLittleEndian</span><span class="sxs-lookup"><span data-stu-id="8a0d9-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="8a0d9-103">Namnrymd: [Microsoft. Quantum. aritmetisk](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8a0d9-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8a0d9-105">Konverterar ett `BigEndian` qubit-register till ett `LittleEndian` qubit-register genom att kasta om qubit-ordningen.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="8a0d9-106">Indata</span><span class="sxs-lookup"><span data-stu-id="8a0d9-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="8a0d9-107">inmatade: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="8a0d9-108">Qubit-register i `BigEndian` format.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="8a0d9-109">Utdata: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="8a0d9-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="8a0d9-110">Qubit-register i `LittleEndian` format.</span><span class="sxs-lookup"><span data-stu-id="8a0d9-110">Qubit register in `LittleEndian` format.</span></span>