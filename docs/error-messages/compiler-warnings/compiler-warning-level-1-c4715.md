---
title: Compilerwarnung (Stufe 1) C4715 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4715
dev_langs:
- C++
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57bd7f86a06c060a469d31e5fbdfcfbd7afb8c80
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4715"></a>Compilerwarnung (Stufe 1) C4715
'Funktion': nicht alle Steuerelementpfade geben einen Wert zurück.  
  
 Die angegebene Funktion kann möglicherweise keinen Wert zurück.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 Um diese Warnung zu vermeiden, ändern Sie den Code, damit alle Pfade einen Rückgabewert der Funktion zugewiesen werden:  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 Es ist möglich, dass Ihr Code einen Aufruf einer Funktion, die nie zurückgegeben enthalten kann, wie im folgenden Beispiel gezeigt:  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 Dieser Code wird auch eine Warnung generiert, da der Compiler nicht, dass weiß `fatal` nie zurückgegeben. Um zu verhindern, dass dieser Code generiert eine Fehlermeldung, deklarieren `fatal` mit [__declspec(noreturn)](../../cpp/noreturn.md).