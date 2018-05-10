---
title: 2.7.2.2 Firstprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b8e44ca52ba1f76d5b3791a1d08301bf06e7eab
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate
Die **Firstprivate** -Klausel bietet eine Obermenge der gebotenen Funktionen der **private** Klausel. Die Syntax der **Firstprivate** -Klausel ist wie folgt:  
  
```  
firstprivate(variable-list)  
```  
  
 Variablen, die im angegebenen *Variablenliste* haben **private** Klausel Semantik, wie in beschrieben [Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf der Seite "25". Die Initialisierung oder -Konstruktion geschieht, als ob er einmal pro Thread, vor der Ausführung des Threads, der das Konstrukt ausgeführt wurden. Für eine **Firstprivate** -Klausel einer parallel-Konstrukt, der anfängliche Wert des neuen privaten Objekts ist der Wert des ursprünglichen Objekts, das direkt vor dem das parallele Konstrukt für den Thread vorhanden ist, die er erkennt. Für eine **Firstprivate** -Klausel für ein Freigeben von Arbeit-Konstrukt, der anfängliche Wert des neuen Objekts privaten für jeden Thread, der das Freigeben von Arbeit Konstrukt ausgeführt wird. ist der Wert des ursprünglichen Objekts, das vor dem Punkt vorhanden ist, im selben Thread auftritt, das Freigeben von Arbeit-Konstrukt. Darüber hinaus wird das neue private Objekt für jeden Thread für C++-Objekte kopieren aus dem ursprünglichen Objekt erstellt.  
  
 Die Einschränkungen fest, die **Firstprivate** Klausel lauten wie folgt:  
  
-   Eine Variable, die im angegebenen eine **Firstprivate** -Klausel muss nicht zulässig, einen unvollständigen Typ oder einen Referenztyp darstellt.  
  
-   Eine Variable mit einem Klassentyp sein, die als angegeben wird **Firstprivate** benötigen eine erreichbare, eindeutige Kopierkonstruktor.  
  
-   Variablen, die innerhalb eines parallelen Bereichs privaten sind bzw. die angezeigt werden, in, der **Verringerung** -Klausel der eine **parallel** Richtlinie kann nicht angegeben werden, eine **Firstprivate** -Klausel für eine arbeitsteilungsanweisung, die an das parallele Konstrukt gebunden.