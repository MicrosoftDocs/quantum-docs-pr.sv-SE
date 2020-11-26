---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity-åtgärd
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: 6e0a43e61e3c49edef94db63f07ed29132d84c83
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210445"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="a8add-102">PrepareIdentity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a8add-102">PrepareIdentity operation</span></span>

<span data-ttu-id="a8add-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a8add-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a8add-104">Paket: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a8add-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a8add-105">Med en registrerad registrering förbereder vi registreringen i maximally blandat läge.</span><span class="sxs-lookup"><span data-stu-id="a8add-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="a8add-106">Registret förbereds i läget $ \boldone/2 ^ N $ genom att tillämpa den fullständiga avpolarisering-kanalen på varje qubit, där $N $ är registrerings längden.</span><span class="sxs-lookup"><span data-stu-id="a8add-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a8add-107">Indata</span><span class="sxs-lookup"><span data-stu-id="a8add-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="a8add-108">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a8add-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a8add-109">Ett register vars tillstånd ska avsättas på det sätt som beskrivs ovan.</span><span class="sxs-lookup"><span data-stu-id="a8add-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a8add-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8add-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a8add-111">Se även</span><span class="sxs-lookup"><span data-stu-id="a8add-111">See Also</span></span>

- [<span data-ttu-id="a8add-112">Microsoft. Quantum. preparation. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="a8add-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)