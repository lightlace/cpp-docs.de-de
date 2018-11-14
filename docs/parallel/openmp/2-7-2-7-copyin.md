---
title: 2.7.2.7 copyin
ms.date: 11/04/2016
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
ms.openlocfilehash: 20db32530ee60967245497cdfb12a0fce103f7b7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519528"
---
# <a name="2727-copyin"></a>2.7.2.7 copyin

Die **Copyin** -Klausel bietet einen Mechanismus, um den gleichen Wert zuweisen **Threadprivate** Variablen für jeden Thread im Team, das Ausführen des parallelen Bereichs. Für jede Variable, die im angegebenen ein **Copyin** -Klausel, die den Wert der Variablen in der master-Thread des Teams kopiert wurde, als ob durch eine Zuweisung der privaten Kopien am Anfang des parallelen Bereichs. Die Syntax der **Copyin** -Klausel ist wie folgt:

```

copyin(
variable-list
)
```

Die Einschränkungen fest, die **Copyin** Klausel lauten wie folgt:

- Eine Variable, die im angegebenen die **Copyin** -Klausel muss eine erreichbare, eindeutige Kopierzuweisungsoperator aufweisen.

- Eine Variable, die im angegebenen die **Copyin** Klausel muss ein **Threadprivate** Variable.