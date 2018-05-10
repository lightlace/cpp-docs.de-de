---
title: 2.7.2.7 Copyin | Microsoft Docs
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
ms.openlocfilehash: 7ee711bfb24e7a2a1cbada1a7e01a243e204f4a8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="2727-copyin"></a>2.7.2.7 copyin
Die **Copyin** Klausel bietet einen Mechanismus zum Zuweisen des gleichen Werts **Threadprivate** Variablen für jeden Thread im Team, die Ausführung des parallelen Bereichs. Für jede Variable, die im angegebenen eine **Copyin** -Klausel, die den Wert der Variablen in der master-Thread der vom Team kopiert werden, als wäre durch eine Zuweisung der Threads privaten Kopien am Anfang des parallelen Bereichs. Die Syntax der **Copyin** -Klausel ist wie folgt:  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 Die Einschränkungen fest, die **Copyin** Klausel lauten wie folgt:  
  
-   Eine Variable, die im angegebenen der **Copyin** -Klausel muss eine erreichbare, eindeutige Kopierzuweisungsoperator aufweisen.  
  
-   Eine Variable, die im angegebenen der **Copyin** -Klausel muss eine **Threadprivate** Variable.