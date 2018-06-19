---
title: Ausdrucksauswertungsfehler CXX0064 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0064
dev_langs:
- C++
helpviewer_keywords:
- CAN0064
- CXX0064
ms.assetid: aa509e71-0616-41ca-a94e-6c376b041e57
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7964eac628fa89695d1757cff8b7b329fd7fe713
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302135"
---
# <a name="expression-evaluator-error-cxx0064"></a>Ausdrucksauswertungsfehler CXX0064
Haltepunkt kann nicht auf gebundene virtuelle Memberfunktion festgelegt werden.  
  
 Ein Haltepunkt wurde auf eine virtuelle Memberfunktion, die über einen Zeiger auf ein Objekt, z. B. festgelegt:  
  
```  
pClass->vfunc( int );  
```  
  
 Ein Haltepunkt kann auf eine virtuelle Funktion durch die Klasse, wie z. B. Eingabe festgelegt werden:  
  
```  
Class::vfunc( int );  
```  
  
 Dieser Fehler ist mit CAN0064 identisch.