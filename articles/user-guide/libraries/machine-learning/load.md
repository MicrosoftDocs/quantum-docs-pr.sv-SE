---
title: Läser in klassiska data
description: Lär dig hur du läser in en egen data uppsättning för att träna en klassificerings modell med Microsoft Quantum Development Kit (QDK).
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868839"
---
# <a name="load-and-classify-your-own-datasets"></a>Läs in och klassificera dina egna data uppsättningar

I den här korta självstudien ska vi lära dig hur du läser in din egen data uppsättning för att träna en klassificerings modell med Quantum Development Kit (QDK).

Vi rekommenderar starkt att du använder ett standardiserat serialiserat format, till exempel [JSON-filer](https://en.wikipedia.org/wiki/JSON) , för att lagra dina data.
Sådana format ger hög kompatibilitet med olika ramverk som python och .NET-eko systemet.
Vi rekommenderar särskilt att du använder vår mall för att läsa in data, så att du kan kopiera och klistra in koden direkt från exemplen.

## <a name="template-for-loading-your-datasets"></a>Mall för att läsa in dina data uppsättningar

Anta att vi har en tränings data uppsättning $ (x, y) $ med storlek $N = $2 där varje instans $x _i $ $x $ har tre funktioner: $x _ {I1} $, $x _ {I2} $ och $x _ {i3} $.
Verifierings data uppsättningen har samma struktur.
Dessa datsets kan representeras av en `data.json` fil som liknar följande:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Exempel som använder mallen

Anta att vi har en liten data uppsättning med höjd och vikt för olika katter och hundar. Den här data uppsättningen är mycket liten för att träna en modell, men det räcker att Visa processen för att läsa in en data uppsättning.

| Höjd (m) | Vikt (kg) | Animalie |
|-----------|------------|--------|
| 0,54      | 30         | Hunden    |
| 0,30      | 8          | Lat    |
| 0,91      | 44         | Hunden    |
| 0,86      | 31          | Hunden    |
| 0,32      | 5         | Lat    |
| 0,25      | 4          | Lat    |

Processen är:

- Först måste vi separera data uppsättningen till utbildning och verifiering. I det här fallet kan vi bara ta de tre första exemplen för utbildning och resten av exemplen för verifiering. I allmänhet är det en bra idé att slumpmässigt testa inlärnings-och validerings data uppsättningen för att undvika oönskade kompensationer i tränings data.
- För det andra måste vi tilldela en numerisk etikett till varje klass. Observera att för tillfället QML-biblioteket endast admits binära klassificerings problem. Vi kommer att tilldela etiketten 0 till klassen `Dog` och siffran 1 till klassen `Cat` .
- Slutligen fyller vi mallen med hjälp av data från vår data uppsättning. Observera att för stora data uppsättningar bör du skapa ett litet skript för att automatiskt generera mallen från din specifika data uppsättning. Det här skriptet beror på data uppsättningens ursprungliga format.

För vår data uppsättning `data.json` är filen:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Läsa in data

När du har serialiserat dina data som en JSON-fil kan du läsa in dem i med hjälp av JSON-bibliotek som ingår i det valda värd språket.

### <a name="python"></a>[Python](#tab/tabid-python)

Python tillhandahåller det [inbyggda `json` paketet](https://docs.python.org/3.7/library/json.html) för att arbeta med JSON-serialiserade data:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

.NET Core Platform tillhandahåller [ `System.Text.Json` paketet](https://www.nuget.org/packages/System.Text.Json) för att arbeta med JSON-serialiserade data:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Nästa steg

Nu är du redo att börja köra dina egna experiment med dina egna data uppsättningar. Prova olika klassificerare och data uppsättningar och bidra till communityn som delar dina resultat!
