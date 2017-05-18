---
title: Compiler-Warnung (Stufe 1) C4382 generiert | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4382
dev_langs:
- C++
helpviewer_keywords:
- C4382
ms.assetid: 34be9ad3-bae6-411a-8f80-0c8fd0d2c092
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 4571fe618b0ae89251d2748fbbcdfcb654201054
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4382"></a>Compilerwarnung (Stufe 1) C4382
Auslösen von 'Typ': ein Typ mit __clrcall-Destruktor oder Copy-Konstruktor kann nur abgefangen werden, in/CLR: pure-Modul  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 veraltet ist.  
  
 Bei der Kompilierung mit **/CLR** (nicht **/CLR: pure**), Ausnahmebehandlung erwartet die Memberfunktionen in einem systemeigenen Typ zu [__cdecl](../../cpp/cdecl.md) und nicht [__clrcall](../../cpp/clrcall.md). Systemeigene Typen mit Memberfunktionen verwenden `__clrcall` Aufrufkonvention kann nicht aufgefangen werden, in einem Modul kompiliert mit **/CLR**.  
  
 Wenn in einem Modul kompiliert werden, mit der Ausnahme abgefangen wird **/CLR: pure**, können Sie diese Warnung ignorieren.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4382 generiert.  
  
```  
// C4382.cpp  
// compile with: /clr /W1 /c  
struct S {  
   __clrcall ~S() {}  
};  
  
struct T {  
   ~T() {}  
};  
  
int main() {  
   S s;  
   throw s;   // C4382  
  
   S * ps = &s;  
   throw ps;   // OK  
  
   T t;  
   throw t;   // OK  
}  
```
