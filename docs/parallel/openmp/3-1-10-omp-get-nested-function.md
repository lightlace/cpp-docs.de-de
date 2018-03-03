---
title: 3.1.10 Omp_get_nested-Funktion | Microsoft Docs
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
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36b213ee45018e7cc0ccf3a1cb99dcbd640d4457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested-Funktion
Die `omp_get_nested` Funktion gibt einen Wert ungleich NULL, wenn die geschachtelten Parallelität aktiviert ist, und 0 zurück, wenn er deaktiviert ist. Weitere Informationen zu geschachtelten Parallelität finden Sie in Abschnitt 3.1.9 auf Seite "40". Es wird folgendes Format verwendet:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Wenn eine Implementierung keine geschachtelten Parallelität implementiert, gibt diese Funktion immer 0 zurück.