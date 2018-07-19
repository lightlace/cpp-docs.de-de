---
title: A. 6 Lastprivate-Klausel mit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eec6ddc46aab36671e767963e5aaf6e25c4d25cd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690542"
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