---
title: "Compilerfehler C2065"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2065"
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
caps.handback.revision: "20"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Bezeichner“: nicht deklarierter Bezeichner.  
  
 Ein Variablentyp muss vor seiner Verwendung in einer Deklaration angegeben werden.  Die von einer Funktion verwendeten Parameter müssen in einer Deklaration oder einem Prototyp angegeben werden, bevor die Funktion verwendet werden kann.  
  
 Mögliche Ursachen:  
  
1.  Der Bezeichnername ist falsch geschrieben.  
  
2.  Im Bezeichnernamen wird eine falsche Groß\-\/Kleinschreibung verwendet.  
  
3.  Hinter einer Zeichenfolgenkonstante fehlt ein schließendes Anführungszeichen.  
  
4.  Sie kompilieren mit einer Debugversion der C\-Laufzeit, und dadurch wird in einer `for`\-Schleife eine Iteratorvariable aus der C\+\+\-Standardbibliothek deklariert. Anschließend wird versucht, diese Iteratorvariable außerhalb des Gültigkeitsbereichs der `for`\-Schleife zu verwenden.  Beim Kompilieren eines C\+\+\-Standardbibliothekscodes mit einer Debugversion der C\-Laufzeit wird [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) impliziert.  Weitere Informationen finden Sie unter [Debugiterator\-Unterstützung](../../standard-library/debug-iterator-support.md).  
  
5.  Sie rufen möglicherweise eine Funktion in einer SDK\-Headerdatei auf, die in der aktuellen Buildumgebung nicht unterstützt wird.  
  
6.  Erforderliche Includedateien fehlen, insbesondere bei der Definition von `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN` oder `WIN32_EXTRA_LEAN`.  Um die Kompilierung zu beschleunigen, werden durch diese Symbole einige Headerdateien aus windows.h und afxv\_w32.h ausgeschlossen.  \(Überprüfen Sie die Dateien windows.h und afxv\_w32.h auf eine aktuelle Beschreibung der ausgeschlossenen Dateien.\)  
  
7.  Falscher Gültigkeitsbereich für den Namespace.  Um beispielsweise Funktionen und Operatoren der C\+\+\-Standardbibliothek aufzulösen, müssen Sie den `std`\-Namespace mit der `using`\-Direktive angeben.  Im folgenden Beispielcode tritt ein Fehler bei der Kompilierung auf, da die `using`\-Direktive auskommentiert und `cout` im `std`\-Namespace definiert wird:  
  
## Beispiel  
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
  
## Beispiel  
 Wenn Sie eine generische Funktion aufrufen und das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann, gibt der Compiler einen Fehler aus.  Weitere Informationen finden Sie unter [Generic Functions \(C\+\+\/CLI\)](../../windows/generic-functions-cpp-cli.md).  
  
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
  
## Beispiel  
 Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual C\+\+ 2005 auftreten, und zwar beim Überprüfen der Parameter für Visual C\+\+\-Attribute.  
  
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