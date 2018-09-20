---
title: 2.6.2 critical-Konstrukt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e51bd425999081c7a06a7d5692dbea16c887fa0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417851"
---
# <a name="262-critical-construct"></a>2.6.2 critical-Konstrukt

Die **kritische** -Direktive identifiziert ein Konstrukt, die Ausführung von einem zugeordneten strukturierten Block auf einen einzelnen Thread zu einem Zeitpunkt beschränkt. Die Syntax der **kritische** Richtlinie lautet wie folgt:

```
#pragma omp critical [(name)]  new-linestructured-block
```

Eine optionale *Namen* kann zum Identifizieren des kritischen Bereichs verwendet werden. Bezeichner, die zum Identifizieren von eines kritischen Bereichs verfügen über eine externe Bindung, und in einem Namespace ist unabhängig von den Namespaces, die von Bezeichnungen, Tags, Mitglieder und wie gewöhnliche Bezeichner verwendet werden.

Ein Thread wartet am Anfang des einem kritischen Bereich, bis kein anderer Thread einen kritischen Bereich (eine beliebige Stelle im Programm), mit dem gleichen Namen ausgeführt wird. Alle unbenannten **kritische** Anweisungen in den nicht angegebenen Namen zugeordnet.