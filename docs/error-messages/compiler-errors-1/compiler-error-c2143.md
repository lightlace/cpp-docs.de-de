---
title: "Compilerfehler C2143 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2143"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2143"
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# Compilerfehler C2143
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: Es fehlt 'Token1' vor 'Token2'  
  
 Der Compiler hat ein spezifisches Token \(also ein anderes Sprachelement als ein Leerzeichen\) erwartet und stattdessen ein anderes Token gefunden.  
  
 Informationen zu diesem Fehler, wenn sie auftritt, wenn Sie einen im verwenden, finden Sie unter [Knowledge Base\-Artikel 241706](http://support.microsoft.com/kb/241706).  
  
 Anhand der [C\+\+\-Sprachreferenz](../../cpp/cpp-language-reference.md) können Sie feststellen, ob der Code syntaktisch falsch ist.  Da der Compiler diesen Fehler möglicherweise direkt nach dem Treffen auf die Zeile meldet, durch die das Problem verursacht wird, prüfen Sie einige Codezeilen vor der fehlerhaften Zeile.  
  
 C2143 kann in unterschiedlichen Situationen auftreten.  
  
 Er kann, wenn ein Operator, der ein Name \(`::`, `->` und `.`\) angeben kann vom Schlüsselwort `template` gefolgt werden muss, wie in diesem Beispiel erfolgen:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 Standardmäßig übernimmt C\+\+ an, dass `Ty::PutFuncType` keine Vorlage ist; Daher wird folgende `<` als Kleiner\-als\-Zeichen interpretiert.  Sie müssen explizit dem Compiler mitteilen, dass `PutFuncType` eine Vorlage darstellt, sodass sie der spitzen Klammer ordnungsgemäß analysieren kann.  Um diesen Fehler zu beheben, verwenden Sie das Schlüsselwort `template` im abhängigen Namen des Typs, wie hier gezeigt:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 kann auftreten, wenn **\/clr** verwendet wird und eine `using`\-Direktive einen Syntaxfehler haben:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Es kann auch auftreten, wenn Sie versuchen, eine Quellcodedatei zu kompilieren, indem Sie CLR\-Syntax ohne auch mit **\/clr** verwenden:  
  
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
  
 Das erste Zeichen hinter, das eine `if`\-Anweisung folgt, muss eine öffnende runde Klammer sein.  Der Compiler kann keine anderen Zeichen übersetzen:  
  
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
  
 C2143 kann auftreten, wenn einer schließenden geschweiften Klammer, einer Klammer oder ein Semikolon fehlt auf der Zeile, in der der Fehler oder in einer der Zeilen darüber oben erkannt wird:  
  
```caml  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Oder wenn ein ungültiges Tag in einer Klassendeklaration gibt:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Wenn eine Bezeichnung nicht an eine Anweisung angefügt ist.  Zum Positionieren einer solchen Bezeichnung \(beispielsweise am Ende einer zusammengesetzten Anweisung\) muss sie an eine NULL\-Anweisung angefügt werden.  
  
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
  
 Der Fehler kann auftreten, wenn ein nicht qualifizierter Aufruf eines Typs in der C\+\+\-Standardbibliothek wird:  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Oder es gibt ein fehlendes `typename`\-Schlüsselwort:  
  
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
  
 Wenn Sie versuchen, eine explizite Instanziierung definiert wird:  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 In einem C\-Programm müssen Variablen am Anfang der Funktion deklariert werden. Nachdem die Funktion nicht\-Deklaration\-Anweisungen ausgeführt hat, können die Variablen nicht deklariert werden.  
  
```c  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
  
```