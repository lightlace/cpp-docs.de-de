---
title: Compilerwarnung (Stufe 1) C4005 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4005
dev_langs:
- C++
helpviewer_keywords:
- C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a06ea88dab6ac7e89f7d53351b54593fd7bd232
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4005"></a>Compilerwarnung (Stufe 1) C4005 generiert
'Bezeichner': Neudefinition von Makros  
  
 Die Makro-Bezeichner wird zweimal definiert. Der Compiler verwendet die zweite Makrodefinition.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Definieren ein Makro in der Befehlszeile und im Code mit einem `#define` Richtlinie.  
  
2.  Makros, die von Include-Dateien importiert werden.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Entfernen Sie eine der Definitionen.  
  
2.  Verwenden einer [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) Richtlinie vor der zweiten Definition.  
  
 Im folgende Beispiel wird C4005 generiert:  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```