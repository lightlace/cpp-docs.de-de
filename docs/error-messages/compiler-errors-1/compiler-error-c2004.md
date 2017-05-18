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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 81b2693ba3a1132738b5a1ff0e830fc4cef36e13
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

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
