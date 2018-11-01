---
title: 2.7.2.5 default
ms.date: 11/04/2016
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
ms.openlocfilehash: efb10913b74ebfae37c95d057955c87bdcfca9a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580225"
---
# <a name="2725-default"></a>2.7.2.5 default

Die **Standard** Klausel ermöglicht dem Benutzer, die Datenfreigabe-Attribute von Variablen beeinflussen. Die Syntax der **Standard** -Klausel ist wie folgt:

```
default(shared | none)
```

Angeben **default(shared)** ist gleichbedeutend mit einzelnen aktuell sichtbare Variablen im explizit Auflisten einer **freigegebenen** -Klausel, es sei denn, es ist **Threadprivate** oder **Nachteile**`t`-qualifizierten. In Abwesenheit einer expliziten **Standard** -Klausel, das Standardverhalten ist identisch mit If **default(shared)** wurden angegeben.

Angeben von **default(none)** erfordert, dass mindestens eine der folgenden für jeden Verweis auf eine Variable in der lexikalischen Wertebereich das parallele Konstrukt "true" sein muss:

- Die Variable wird explizit in einem Attribut Datenfreigabeklausel eines Konstrukts aufgeführt, die den Verweis enthält.

- Die Variable wird in das parallele Konstrukt deklariert.

- Die Variable ist **Threadprivate**.

- Die Variable hat einen **const**-qualifizierten Typ.

- Die Variable ist die Schleifensteuerungsvariable für eine **für** Schleife, die unmittelbar folgt einem **für** oder **für parallele** Richtlinie und den Variablen Verweis angezeigt wird, innerhalb der Schleife .

Gibt eine Variable auf einen **Firstprivate**, **Lastprivate**, oder **Verringerung** -Klausel von einer eingeschlossenen-Direktive verwenden, einen impliziten Verweis auf die Variable in der einschließenden Kontext. Solche impliziten verweisen, sind auch gemäß den oben aufgeführten Anforderungen.

Nur eine einzige **Standard** -Klausel angegeben werden kann, auf eine **parallele** Richtlinie.

Eine Variable des Standard-Datenfreigabe-Attribut werden, indem überschrieben kann die **private**, **Firstprivate**, **Lastprivate**, **Verringerung**, und **freigegebenen** -Klauseln, wie im folgenden Beispiel gezeigt:

```
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\
   private(x)  private(r)  lastprivate(i)
```