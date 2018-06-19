---
title: 3.1.6 Omp_in_parallel-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22b491695d2ae49336d7d8998af64e724f344d87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686281"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel-Funktion
Die **Omp_in_parallel** Funktion gibt einen Wert ungleich NULL zurück, wenn sie in der dynamischen Wertebereich einen parallel ausgeführten parallelen Bereichs aufgerufen wird; andernfalls wird 0 zurückgegeben. Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Diese Funktion gibt einen Wert ungleich NULL beim Aufrufen durch innerhalb einer Region parallelen ausführen, einschließlich geschachtelter Bereiche, die serialisiert werden.