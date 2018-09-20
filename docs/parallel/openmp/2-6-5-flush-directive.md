---
title: 2.6.5 flush-Direktive | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d67453b636d50fcb78092318ebb76f5192817548
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442733"
---
# <a name="265-flush-directive"></a>2.6.5 flush-Anweisung

Die **leeren** -Direktive, ob die explizite oder implizite Gewährleistung aus, gibt an, an dem die Implementierung erforderlich ist, um sicherzustellen, dass alle Threads in einem Team eine konsistente Sicht der bestimmte Objekte (unten angegeben) in, ein Sequenzpunkt auf "threadübergreifende" Arbeitsspeicher. Dies bedeutet, dass die vorherige auswertungen von Ausdrücken, die auf diese Objekte verweisen, die abgeschlossen sind und nachfolgende auswertungen noch nicht. Z. B. Compiler müssen die Werte der Objekte von Registern wiederherstellen, auf den Speicher und Hardware möglicherweise leeren Puffer schreiben, in den Speicher und die Werte der Objekte aus dem Speicher erneut zu laden.

Die Syntax der **leeren** Richtlinie lautet wie folgt:

```
#pragma omp flush [(variable-list)]  new-line
```

Wenn die Objekte, die Synchronisierung erfordern können alle Variablen festgelegt werden, können diese Variablen angegeben werden, in der optionalen *Variablenliste*. Wenn ein Zeiger in vorhanden ist. die *Variablenliste*, wird der Zeiger selbst geleert, nicht das Objekt der Zeiger verweist auf.

Ein **leeren** Direktive ohne eine *Variablenliste* aller freigegebenen Objekte mit Ausnahme der Objekte mit automatischer Speicherdauer synchronisiert. (Dies ist wahrscheinlich einen höheren Aufwand als ein **leeren** mit einem *Variablenliste*.) Ein **leeren** Direktive ohne eine *Variablenliste* wird implizit für die folgenden Anweisungen:

- `barrier`

- Am Eingang und das Ende von **kritisch**

- Am Eingang und das Ende von `ordered`

- Am Eingang und das Ende von **parallel**

- Beenden Sie at **für**

- Beenden Sie at **Abschnitte**

- Beenden Sie at **einzelne**

- Am Eingang und das Ende von **für parallele**

- Am Eingang und das Ende von **parallel Sections-**

Die Richtlinie ist nicht impliziert werden, wenn eine `nowait` -Klausel vorhanden ist. Beachten Sie, die die **leeren** Richtlinie ist nicht für eine der folgenden implizit:

- Klicken Sie auf einen Eintrag in **für**

- Eintrag oder Beendigung **master**

- Klicken Sie auf einen Eintrag in **Abschnitte**

- Klicken Sie auf einen Eintrag in **einzelne**

Ein Verweis, der den Wert eines Objekts mit einem Volatile-qualified-Typ greift auf verhält, als wäre es ein **leeren** Richtlinie, die das Objekt am vorherigen Sequenzpunkt angeben. Ein Verweis, der den Wert eines Objekts mit einem Volatile-qualified-Typ ändert, verhält sich, als wäre es ein **leeren** Richtlinie, die dieses Objekt die nachfolgende Folge Zeitpunkt angeben.

Beachten Sie, dass die **leeren** Richtlinie verfügt nicht über eine C-Language-Anweisung als Teil der Syntax, es gibt einige Einschränkungen für die Platzierung innerhalb eines Programms. Finden Sie unter [Anhang C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) für die formale Grammatik. Das folgende Beispiel veranschaulicht diese Einschränkungen.

```
/* ERROR - The flush directive cannot be the immediate
*          substatement of an if statement.
*/
if (x!=0)
   #pragma omp flush (x)
...

/* OK - The flush directive is enclosed in a
*      compound statement
*/
if (x!=0) {
   #pragma omp flush (x)
}
```

Einschränkungen für die **leeren** Richtlinie lauten wie folgt:

- Eine Variable, die im angegebenen ein **leeren** Richtlinie darf keinen Verweistyp handelt.