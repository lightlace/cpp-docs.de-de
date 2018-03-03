---
title: Compilerfehler Warnung (Stufe 1) C4744 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b6fa95f8477f889aa8664d2b6d99c753cb9848d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4744"></a>Compilerwarnung (Stufe 1) C4744
"Var" hat einen anderen Typ in "Datei1" und "Datei2": "Typ1" und "Typ2"  
  
 Eine externe Variable verwiesen wird, oder in zwei Dateien definiert verfügt über verschiedene Arten in diesen Dateien.  Um zu beheben, verwenden Sie entweder den Typdefinitionen identisch bzw. Variablenname Änderung in einer der Dateien.  
  
 C4744 wird nur ausgegeben, wenn Dateien mit/GL kompiliert werden  Weitere Informationen finden Sie unter [/GL (Optimierung des ganzen Programms)](../../build/reference/gl-whole-program-optimization.md).  
  
> [!NOTE]
>  C4744 tritt normalerweise in C# (nicht C++)-Dateien, da c++ ein Variablenname Typinformationen ergänzt wird.  Wenn das Beispiel (siehe unten) als C++ kompiliert wird, erhalten Sie Linkerfehler LNK2019.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel enthält die erste Definition.  
  
```  
// C4744.c  
// compile with: /c /GL  
int global;  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4744 generiert.  
  
```  
// C4744b.c  
// compile with: C4744.c /GL /W1  
// C4744 expected  
#include <stdio.h>  
  
extern unsigned global;  
  
main()   
{  
    printf_s("%d\n", global);  
}  
```