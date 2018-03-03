---
title: A. 6 Lastprivate-Klausel mit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1744787e1dfb90fa9af93db5dba4eecd600b4334
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   Verwenden der lastprivate-Klausel
Korrekte Ausführung in einigen Fällen hängt vom Wert, den die letzte Iteration einer Schleife einer Variablen zuweist. Diese Programme müssen alle solcher Variablen als Argumente für Auflisten einer `lastprivate` -Klausel ([Abschnitt 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) Seite 27) so, dass die Werte der Variablen bei Ausführung der Schleife sequenziell ist identisch.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 Im vorherigen Beispiel den Wert der `i` am Ende des parallelen Bereichs ist gleich `n-1`, wie in der sequenziellen Groß-/Kleinschreibung.