---
title: 2.7.2.3 Lastprivate | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25edca8391eb094691ef4fea3c360d351f979b43
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385962"
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

Die `lastprivate` -Klausel bietet eine Obermenge von der Funktionalität der `private` Klausel. Die Syntax der `lastprivate` -Klausel ist wie folgt:

```
lastprivate(variable-list)
```

Variablen in der *Variablenliste* haben `private` Klausel-Semantik. Wenn eine `lastprivate` -Klausel wird angezeigt, auf die Richtlinie, die eine gemeinsame Verwendung von Arbeit Konstrukt, den Wert für jeden identifiziert `lastprivate` Variable von der sequenziell letzte Iteration der Schleife zugeordnet ist, oder die lexikalisch letzten abschnittsdirektive, zugewiesen wird die Ursprüngliches Objekt der Variablen. Variablen, die nicht der letzte Durchlauf der ein Wert zugewiesen der **für** oder **für parallele**, oder durch den lexikalisch letzten Abschnitt des der **Abschnitte** oder  **Parallel Sections-** -Direktive haben unbestimmte Werte nach der Erstellung. Nicht zugewiesene Unterobjekte haben auch einen unbestimmten Wert nach der Erstellung.

Die Einschränkungen fest, die `lastprivate` Klausel lauten wie folgt:

- Alle Einschränkungen für `private` anwenden.

- Eine Variable mit einem Klassentyp, der als angegeben wird `lastprivate` muss eine erreichbare, eindeutige Kopierzuweisungsoperator verfügen.

- Variablen, die innerhalb eines parallelen Bereichs privat sind, bzw. die angezeigt werden, in, der `reduction` -Klausel einer **parallele** Richtlinie kann nicht angegeben werden, eine `lastprivate` -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden wird.