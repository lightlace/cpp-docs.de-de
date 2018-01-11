---
title: 3.1.8 Omp_get_dynamic-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bd4ec73b82848efcdface781738639b05a256958
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic-Funktion
Die **Omp_get_dynamic** Funktion gibt einen Wert ungleich NULL zurück, wenn dynamische Anpassung der Threads aktiviert ist, und andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Wenn die dynamische Anpassung der Anzahl der Threads in die Implementierung nicht implementiert wird, gibt diese Funktion immer 0 zurück.  
  
## <a name="cross-references"></a>Referenzen:  
  
-   Eine Beschreibung der Thread dynamische Anpassung, finden Sie unter [Abschnitt 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) auf Seite 39.