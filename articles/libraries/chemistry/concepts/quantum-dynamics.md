---
title: Quantum Dynamics
description: Lär dig mer om likheter och skillnader mellan Quantum Dynamics och klassisk Dynamics.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 9cb74ccd4b7806a90c0701300860d777fa8e5d75
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904493"
---
# <a name="quantum-dynamics"></a>Quantum Dynamics

Quantum Mechanics är i stort sett en studie av Quantum Dynamics, som används för att förstå hur ett ursprungligt Quantum-tillstånd $ \ket{\psi (0)} $ varierar över tid (se [konceptuella dokument](xref:microsoft.quantum.concepts.dirac) för Quantum computing för mer information om Dirac-notation).
Särskilt, med tanke på detta första villkor, ett Quantum-tillstånd, en utvecklings tid och en specifikation av det Quantum-dynamiska systemet, kommer ett Quantum-tillstånd $ \ket{\psi (t)} $ att eftersträvas.
Innan du fortsätter med att förklara Quantum Dynamics är det praktiskt att gå tillbaka och tänka på klassiskt Dynamics eftersom det ger insikter om hur Quantum Mechanics egentligen inte skiljer sig från klassisk Dynamics.

I klassisk Dynamics vet vi från Newton s andra lag om att en partikels placering utvecklas enligt $F (x, t) = ma = m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, där $F (x, t) $ är kraften, $m $ är massan och $a $ är accelerationen.
Sedan, med utgångs punkt i en inledande position $x (0) $, utvecklings tid $t $ och beskrivning av de krafter som fungerar på partikeln, kan vi hitta $x (t) $ genom att lösa den differentiella ekvationen som erhålls av Newton-ekvationer för $x (t) $.
Att ange krafterna på det här sättet är lite smärta.
Vi brukar ofta uttrycka krafterna när det gäller systemets potentiella energi, vilket ger oss $-\ partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
För en partikel anges systemets dynamik endast av den potentiella energi funktionen, partikel massan och utvecklings tiden.

Ett bredare språk introduceras ofta för klassisk dynamik som går utanför $F = ma $.
En formulering, som är särskilt användbar i Quantum Mechanics, är Hamiltonian Mechanics.
I Hamiltonian Mechanics, den totala energin för ett system och de (generaliserade) positionerna och tidpunkten för att ge all information som behövs för att beskriva rörelsen i ett godtyckligt klassiskt objekt.
Mer specifikt kan $f (x, p, t) $ vara en del av de generaliserade positionerna $x $ och tag upp $p $ i ett system och låta $H (x, p, t) $ vara Hamiltonian-funktionen.
Om vi till exempel tar $f (x, p, t) = x (t) $ och $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, skulle vi återställa ovanstående fall av Newtonian Dynamics.
I allmänhet har vi den \begin{align} \frac{d}{DT} f & = \ partial_t f-(\ partial_x H \ partial_p f + \ partial_p H \ partial_x f)\\\\ & \defeq \ partial_t f + \\{f, H\\}.
\end{align} här $\\{f, H\\} $ kallas Poisson- [klammern](https://en.wikipedia.org/wiki/Poisson_bracket) och visas ubiquitously i klassiskt Dynamics på grund av den centrala rollen den spelar i definiera Dynamics.

Quantum Dynamics kan beskrivas med exakt samma språk.
Hamiltonian, eller den totala energin, anger att dynamiken för alla stängda Quantum-system är fullständigt.
Det finns dock några betydande skillnader mellan de två basreaktionsteorier.
I klassisk Mechanics $x $ och $p $ är bara siffror, medan de inte är i Quantum Mechanics.
De är faktiskt inte ens förfaller: $xp \ne BPT $.

Det högra matematiska konceptet för att beskriva dessa icke-arbetsobjekt är en operator, som i de fall där $x $ och $p $ bara kan ta en diskret uppsättning värden som sammanfaller med begreppet matris.
För enkelhetens skull antar vi därför att vårt Quantum-system är ändligt så att det kan beskrivas med [vektorer och matriser](xref:microsoft.quantum.concepts.vectors).
Vi kräver ytterligare att dessa matriser är Hermitian (vilket innebär att matrisen konjugat är densamma som den ursprungliga matrisen).
Detta garanterar att Eigenvalues för matriserna är verkliga värden. ett villkor som vi vidtar för att säkerställa att när vi mäter en kvantitet som position som vi inte får tillbaka ett imaginärt nummer.

Precis som de jämförbara positionerna och momenten i Quantum Mechanics måste ersättas av operatörer måste Hamiltonian-funktionen ersättas av en operator.
För en partikel i ledigt utrymme har vi till exempel $H (x, p) = p ^ 2/2 m $, i Quantum Mechanics Hamiltonian-operatören $ \hat{H} $ är $ \hat{H} = \hat{p} ^ 2/2 m $ där $ \hat{p} $ är operatorn för momentet.
Från och med i det här perspektivet, kommer från klassisk till Quantum Dynamics bara att ersätta variablerna som används i vanliga Dynamics med operatörer.
När vi har konstruerat Hamiltonian-operatören genom att översätta den vanliga klassiska klassisk Hamiltonian till Quantum language, kan vi uttrycka dynamiken i en godtycklig, mekanisk mekanisk mängd (d.v.s. en Quantum mekanisk operatör) $ \hat{f} (t) $ via \begin{ align} \frac{d}{DT} \hat{f} = \ partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} där $ [f, H] = fH-HF $ kallas commutator.
Det här uttrycket är exakt likadant som det klassiska uttrycket som anges ovan med skillnaden att Poisson-klammern $\\{f, H\\} $ ersätts med commutator mellan $f $ och $H $.
Den här processen att ta en klassisk Hamiltonian och använda den för att hitta en Quantum Hamiltonian är känd i Quantum jargong som kanonisk kvantifieringsfel.

Vilka operatörer $f $ är vi mest intresse rad av?  Svaret på detta beror på problemet som vi vill lösa.
Kanske är den mest användbara mängden att hitta är operatorn Quantum, som beskrivs i den tidigare konceptuella dokumentationen kan användas för att extrahera allt som vi vill veta om Dynamics.
När du har gjort detta (och förenkla resultatet om det är ett rent tillstånd), hittas Schrödinger-ekvationen för Quantum-tillstånd \begin{align} i \ partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

Den här ekvationen, men kanske mindre intuitivt än vad som nämnts ovan, ger kanske det enklaste uttrycket för att förstå hur du simulerar Quantum Dynamics på antingen en Quantum eller klassisk dator.
Detta beror på att lösningen till den differentiella ekvationen kan uttryckas i följande format (för det fall där Hamiltonian är konstant i $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} här $e ^ {-iHt} $ är en enhetlig matris.
Det innebär att det finns en Quantum-krets som kan utformas för att utföra det eftersom quantum datorer kan likna en enhetlig matris.
Det här är en Quantum-krets som används för att implementera den väntande tids utvecklings operatören $e ^ {-iHt} $ är vad som ofta kallas Quantum-simulering eller i synnerhet en dynamisk simulering av en dynamisk Quantum-simulering.
