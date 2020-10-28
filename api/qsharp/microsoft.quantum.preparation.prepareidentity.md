---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity-åtgärd
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92733726"
---
# <a name="prepareidentity-operation"></a><span data-ttu-id="a5e3d-102">PrepareIdentity-åtgärd</span><span class="sxs-lookup"><span data-stu-id="a5e3d-102">PrepareIdentity operation</span></span>

<span data-ttu-id="a5e3d-103">Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a5e3d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a5e3d-104">Paketfilerna [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5e3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5e3d-105">Med en registrerad registrering förbereder vi registreringen i maximally blandat läge.</span><span class="sxs-lookup"><span data-stu-id="a5e3d-105">Given a register, prepares that register in the maximally mixed state.</span></span>

<span data-ttu-id="a5e3d-106">Registret förbereds i läget $ \boldone/2 ^ N $ genom att tillämpa den fullständiga avpolarisering-kanalen på varje qubit, där $N $ är registrerings längden.</span><span class="sxs-lookup"><span data-stu-id="a5e3d-106">The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.</span></span>

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="a5e3d-107">Indata</span><span class="sxs-lookup"><span data-stu-id="a5e3d-107">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="a5e3d-108">Registrera: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a5e3d-108">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a5e3d-109">Ett register vars tillstånd ska avsättas på det sätt som beskrivs ovan.</span><span class="sxs-lookup"><span data-stu-id="a5e3d-109">A register whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5e3d-110">Utdata: [enhet](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5e3d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="a5e3d-111">Se även</span><span class="sxs-lookup"><span data-stu-id="a5e3d-111">See Also</span></span>

- [<span data-ttu-id="a5e3d-112">Microsoft. Quantum. preparation. PrepareSingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="a5e3d-112">Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity</span></span>](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)