---
title: Ausdrucksanweisung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- statements [C++], expression
- expression statements
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60879ca8792e3259a69b7a9a3de6cd83dce0d6d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411580"
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