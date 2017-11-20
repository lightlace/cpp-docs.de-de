---
title: 3.1.9 Omp_set_nested-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a70406e42904c40ac81901ffd174991c0ebc54d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested-Funktion
Die **Omp_set_nested** Funktion aktiviert oder deaktiviert die geschachtelten Parallelität. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 Wenn *geschachtelte* ergibt 0 (null) und geschachtelte Parallelität deaktiviert ist, dies ist die Standardeinstellung und geschachtelten parallele Regionen serialisiert und vom aktuellen Thread ausgeführt werden. Wenn *geschachtelte* ergibt einen Wert ungleich NULL geschachtelten Parallelität aktiviert ist, und parallele Bereiche, die geschachtelt sind möglicherweise zusätzliche Threads zum Bilden von geschachtelten Teams bereitstellen.  
  
 Diese Funktion wirkt sich die oben beschriebenen, beim Aufrufen durch einen Teil des Programms, in dem die **Omp_in_parallel** Funktion gibt 0 (null) zurück. Wenn sie von einem Teil des Programms aufgerufen wird, in dem die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, das Verhalten dieser Funktion ist nicht definiert.  
  
 Dieser Aufruf hat Vorrang gegenüber der **OMP_NESTED** -Umgebungsvariablen angegeben.  
  
 Wenn geschachtelte Parallelität aktiviert ist, wird die Anzahl der Threads, die zum Ausführen von geschachtelten paralleler Regions Implementierung definiert. Daher dürfen OpenMP-kompatible Implementierung geschachtelten parallele Regionen zu serialisieren, auch wenn geschachtelte Parallelität aktiviert ist.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   **OMP_NESTED** Umgebung-Variable verwenden, finden Sie unter [Abschnitt 4.4](../../parallel/openmp/4-4-omp-nested.md) auf Seite "49".  
  
-   **Omp_in_parallel** funktionieren, finden Sie unter [Abschnitt 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) auf Seite 38.