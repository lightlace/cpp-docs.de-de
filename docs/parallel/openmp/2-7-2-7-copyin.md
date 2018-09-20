---
title: 2.7.2.7 Copyin | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94b4c529b7ad6fd717be1e1dee0edd3ff9ac3ff5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426886"
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