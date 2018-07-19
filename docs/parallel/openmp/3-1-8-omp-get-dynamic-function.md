---
title: 3.1.8 Omp_get_dynamic-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af7755173ab884a40a5f8a41f432f265cc1e6c32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686190"
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