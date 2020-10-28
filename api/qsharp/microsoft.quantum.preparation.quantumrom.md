---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Funktionen QuantumROM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92732622"
---
# <a name="quantumrom-function"></a>Funktionen QuantumROM

Namnrymd: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Paketfilerna [](https://nuget.org/packages/)


Använder Quantum ROM-tekniken för att representera en bestämd densitet.

Med en lista med $N $ koefficienter $ \ alpha_j $, returnerar detta en enhetlig $U $ som använder Quantum-ROM-tekniken för att förbereda en uppskattning $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ av reningen av densitets mat ris $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $. I den här uppskattningen är felet $ \epsilon $ sådant som $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \le \epsilon/N $ och $ \| \tilde\rho-\rho \| \le \epsilon $. Med andra ord, $ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\rceil} \ ket {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{Garbage} _J}.
\end{align} $ $

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Indata

### <a name="targeterror--double"></a>targetError: [dubbel](xref:microsoft.quantum.lang-ref.double)

Mål felet $ \epsilon $.


### <a name="coefficients--double"></a>koefficienter: [dubbla](xref:microsoft.quantum.lang-ref.double)[]

Matris med $N $-koefficienter som anger sannolikheten för bas tillstånd.
Negativa tal $-\ alpha_j $ kommer att behandlas som positivt $ | \ alpha_j | $.



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a>Utdata: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [enhets](xref:microsoft.quantum.lang-ref.unit) justering + CTL)

## <a name="first-parameter"></a>Första parametern

En tupel `(x,(y,z))` där `x = y + z` är det totala antalet tilldelade qubits, `y` är antalet qubits för `LittleEndian` registret och `z` är antalet skräp qubits.

## <a name="second-parameter"></a>Andra parameter

Den enpresterande $ \ sum_j | \ alpha_j | $ för den effektiva matrisen.

## <a name="third-parameter"></a>Tredje parametern

Den enhetliga $U $.

## <a name="references"></a>Referenser

- Koda elektroniska Spectra i Quantum-kretsar med linjär T-komplexitet Ryan Babbush, Craig Gidney, Dominic W. bär, Nathan Wiebe, Jarrod McClean, Alexandru mattare, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662