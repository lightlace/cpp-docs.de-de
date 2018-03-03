---
title: Compilerfehler C2059 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2059
dev_langs:
- C++
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a87f9c3dbb1405463804b7abd5c94abe04a42845
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2059"></a>Compilerfehler C2059
Syntaxfehler: 'token'  
  
 Das Token verursachte einen Syntaxfehler.  
  
 Im folgenden Beispiel wird eine Fehlermeldung für die Zeile, die deklariert `j`.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 Um die Ursache des Fehlers zu ermitteln, untersuchen Sie nicht nur die Zeile, die in der Fehlermeldung aufgeführt ist, sondern auch die darüber liegenden Zeilen. Wenn Überprüfung der entsprechenden Zeilen keinen Hinweis darauf, zu dem Problem ergibt, kommentieren Sie die Zeile, die in der Fehlermeldung aufgeführt ist und möglicherweise mehrere Zeilen darüber.  
  
 Wenn die Fehlermeldung auf ein Symbol, das auftritt, die unmittelbar folgt eine `typedef` Variable, stellen Sie sicher, dass die Variable im Quellcode definiert ist.  
  
 Wenn ein Symbol auf nichts verweist, ausgewertet wird, wie auftreten können, erhalten Sie möglicherweise C2059 beim **/d** `symbol`  **=**  zum Kompilieren verwendet wird.  
  
```  
// C2059a.cpp  
// compile with: /DTEST=  
#include <stdio.h>  
  
int main() {  
   #ifdef TEST  
      printf_s("\nTEST defined %d", TEST);   // C2059  
   #else  
      printf_s("\nTEST not defined");  
   #endif  
}  
```  
  
 Ein weiterer Fall, in dem C2059 auftreten kann, ist beim Kompilieren einer Anwendung, die eine Struktur in die Standardargumente für eine Funktion angibt. Der Standardwert für ein Argument muss ein Ausdruck sein. Eine Initialisiererliste – z. B. eine, die zum Initialisieren einer Struktur verwendet – stellt keinen Ausdruck.  Um dieses Problem zu beheben, definieren Sie einen Konstruktor, um die erforderliche Initialisierung auszuführen.  
  
 Im folgende Beispiel wird C2059 generiert:  
  
```  
// C2059b.cpp  
// compile with: /c  
struct ag_type {  
   int a;  
   float b;  
   // Uncomment the following line to resolve.  
   // ag_type(int aa, float bb) : a(aa), b(bb) {}   
};  
  
void func(ag_type arg = {5, 7.0});   // C2059  
void func(ag_type arg = ag_type(5, 7.0));   // OK  
```  
  
 Sie können auch C2059 abrufen, wenn Sie eine Member-Vorlagenklasse oder Funktion außerhalb der Klasse definieren. Informationen finden Sie unter [Knowledge Base-Artikel 241949](http://support.microsoft.com/kb/241949).  
  
 C2059 kann bei einer Umwandlung falsch formatiertes auftreten.  
  
 Im folgenden Beispiel wird C2059 generiert:  
  
```  
// C2059c.cpp  
// compile with: /clr  
using namespace System;  
ref class From {};  
ref class To : public From {};  
  
int main() {  
   From^ refbase = gcnew To();  
   To^ refTo = safe_cast<To^>(From^);   // C2059  
   To^ refTo2 = safe_cast<To^>(refbase);   // OK  
}  
```  
  
 C2059 kann auch auftreten, wenn Sie versuchen, einen Namespacenamen zu erstellen, der einen Punkt enthält.  
  
 Im folgenden Beispiel wird C2059 generiert:  
  
```  
// C2059d.cpp  
// compile with: /c  
namespace A.B {}   // C2059  
  
// OK  
namespace A  {  
   namespace B {}  
}  
```  
  
 C2059 kann auftreten, wenn ein Operator, der einen Namen zu qualifizieren, kann (`::`, `->`, und `.`) muss das Schlüsselwort folgen `template`, wie im folgenden Beispiel gezeigt:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::Rebind<X>::Other AX; // error C2059  
};  
  
```  
  
 Standardmäßig C++ setzt voraus, dass `AY::Rebind` keine Vorlage ist; daher die folgenden `<` wird interpretiert, als ein kleiner-als-Zeichen.  Sie müssen den Compiler anweisen, explizit, die `Rebind` ist eine Vorlage aus, sodass die Spitze Klammer ordnungsgemäß analysiert werden kann. Verwenden Sie zum Beheben dieses Fehlers die `template` Schlüsselwort im abhängigen Typ-Namen, wie hier gezeigt:  
  
```cpp  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    typedef typename AY::template Rebind<X>::Other AX; // correct  
};  
  
```