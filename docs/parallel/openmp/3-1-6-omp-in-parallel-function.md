---
title: 3.1.6 Omp_in_parallel-Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2e5d05af81eb112894ca27a7599c271138893ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel-Funktion
Die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, wenn sie in der dynamischen Wertebereich einen parallel ausgeführten parallelen Bereichs aufgerufen wird; andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Diese Funktion gibt einen Wert ungleich NULL beim Aufrufen durch innerhalb einer Region parallelen ausführen, einschließlich geschachtelter Bereiche, die serialisiert werden.