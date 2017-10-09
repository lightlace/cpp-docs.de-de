---
title: Compilerfehler C2004 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2004
dev_langs:
- C++
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f4596e43fad713f6b0a81eea9e697c6e0f91c75b
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2004"></a>Compilerfehler C2004
"defined(id)" erwartet  
  
 Ein Bezeichner muss in den Klammern hinter dem Präprozessorschlüsselwort angegeben werden.  
  
 Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual Visual Studio .NET 2003 auftreten: fehlende Klammer in Präprozessordirektive. Wenn die schließende Klammer in einer Präprozessordirektive fehlt, generiert der Compiler einen Fehler.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2004 generiert.  
  
```  
// C2004.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG   // C2004  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```  
  
## <a name="example"></a>Beispiel  
 Mögliche Lösung:  
  
```  
// C2004b.cpp  
// compile with: /DDEBUG  
#include <stdio.h>  
  
int main()   
{  
    #if defined(DEBUG)  
        printf_s("DEBUG defined\n");  
    #endif  
}  
```
