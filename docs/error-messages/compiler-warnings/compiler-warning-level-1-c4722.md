---
title: Compilerwarnung (Stufe 1) C4722 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 143a902a4d05ab73df96f3f8ab35f52dab244df4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4722"></a>Compilerwarnung (Stufe 1) C4722
„function“: Der Destruktor gibt nie Werte zurück, möglicherweise ist ein Speicherverlust aufgetreten.  
  
 Die Ablaufsteuerung wird mit einem Destruktor beendet. Der Thread oder das gesamte Programm wird beendet, und zugeordnete Ressourcen können möglicherweise nicht freigegeben werden.  Zudem ist das Verhalten der ausführbaren Datei nicht definiert, wenn ein Destruktor für die Stapelentladung während der Ausnahmeverarbeitung aufgerufen wird.  
  
 Zum Beheben dieses Fehlers entfernen Sie den Funktionsaufruf, der bewirkt, dass der Destruktor nicht zurückgegeben wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4722 generiert.  
  
```  
// C4722.cpp  
// compile with: /O1 /W1 /c  
#include <stdlib.h>  
class C {  
public:  
   C();  
   ~C() { exit(1); };   // C4722  
};  
  
extern void func (C*);  
  
void Test(){  
   C x;  
   func(&x);  
   // control will not leave Test because destructor will exit  
}  
```