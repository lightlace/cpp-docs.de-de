---
title: Ausdrucksanweisung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e627e107df850f31a9cf04981795edd1185c0ce5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="expression-statement"></a>Ausdrucksanweisung
Ausdrucksanweisungen bewirken die Auswertung von Ausdrücken. Keine Übertragung der Steuerung oder Iteration tritt infolge einer Ausdrucksanweisung auf.  
  
 Die Syntax für die Ausdrucksanweisung ist einfach  
  
## <a name="syntax"></a>Syntax  
  
```  
[expression ] ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Alle Ausdrücke in einer Ausdrucksanweisung werden ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor die nächste Anweisung ausgeführt wird. Die häufigsten Ausdrucksanweisungen sind Zuweisungen und Funktionsaufrufe.  Da der Ausdruck optional ist, wird ein Semikolon allein als eine leere Ausdrucksanweisung genannt betrachtet die [null](../cpp/null-statement.md) Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)