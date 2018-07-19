---
title: Compilerwarnung (Stufe 3) C4290 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f03d35e1a3756979d8936647255e2b65afef56d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289892"
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