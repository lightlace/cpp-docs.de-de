---
title: Compilerfehler C2143 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2143
dev_langs:
- C++
helpviewer_keywords:
- C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 31ea645b9dd22fd15bbf4695935482d899a13386
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2143"></a>Compilerfehler C2143
Syntaxfehler: Fehlender "ttoken1" vor "token2"  
  
 Der Compiler hat ein spezifisches Token (d. h. ein Sprachelement als Leerzeichen) erwartet und stattdessen ein anderes Token gefunden.  
  
 Informationen zu diesem Fehler bei der Ausführung bei der Verwendung eines Funktion Try-Blocks, finden Sie unter [Knowledge Base-Artikel 241706](http://support.microsoft.com/kb/241706).  
  
 Überprüfen Sie die [C++-Sprachreferenz](../../cpp/cpp-language-reference.md) um zu bestimmen, wo Code syntaktisch falsch ist. Überprüfen Sie mehrere Codezeilen, die den Fehler vorausgehen, weil der Compiler diesen Fehler zu melden möglicherweise nach der Zeile gefunden wird, die das Problem verursacht.  
  
 C2143 kann in verschiedenen Situationen auftreten.  
  
 Er kann auftreten, wenn ein Operator, der einen Namen zu qualifizieren, kann (`::`, `->`, und `.`) muss das Schlüsselwort folgen `template`, wie in diesem Beispiel:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 Standardmäßig C++ setzt voraus, dass `Ty::PutFuncType` keine Vorlage ist; daher die folgenden `<` wird interpretiert, als ein kleiner-als-Zeichen.  Sie müssen den Compiler anweisen, explizit, die `PutFuncType` ist eine Vorlage aus, sodass die Spitze Klammer ordnungsgemäß analysiert werden kann. Verwenden Sie zum Beheben dieses Fehlers die `template` Schlüsselwort im abhängigen Typ-Namen, wie hier gezeigt:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 kann auftreten, wenn **"/ CLR"** wird verwendet, und ein `using` Anweisung einen Syntaxfehler aufweist:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Er kann auch auftreten, wenn Sie versuchen, eine Quellcodedatei mit CLR-Syntax ohne Kompilieren **"/ CLR"**:  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 Das erste nicht-Leerzeichen, das folgt eine `if` -Anweisung muss eine linke Klammer sein. Der Compiler kann nicht in etwas anderes übersetzen:  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143 tritt auf, wenn eine schließende geschweifte Klammer, eine Klammer oder ein Semikolon in der Zeile nicht vorhanden ist, in dem der Fehler aufgetreten ist, oder auf eine der Zeilen nur über:  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Oder in einer Klassendeklaration ein ungültiges Tag vorhanden ist:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Oder wenn eine Bezeichnung nicht an eine Anweisung angefügt ist. Wenn Sie eine Bezeichnung allein setzen müssen, z. B. am Ende einer verbundanweisung, fügen Sie es an eine null-Anweisung:  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 Der Fehler kann auftreten, wenn ein nicht qualifizierter Aufruf auf einen Typ in der C++-Standardbibliothek ausgeführt wird:  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Oder es ist ein fehlendes `typename` Schlüsselwort:  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 Oder wenn Sie versuchen, eine explizite Instanziierung zu definieren:  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 In einem C-Programm Variablen müssen am Anfang der Funktion deklariert werden, und sie können nicht deklariert werden, nachdem die Funktion nicht-Declaration-Anweisungen ausführt.  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  

