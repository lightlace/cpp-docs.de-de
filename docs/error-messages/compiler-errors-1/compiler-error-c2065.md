---
title: Compiler Error C2065 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 81686df4727ab2b3d5af749174a42016e8443e70
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2065"></a>Compiler Error C2065
„Bezeichner“: nicht deklarierter Bezeichner.  
  
 Ein Variablentyp muss vor seiner Verwendung in einer Deklaration angegeben werden. Die von einer Funktion verwendeten Parameter müssen in einer Deklaration oder einem Prototyp angegeben werden, bevor die Funktion verwendet werden kann.  
  
 Mögliche Ursachen:  
  
1.  Der Bezeichnername ist falsch geschrieben.  
  
2.  Im Bezeichnernamen wird eine falsche Groß-/Kleinschreibung verwendet.  
  
3.  Hinter einer Zeichenfolgenkonstante fehlt ein schließendes Anführungszeichen.  
  
4.  Kompilieren von mit einer Debugversion der C-Laufzeit in eine C++-Standardbibliothek Iteratorvariable Deklarieren einer `for` Schleife und dann versucht wird, die außerhalb des Bereichs der Iteratorvariablen verwenden die `for` Schleife. Kompilieren von C++-Standardbibliothek Code mit einer Debugversion der C-Laufzeit impliziert [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  Finden Sie unter [Debug Iterator Support](../../standard-library/debug-iterator-support.md) Weitere Informationen.  
  
5.  Sie rufen möglicherweise eine Funktion in einer SDK-Headerdatei auf, die in der aktuellen Buildumgebung nicht unterstützt wird.  
  
6.  Erforderliche Includedateien fehlen, insbesondere bei der Definition von `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN` oder `WIN32_EXTRA_LEAN`. Um die Kompilierung zu beschleunigen, werden durch diese Symbole einige Headerdateien aus windows.h und afxv_w32.h ausgeschlossen. (Überprüfen Sie die Dateien windows.h und afxv_w32.h auf eine aktuelle Beschreibung der ausgeschlossenen Dateien.)  
  
7.  Falscher Gültigkeitsbereich für den Namespace. Um beispielsweise Funktionen und Operatoren der C++-Standardbibliothek aufzulösen, müssen Sie den `std`-Namespace mit der `using`-Direktive angeben. Im folgenden Beispielcode tritt ein Fehler bei der Kompilierung auf, da die `using`-Direktive auskommentiert und `cout` im `std`-Namespace definiert wird:  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2065 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## <a name="example"></a>Beispiel  
 Wenn Sie eine generische Funktion aufrufen und das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann, gibt der Compiler einen Fehler aus. Weitere Informationen finden Sie unter [generische Funktionen (C++ / CLI)](../../windows/generic-functions-cpp-cli.md).  
  
 Im folgenden Beispiel wird C2065 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example"></a>Beispiel  
 Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual C++ 2005 auftreten, und zwar beim Überprüfen der Parameter für Visual C++-Attribute.  
  
 Im folgenden Beispiel wird C2065 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```
