---
title: Compilerwarnung (Stufe 2) C4412 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4412
dev_langs: C++
helpviewer_keywords: C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92898b9c8e8845ecc8bc650b80cf41a33b3a59d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4412"></a>Compilerwarnung (Stufe 2) C4412
'Funktion': Funktionssignatur enthält Typ 'Typ'; C++-Objekte sind nicht sicher zwischen reinem Code übergeben und gemischtem oder systemeigenem.  
  
 Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert ist.  
  
 Der Compiler hat eine potenziell unsichere Situation, die zu einem Laufzeitfehler führen konnte: erfolgt ein Aufruf von einer **/CLR: pure** Kompiliereinheit an eine Funktion, die über Dllimport und Funktionssignatur importiert wurde, enthält einen unsicheren Typ . Ein Typ ist unsicher, wenn er eine Memberfunktion enthält oder einen Datenmember, der einem unsicheren Typ oder eine Dereferenzierung zu einem unsicheren Typ ist.  
  
 Dies ist unsicher aufgrund der Unterschied in der Standard-Aufrufkonventionen zwischen reinem und systemeigenem Code (oder gemischten systemeigenen und verwalteten). Beim Importieren von (über `dllimport`) eine Funktion in einer **/CLR: pure** Kompiliereinheit, stellen Sie sicher, dass die Deklarationen der jeden Typ in der Signatur mit denjenigen in der Kompiliereinheit identisch, die die Funktion sind (Achten Sie besonders exportiert Unterschiede bei impliziten Aufrufkonventionen).  
  
 Eine virtuelle Memberfunktion ist besonders anfällig für unerwartete Ergebnisse zurückgibt.  Allerdings sollten auch eine nicht virtuelle Funktion, die getestet werden, um sicherzustellen, dass die richtigen Ergebnisse zu erhalten. Wenn Sie sicher sind, dass Sie die richtigen Ergebnisse ausgegeben werden, können Sie diese Warnung ignorieren.  
  
 Weitere Informationen zu **/CLR: pure**, finden Sie unter [wie: Migrieren auf/CLR: pure (C + c++ / CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
 C4412 ist standardmäßig deaktiviert. Finden Sie unter [Compiler deaktivierte Compilerwarnungen standardmäßig](../../preprocessor/compiler-warnings-that-are-off-by-default.md) und [Dllexport, Dllimport](../../cpp/dllexport-dllimport.md) für Weitere Informationen.  
  
 Um diese Warnung zu beheben, entfernen Sie alle Funktionen aus dem Typ.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4412 generiert.  
  
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
 Im folgende Beispiel wird eine Headerdatei, die zwei Typen deklariert. Die `Unsafe` Typ ist unsicher, da sie eine Memberfunktion verfügt.  
  
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
 In diesem Beispiel werden Funktionen mit den in der Headerdatei definierten Typen exportiert.  
  
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
 Die Standardaufrufkonvention einer **/CLR: pure** Kompilierung unterscheidet sich von der systeminterne Kompilierung.  Wenn C4412.h eingeschlossen ist, wird `Test` standardmäßig `__clrcall`. Wenn Sie kompilieren und dieses Programms ausführen (verwenden Sie keine **/c**), das Programm wird eine Ausnahme ausgelöst.  
  
 Im folgenden Beispiel wird C4412 generiert.  
  
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