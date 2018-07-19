---
title: return-Anweisung in Programmbeendigung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb594eb10e8068d5f5b3ed124d5e77b48ced728e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943144"
---
# <a name="return-statement-in-program-termination-c"></a>return-Anweisung in Programmbeendigung (C++)
Ausgeben einer `return` -Anweisung vom **main** ist funktionell gleichwertig mit Aufrufen der **beenden** Funktion. Betrachten Sie das folgende Beispiel:  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 Die **beenden** und **zurückgeben** Anweisungen im vorherigen Beispiel funktional identisch sind. Allerdings erfordert C++, dass Funktionen, die andere als Rückgabetypen **"void"** geben einen Wert zurück. Die **zurückgeben** -Anweisung können Sie zum Zurückgeben eines Werts aus `main`.  
  
## <a name="see-also"></a>Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)