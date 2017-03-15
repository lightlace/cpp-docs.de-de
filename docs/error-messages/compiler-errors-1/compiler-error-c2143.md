---
title: Compiler-Fehler C2143 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: faa9361da0091ec86628af19a03eadb133ea43cc
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2143"></a>Compilerfehler C2143
Syntaxfehler: Fehlendes 'token1' vor 'token2'  
  
 Der Compiler hat ein spezifisches Token (d. h. ein Sprachelement als ein Leerzeichen) erwartet und stattdessen ein anderes Token gefunden.  
  
 Informationen zu diesem Fehler, wenn es tritt auf, wenn Sie einen Function-Try-Block verwenden, finden Sie unter [Knowledge Base-Artikel 241706](http://support.microsoft.com/kb/241706).  
  
 Überprüfen Sie die [C++-Sprachreferenz](../../cpp/cpp-language-reference.md) bestimmt der Code syntaktisch falsch ist. Da der Compiler diesen Fehler zu melden kann, nachdem sie die Zeile stößt, die das Problem verursacht, überprüfen Sie einige Codezeilen vor der fehlerhaften.  
  
 C2143 kann in verschiedenen Situationen auftreten.  
  
 Er kann auftreten, wenn ein Operator, der einen Namen zu qualifizieren, kann (`::`, `->`, und `.`) muss das Schlüsselwort folgen `template`, wie im folgenden Beispiel:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 Standardmäßig C++ setzt voraus, dass `Ty::PutFuncType` keine Vorlage; daher die folgenden `<` wird als ein interpretiert-als-Zeichen.  Sie müssen den Compiler anweisen explizit, die `PutFuncType` ist eine Vorlage, damit es ordnungsgemäß auf die Spitze Klammer analysieren kann. Um diesen Fehler zu korrigieren, verwenden die `template` Schlüsselwort im abhängigen Typ-Namen, wie hier gezeigt:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 kann auftreten, wenn **/CLR** wird verwendet, und ein `using` Richtlinie einen Syntaxfehler aufweist:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Es kann auch auftreten, wenn Sie versuchen, eine Quellcodedatei mit CLR-Syntax ohne Kompilieren **/CLR**:  
  
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
  
 Das erste folgende Zeichen kein Leerzeichen ein `if` -Anweisung muss eine öffnende runde Klammer sein. Der Compiler kann nicht alles andere übersetzen:  
  
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
  
 C2143 kann auftreten, wenn eine schließende geschweifte Klammer, eine Klammer oder ein Semikolon in der Zeile nicht vorhanden ist, in dem der Fehler aufgetreten ist, oder auf eine der Zeilen direkt über:  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Oder wenn ein ungültiges Tag in einer Klassendeklaration:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Oder wenn eine Bezeichnung nicht an eine Anweisung angefügt ist. Wenn Sie eine Bezeichnung allein platzieren müssen, z. B. am Ende einer zusammengesetzten Anweisung fügen Sie es an eine null-Anweisung:  
  
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
  
 Der Fehler kann auftreten, wenn ein nicht qualifizierter Aufruf an einen Typ in der C++-Standardbibliothek hergestellt wird:  
  
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
  
 In einem C-Programm müssen Variablen am Anfang der Funktion deklariert werden, und sie können nicht deklariert werden, nachdem die Funktion nicht-Declaration-Anweisungen ausführt.  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  

