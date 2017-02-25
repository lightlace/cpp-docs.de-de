---
title: "Compilerfehler C2059 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2059"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2059"
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Compilerfehler C2059
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Syntaxfehler: 'Token'  
  
 Das Token hat einen Syntaxfehler verursacht.  
  
 Im folgenden Beispiel wird eine Fehlermeldung für die Zeile generiert, die `j` deklariert.  
  
```  
// C2059e.cpp  
// compile with: /c  
// C2143 expected  
// Error caused by the incorrect use of '*'.  
   int j*; // C2059   
```  
  
 Um die Fehlerursache zu bestimmen, überprüfen Sie nicht nur die Zeile die in der Fehlermeldung aufgeführte, sondern auch die darüberliegenden Zeilen.  Wenn, die Überprüfung, Zeilen keinen Hinweis zum Problem führt, versuchen Sie, das Auskommentieren der die Zeile, die in der Fehlermeldung und möglicherweise in verschiedenen Zeilen darüber aufgeführt ist.  
  
 Wenn die Fehlermeldung in einem Symbol auftritt, das unmittelbar auf eine `typedef`\-Variable folgt, stellen Sie sicher, dass die Variable im Quellcode definiert ist.  
  
 Sie rufen u C2059, Wenn eine Symbolauswertung keinen Wert ergibt, wie bei der **\/D**`symbol`, wenn **\=** verwendet wird, um zu kompilieren.  
  
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
  
 Ein weiterer Fall, in dem C2059 auftreten kann, ist, wenn Sie eine Anwendung kompilieren, die eine Struktur in den Standardargumenten für eine Funktion angegeben wird.  Der Standardwert für ein Argument muss ein Ausdruck sein.  Ein Beispiel Liste\-für Initialisierer, eines, das verwendet, um eine zu initialisieren, Struktur\-ist kein Ausdruck.  Um dieses Problem zu beheben, definieren Sie einen Konstruktor um die erforderliche Initialisierung durchführt.  
  
 Im folgenden Beispiel wird C2059 generiert:  
  
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
  
 Die Fehlermeldung C2059 kann auch ausgegeben werden, wenn Sie eine Membervorlagenklasse oder \-funktion außerhalb der Klasse definieren.  Weitere Informationen finden Sie unter [Knowledge Base\-Artikel 241949](http://support.microsoft.com/kb/241949).  
  
 C2059 kann bei einer falsch formatierten Typumwandlung auftreten.  
  
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
  
 C2059 kann auch bei dem Versuch auftreten, einen Namespacenamen zu erzeugen, der einen Punkt enthält.  
  
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
  
 C2059 kann, wenn ein Operator, der ein Name \(`::`, `->` und `.`\) angeben kann vom Schlüsselwort `template` gefolgt werden muss, wie in diesem Beispiel gezeigt auftreten:  
  
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
  
 Standardmäßig übernimmt C\+\+ an, dass `AY::Rebind` keine Vorlage ist; Daher wird folgende `<` als Kleiner\-als\-Zeichen interpretiert.  Sie müssen explizit dem Compiler mitteilen, dass `Rebind` eine Vorlage darstellt, sodass sie der spitzen Klammer ordnungsgemäß analysieren kann.  Um diesen Fehler zu beheben, verwenden Sie das Schlüsselwort `template` im abhängigen Namen des Typs, wie hier gezeigt:  
  
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