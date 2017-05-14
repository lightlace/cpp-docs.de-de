---
title: Compilerfehler Fehler C2065 | Microsoft Docs
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 5a3a0d4389a958f421f23a4dc96a395eaf3e22ab
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-error-c2065"></a>Compilerfehler Fehler C2065
„Bezeichner“: nicht deklarierter Bezeichner.  
  
Der Compiler nicht die Deklaration für einen Bezeichner gefunden. Wenn der Bezeichner eine Variable ist, müssen Sie den Typ der Variablen in einer Deklaration angeben, bevor er verwendet werden kann. Ist der Bezeichner eines Funktionsnamens, müssen der Parameter, die die Funktion verwendet in einer Deklaration angegeben werden, bevor die Funktion verwendet werden kann. Wenn der Bezeichner des Tags für einen benutzerdefinierten Typ, z. B. eine `class` oder `struct`, der Typ des Tags muss deklariert werden, bevor er verwendet werden kann. Wenn der Bezeichner ein Typalias ist, muss der Typ deklariert werden, mithilfe einer `using` Deklaration oder `typedef` vor den Typ verwendet werden kann.  
  
Es gibt zahlreiche mögliche Ursachen für diesen Fehler. Hier sind einige der am häufigsten auftretenden Probleme:
  
## <a name="example-misspelled-identifier"></a>Beispiel: falsch geschriebenes Kennung  
  
Dieser Fehler tritt häufig auf, wenn der Bezeichnername falsch geschrieben ist oder der Bezeichner wird, die falschen Groß- und Kleinbuchstaben Buchstaben verwendet. Der Name in der Deklaration muss genau mit den Namen entsprechen, den Sie verwenden.  
  
```cpp  
// C2065_spell.cpp  
// compile with: cl /EHsc C2065_spell.cpp 
#include <iostream> 
using namespace std; 
int main() { 
    int someIdentifier = 42; 
    cout << "Some Identifier: " << SomeIdentifier << endl;   
    // C2065: 'SomeIdentifier': undeclared identifier 
    // To fix, correct the spelling:  
    // cout << "Some Identifier: " << someIdentifier << endl;   
}  
```
  
## <a name="example-missing-header-file"></a>Beispiel: fehlende Headerdatei.  
  
Sie haben nicht die Header-Datei enthalten, die den Bezeichner deklariert. Stellen Sie sicher, dass die Datei mit der Deklaration des Bezeichners in jede Quelldatei enthalten ist, die verwendet werden.  
  
```cpp  
// C2065_header.cpp  
// compile with: cl /EHsc C2065_spell.cpp 

//#include <stdio.h> 
int main() { 
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier 
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined  
} 
```  
  
Dieser Fehler in den Quelldateien für Windows-Desktop-app möglicherweise angezeigt werden, wenn Sie definieren `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, oder `WIN32_EXTRA_LEAN`. Diese Präprozessormakros einige Headerdateien aus windows.h und Afxv ausschließen\_w32.h beschleunigen kompiliert. Suchen Sie in windows.h und afxv_w32.h auf eine aktuelle Beschreibung der ausgeschlossenen.  
  
## <a name="eample-missing-closing-quote"></a>Eample: Fehlendes schließendes Anführungszeichen  
  
Dieser Fehler kann auftreten, wenn ein schließendes Anführungszeichen hinter einer Zeichenfolgenkonstante fehlt. Dies ist eine einfache Möglichkeit, die den Compiler Schreibzugriff zu verwechseln. 
  
```cpp  
// C2065_quote.cpp  
// compile with: cl /EHsc C2065_quote.cpp 
#include <iostream>  

int main() { 
    // Fix this issue by adding the closing quote to "Aaaa"
    char * first = "Aaaa, * last = "Zeee"; 
    std::cout << "Name: " << first 
        << " " << last << std::endl; // C2065: 'last': undeclared identifier 
} 
```  
  
## <a name="example-use-iterator-outside-for-loop-scope"></a>Beispiel: Verwenden von Iterator außerhalb for-Schleifenbereich  
  
Dieser Fehler kann auftreten, wenn Sie eine Iteratorvariable in Deklarieren einer `for` Schleife, und anschließend versuchen, diese Iteratorvariable außerhalb des Bereichs der verwenden die `for` Schleife. Ermöglicht der Compiler die [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) -Compileroption in der Standardeinstellung. Finden Sie unter [Debugiterator-Unterstützung](../../standard-library/debug-iterator-support.md) für Weitere Informationen.  
  
```cpp  
// C2065_iter.cpp  
// compile with: cl /EHsc C2065_iter.cpp 
#include <iostream> 
#include <string> 

int main() {
    // char last = '!'; 
    std::string letters{ "ABCDEFGHIJKLMNOPQRSTUVWXYZ" }; 
    for (const char& c : letters) {
        if ('Q' == c) {
            std::cout << "Found Q!" << std::endl;
        }
        // last = c;
    }
    std::cout << "Last letter was " << c << std::endl; // C2065
    // Fix by using a variable declared in an outer scope.
    // Uncomment the lines that declare and use 'last' for an example.
    // std::cout << "Last letter was " << last << std::endl; // C2065
} 
```  
  
## <a name="example-preprocessor-removed-declaration"></a>Beispiel: Präprozessor entfernt Deklaration  
  
Dieser Fehler kann auftreten, wenn Sie verweisen auf eine Funktion oder Variable, die in bedingt kompiliertem Code enthalten ist, die nicht für die aktuelle Konfiguration kompiliert wird. Dies kann auch auftreten, wenn Sie eine Funktion in einer Headerdatei aufrufen, die in der Buildumgebung derzeit nicht unterstützt wird. Wenn bestimmte Variablen oder Funktionen nur verfügbar sind, wenn ein bestimmtes Präprozessormakro definiert ist, stellen Sie sicher, dass der Code, der diese Funktionen aufruft nur kompiliert werden kann, wenn das gleiche Präprozessormakro definiert ist. Dieses Problem ist einfach zu erkennen, in der IDE, da die Deklaration für die Funktion abgeblendet ist, wenn die erforderlichen Präprozessormakros nicht für die aktuelle Buildkonfiguration definiert sind.  
  
Dies ist ein Beispiel für Code, wenn Sie im Debugmodus erstellen, jedoch nicht Retail funktioniert:  
  
```cpp  
// C2065_defined.cpp
// Compile with: cl /EHsc /W4 /MT C2065_defined.cpp
#include <iostream>
#include <crtdbg.h>
#ifdef _DEBUG
    _CrtMemState oldstate;
#endif
int main() {
    _CrtMemDumpStatistics(&oldstate); 
    std::cout << "Total count " << oldstate.lTotalCount; // C2065
    // Fix by guarding references the same way as the declaration:
    // #ifdef _DEBUG
    //    std::cout << "Total count " << oldstate.lTotalCount;
    // #endif
}
```
  
## <a name="example-use-an-unscoped-identifier"></a>Beispiel: Verwenden Sie eine ohne bereichseinschränkung ID.  
  
Dieser Fehler kann auftreten, wenn der Bezeichner nicht ordnungsgemäß festgelegt ist. Z. B. wenn C++-Standardbibliothek Funktionen und Operatoren werden nicht vollständig qualifiziert, durch den Namespace, oder Sie haben nicht geschaltet der `std` Namespace in den aktuellen Bereich mithilfe einer `using` -Direktive der Compiler nicht finden können. Um dieses Problem zu beheben, müssen Sie vollständig qualifizierte Bezeichnernamen, oder geben Sie den Namespace mit der `using` Richtlinie.  
  
In diesem Beispiel wird nicht kompiliert, da `cout` und `endl` definiert sind, der `std` Namespace:  
  
```cpp  
// C2065_scope.cpp  
// compile with: cl /EHsc C2065_scope.cpp 
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier 
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead  
    std::cout << "Hello" << std::endl;  
}
```  
  
Bezeichner, die innerhalb eines deklarierten `class`, `struct`, oder `enum class` Typen auch durch den Namen der einschließenden Bereich gekennzeichnet sein müssen.
  
## <a name="example-ccli-type-deduction-failure"></a>Beispiel: C + c++ / CLI-Typ Abzug Fehler  
  
Dieser Fehler kann auftreten, wenn eine generische Funktion aufrufen und das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann. Weitere Informationen finden Sie unter [generische Funktionen (C + c++ / CLI)](../../windows/generic-functions-cpp-cli.md).  
  
```cpp  
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
  
## <a name="example-ccli-attribute-parameters"></a>Beispiel: C + c++ / CLI-Attribut-Parameter  
  
Dieser Fehler kann außerdem infolge einer Konformitätsverbesserung für Compiler für Visual C++ 2005 auftreten, und zwar beim Überprüfen der Parameter für Visual C++-Attribute.  
  
```cpp  
// C2065_attributes.cpp  
// compile with: cl /c /clr C2065_attributes.cpp  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  

