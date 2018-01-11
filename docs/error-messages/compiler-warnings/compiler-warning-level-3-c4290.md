---
title: Compilerwarnung (Stufe 3) C4290 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4290
dev_langs: C++
helpviewer_keywords: C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f70a278cb3e660e89e1aba067cab9c20aacf8f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4290"></a>Compilerwarnung (Stufe 3) C4290
C++-Ausnahmespezifikation ignoriert zum Angeben einer funktionsrückgabewerts ist nicht __declspec (nothrow)  
  
 Eine Funktion ist deklariert mit Ausnahmespezifikation, die Visual C++ akzeptiert, aber nicht implementiert. Code mit der Ausnahme benötigten Spezifikationen, die während der Kompilierung ignoriert werden, neu kompiliert werden und verknüpft werden wiederverwendet in zukünftigen Versionen Ausnahmespezifikationen unterstützen.  
  
 Weitere Informationen finden Sie unter [Ausnahmespezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md) .  
  
 Sie können diese Warnung vermeiden, indem die [Warnung](../../preprocessor/warning.md) Pragma:  
  
```  
#pragma warning( disable : 4290 )  
```  
  
 Im folgenden Codebeispiel wird die C4290 generiert:  
  
```  
// C4290.cpp  
// compile with: /EHs /W3 /c  
void f1(void) throw(int) {}   // C4290  
  
// OK  
void f2(void) throw() {}  
void f3(void) throw(...) {}  
```