---
title: Compilerwarnung (Stufe 1) C4091 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4091
dev_langs:
- C++
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79a0a74ad2cf6471679fd776f296d465ee8dd29c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4091"></a>Compilerwarnung (Stufe 1) C4091
'Schlüsselwort': auf der linken Seite von "Type" ignoriert werden, wenn keine Variable deklariert wurde  
  
 Der Compiler hat eine Situation, in denen der Benutzer wahrscheinlich gedacht, eine Variable deklariert werden, aber der Compiler konnte sich nicht um die Variable zu deklarieren.  
  
## <a name="example"></a>Beispiel  
 Ein `__declspec` Attribut am Anfang einer benutzerdefinierten Typdeklaration gilt für die Variable dieses Typs. C4091 weist darauf hin, dass keine Variable deklariert wird. Im folgende Beispiel wird C4091 generiert.  
  
```  
// C4091.cpp  
// compile with: /W1 /c  
__declspec(dllimport) class X {}; // C4091  
  
// __declspec attribute applies to varX  
__declspec(dllimport) class X2 {} varX;  
  
// __declspec attribute after the class or struct keyword   
// applies to user defined type  
class __declspec(dllimport) X3 {};  
```  
  
## <a name="example"></a>Beispiel  
 Wenn ein Bezeichner eine Typdefinition ist, kann nicht es auch ein Variablenname sein. Im folgende Beispiel wird C4091 generiert.  
  
```  
// C4091_b.cpp  
// compile with: /c /W1 /WX  
#define LIST 4  
typedef struct _LIST {} LIST;   // C4091  
```