---
title: Compiler (Stufe 2) C4412 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 92aa12514088d0fbffbe826a495d76b49ab311d1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4412"></a>Compilerwarnung (Stufe 2) C4412
'Funktion': Funktionssignatur enthält Typ 'Type'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem oder systemeigenem.  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 veraltet ist.  
  
 Der Compiler hat eine potenziell unsichere Situation, die bei einem Laufzeitfehler verursachen: erfolgt ein Aufruf von einer **/CLR: pure** Kompiliereinheit an eine Funktion, die über Dllimport und die Funktionssignatur importiert wurde, enthält einen unsicheren Typ. Ein Typ ist unsicher, wenn es eine Memberfunktion enthält oder einen Datenmember, der einen unsicheren Typ oder eine Dereferenzierung zu einem unsicheren Typ ist.  
  
 Dies ist unsicher aufgrund der Unterschied in der Standard-Aufrufkonventionen zwischen reinem und systemeigenem Code (oder gemischten systemeigenen und verwalteten). Beim Importieren (über `dllimport`) eine Funktion in einer **/CLR: pure** Kompiliereinheit, stellen Sie sicher, dass die Deklarationen der einzelnen Typen in der Signatur mit denjenigen in der Kompiliereinheit identisch, die die Funktion sind (Achten Sie besonders auf die Unterschiede in der impliziten Aufrufkonventionen) exportiert.  
  
 Eine virtuelle Memberfunktion ist besonders anfällig für unerwartete Ergebnisse zurückgibt.  Allerdings sollten auch eine nicht virtuelle Funktion getestet werden, um sicherzustellen, dass Sie die richtigen Ergebnisse erhalten. Wenn Sie sicher sind, dass Sie die richtigen Ergebnisse erhalten, können Sie diese Warnung ignorieren.  
  
 Weitere Informationen zu **/CLR: reine**, finden Sie unter [wie: Migrieren auf/CLR: pure (C++ / CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
 C4412 ist standardmäßig deaktiviert. Finden Sie unter [Compiler Warnungen, die Are Off standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md) und [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md) Weitere Informationen.  
  
 Um diese Warnung zu beheben, entfernen Sie alle Funktionen aus dem Typ.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4412 generiert.  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel ist eine Headerdatei, die zwei Typen deklariert werden. Die `Unsafe` -Typ ist unsicher, da er eine Memberfunktion besitzt.  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel exportiert die Funktionen mit den Typen, die in der Headerdatei definiert.  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## <a name="example"></a>Beispiel  
 Die Standardaufrufkonvention einer **/CLR: pure** Kompilierung unterscheidet sich von einer systemeigenen Kompilierung.  Wenn C4412.h eingeschlossen ist, wird `Test` standardmäßig `__clrcall`. Wenn Sie kompilieren und führen Sie dieses Programm (verwenden Sie keine **/c**), das Programm wird eine Ausnahme ausgelöst.  
  
 Im folgende Beispiel wird C4412 generiert.  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```
