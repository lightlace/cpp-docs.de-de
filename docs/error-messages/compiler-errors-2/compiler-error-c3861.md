---
title: Compilerfehler C3861 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82656822d408be4b2fc085abe8a007469c822a65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3861"></a>Compilerfehler C3861

> "*Bezeichner*': Bezeichner wurde nicht gefunden.  
  
Der Compiler konnte einen Verweis sogar mit der Suche „argument-dependent“ zu einem Bezeichner nicht auflösen.  
  
Um diesen Fehler zu beheben, vergleichen Sie die Verwendung von *Bezeichner* auf die identifziererdeklaration hinsichtlich Groß-/Kleinschreibung und Rechtschreibung. Überprüfen Sie, ob [Bereich Auflösung Operatoren](../../cpp/scope-resolution-operator.md) und Namespace [using-Direktiven](../../cpp/namespaces-cpp.md#using_directives) ordnungsgemäß verwendet werden. Wenn die Bezeichner in einer Headerdatei deklariert ist, stellen Sie sicher, dass der Header einbezogen werden, bevor der Bezeichner referenziert wird. Wenn der Bezeichner extern sichtbar sein sollen, stellen Sie sicher, dass in jeder Quelldatei deklariert wird, die verwendet werden. Überprüfen Sie auch, dass der Bezeichner Deklaration oder Definition nicht ausgeschlossen wird [bedingten Kompilierungsdirektiven](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md). 

Änderungen an veraltete Funktionen aus der C-Laufzeitbibliothek in Visual Studio 2015 zu entfernen, können dazu führen, dass C3861 aus. Um diesen Fehler zu beheben, entfernen Sie Verweise auf diese Funktionen oder Ersetzen Sie sie durch ihre sicheren alternativen, sofern vorhanden. Weitere Informationen finden Sie unter [veraltete Versionen](../../c-runtime-library/obsolete-functions.md).  

Wenn es sich bei Fehler C3861 aus älteren Versionen des Compilers nach Projektmigration angezeigt wird, müssen Sie möglicherweise Probleme im Zusammenhang mit unterstützten Versionen von Windows. Visual C++ unterstützt nicht mehr die Zielversionen Windows 95, Windows 98, Windows ME, Windows NT oder Windows 2000. Wenn eine dieser Versionen von Windows die Makros WINVER oder _WIN32_WINNT zugewiesen sind, müssen Sie die Makros ändern. Weitere Informationen finden Sie unter [Ändern von WINVER und _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).
  
## <a name="example"></a>Beispiel  

Im folgende Beispiel wird C3861 generiert, da der Bezeichner nicht definiert ist.  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();    // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  

Im folgende Beispiel wird C3861 generiert, da ein Bezeichner nur in den Dateibereich seiner Definition sichtbar, ist es sei denn, sie in anderen Quelldateien deklariert ist, die sie verwenden.  
  
```cpp  
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp  
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {  
   std::cout << f() << std::endl;    // C3861
}  
```  
  
```cpp  
// C3861_a2.cpp  
int f() {  // declared and defined here
   return 42;  
}
```  
  
## <a name="example"></a>Beispiel  

Ausnahmeklassen in der C++-Standardbibliothek erfordern die `std` Namespace.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```  
## <a name="example"></a>Beispiel  

Veraltete Versionen wurden aus der CRT-Bibliothek entfernt.  
  
```cpp  
// C3861_c.cpp  
#include <stdio.h>  
int main() {  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C3861  
   // Use gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```
Im folgende Beispiel wird C3767 generiert, da der Compiler die Argumentabhängige Suche für FriendFunc verwenden kann:  
  
```  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3861 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
Um den Fehler zu beheben, die Friend-Funktion im Klassenbereich deklarieren und im Namespacebereich definieren:  
  

Klasse MyClass {}  
   Int-M_private;  
   Friend "void" func();  
};  
  
"void" func() {}  
   MyClass s;  
   s.m_private = 0;  
}  
  
Int main() {}  
   Func();  
}  