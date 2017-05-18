---
title: Compilerwarnung (Stufe 1) C4722 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4722
dev_langs:
- C++
helpviewer_keywords:
- C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
caps.latest.revision: 6
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
ms.openlocfilehash: a88d734f0f17437efe3b4a60a3439135b7feec4e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

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
