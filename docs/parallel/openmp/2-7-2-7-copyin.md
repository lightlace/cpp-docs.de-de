---
title: 2.7.2.7 copyin
ms.date: 11/04/2016
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
ms.openlocfilehash: 65bb8faba085e5582e779fa0e9d5bf1a91a39f0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545443"
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