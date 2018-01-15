---
title: 2.7.2.7 Copyin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5ba09b70b3a3591b1f8b427ac107576cfcac7935
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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