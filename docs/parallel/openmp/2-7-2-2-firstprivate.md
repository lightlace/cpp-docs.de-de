---
title: 2.7.2.2 firstprivate
ms.date: 11/04/2016
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
ms.openlocfilehash: f981c66fd3e0a2f42dcf731954f5054f96ed2973
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605971"
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

Die **Firstprivate** -Klausel bietet eine Obermenge von der Funktionalität der **private** Klausel. Die Syntax der **Firstprivate** -Klausel ist wie folgt:

```
firstprivate(variable-list)
```

Variablen in *Variablenliste* haben **private** Klausel-Semantik, wie in beschrieben [Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25. Die Initialisierung oder Erstellung des geschieht, als ob er einmal pro Thread, vor der Ausführung des Threads, der das Konstrukt ausgeführt wurden. Für eine **Firstprivate** -Klausel für eine parallele Konstrukt, der Anfangswert des neuen private-Objekts ist der Wert des ursprünglichen Objekts, das unmittelbar vor das parallele Konstrukt für den Thread vorhanden ist, die es trifft. Für eine **Firstprivate** -Klausel für ein Freigeben von Arbeitsaufgaben-Konstrukt, der Anfangswert des neuen Objekts private für jeden Thread, der die gemeinsame Verwendung von Arbeit Konstrukt ausgeführt wird. ist der Wert des ursprünglichen Objekts, das vor dem Zeitpunkt vorhanden ist, im gleiche Thread auftritt, das Freigeben von Arbeitsaufgaben-Konstrukt. Darüber hinaus wird für C++-Objekte, das neue private Objekt für jeden Thread Kopie aus dem ursprünglichen Objekt erstellt ist.

Die Einschränkungen fest, die **Firstprivate** Klausel lauten wie folgt:

- Eine Variable, die im angegebenen ein **Firstprivate** Klausel darf keinen, einen unvollständigen Typ oder ein Verweistyp.

- Eine Variable mit einem Klassentyp, der als angegeben wird **Firstprivate** benötigen eine erreichbare, eindeutige Kopierkonstruktor.

- Variablen, die innerhalb eines parallelen Bereichs privat sind, bzw. die angezeigt werden, in, der **Verringerung** -Klausel eine **parallele** Richtlinie kann nicht angegeben werden, eine **Firstprivate** -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.