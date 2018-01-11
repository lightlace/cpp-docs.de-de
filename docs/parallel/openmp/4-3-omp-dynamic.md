---
title: 4.3 OMP_DYNAMIC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 103067b28990854fb6522c19f4349a9607d65bab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
Die **OMP_DYNAMIC** Umgebungsvariable aktiviert oder deaktiviert die dynamische Anpassung der Anzahl der Threads, die für die Ausführung von parallelen Regionen verfügbar, wenn die dynamische Anpassung explizit aktiviert oder deaktiviert durch Aufrufen der **Omp_set_dynamic** Bibliotheksroutine. Muss sein Wert **"true"** oder **"false"**.  
  
 Wenn auf festgelegt **"true"**, die Anzahl der Threads, die zum Ausführen von paralleler Regions verwendet werden kann angepasst werden, von der Common Language Runtime-Umgebung auf die Systemressourcen optimal zu nutzen.  Wenn auf festgelegt **"false"**, dynamische Anpassung ist deaktiviert. Die standardbedingung lautet Implementierung definiert.  
  
 Beispiel:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>Referenzen:  
  
-   Weitere Informationen zu parallelen Regionen, finden Sie unter [Abschnitt 2.3](../../parallel/openmp/2-3-parallel-construct.md) auf Seite "8".  
  
-   **Omp_set_dynamic** funktionieren, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.