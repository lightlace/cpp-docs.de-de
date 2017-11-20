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
ms.openlocfilehash: cd296192146e76085e1b987e29a377eb621917ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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