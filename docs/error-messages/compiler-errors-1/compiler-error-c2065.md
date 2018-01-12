---
title: Compilerfehler Fehler C2065 | Microsoft Docs
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2065
dev_langs: C++
helpviewer_keywords: C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5dec660bd2f47cb1e95569ced6bead2dd42fc2da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2065"></a>Compilerfehler Fehler C2065

> "*Bezeichner*': nicht deklarierter Bezeichner  
  
Der Compiler nicht die Deklaration für einen Bezeichner gefunden. Es gibt zahlreiche mögliche Ursachen für diesen Fehler. Die häufigsten Ursachen für C2065 sind, dass der Bezeichner wurde nicht deklariert wurde, der Bezeichner ist falsch geschrieben, der Header, in dem der Bezeichner deklariert wird, nicht in der Datei enthalten ist oder der Bezeichner bereichsqualifizierer, z. B. fehlt `cout` anstelle von `std::cout`. Weitere Informationen über Deklarationen in C++, finden Sie unter [Deklarationen und Definitionen (C++)](../../cpp/declarations-and-definitions-cpp.md).
  
Hier sind einige allgemeine Probleme und Lösungen genauer an.

## <a name="the-identifier-is-undeclared"></a>Der Bezeichner wurde nicht deklariert

Ist der Bezeichner einer Variablen oder einem Funktionsnamen, müssen Sie sie deklarieren, bevor er verwendet werden kann. Eine Funktionsdeklaration muss auch die Typen ihrer Parameter einschließen, bevor die Funktion verwendet werden kann. Wenn die Variable deklariert wird mit `auto`, der Compiler muss in der Lage, den Typ von seinem Initialisierer abzuleiten.

Wenn der Bezeichner ein Member einer Klasse oder Struktur ist oder in einem Namespace deklariert, muss von der Klassen- oder Strukturnamen oder den Namespacenamen qualifiziert werden bei Verwendung außerhalb des Bereichs-Struktur, Klasse oder Namespace. Alternativ können Sie der Namespace muss eingebunden werden durch eine `using` wie z. B. die Richtlinie `using namespace std;`, oder der Elementname muss eingebunden werden durch eine `using` Deklaration, z. B. `using std::string;`. Der nicht qualifizierte Name gilt, andernfalls werden einen nicht deklarierten Bezeichner im aktuellen Bereich.

Wenn der Bezeichner des Tags für einen benutzerdefinierten Typ, z. B. eine `class` oder `struct`, der Typ des Tags muss deklariert werden, bevor er verwendet werden kann. Z. B. die Deklaration `struct SomeStruct { /*...*/ };` muss vorhanden sein, bevor Sie eine Variable deklarieren können `SomeStruct myStruct;` im Code.

Wenn der Bezeichner ein Typalias ist, muss der Typ deklariert werden, mithilfe einer `using` Deklaration oder `typedef` , bevor er verwendet werden kann. Sie müssen z. B. deklarieren `using my_flags = std::ios_base::fmtflags;` vor der Verwendung `my_flags` als ein Typalias für `std::ios_base::fmtflags`.
  
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
  
## <a name="example-use-an-unscoped-identifier"></a>Beispiel: Verwenden Sie eine ohne bereichseinschränkung ID. 
  
Dieser Fehler kann auftreten, wenn der Bezeichner nicht ordnungsgemäß festgelegt ist. Wenn Sie C2065 angezeigt, bei der Verwendung `cout`, dies ist die Ursache. Bei C++-Standardbibliothek Funktionen und Operatoren werden nicht vollständig qualifiziert, durch den Namespace oder Sie haben nicht geschaltet der `std` Namespace in den aktuellen Bereich mithilfe einer `using` -Direktive der Compiler nicht finden können. Um dieses Problem zu beheben, müssen Sie vollständig qualifizierte Bezeichnernamen, oder geben Sie den Namespace mit der `using` Richtlinie.  
  
In diesem Beispiel wird nicht kompiliert, da `cout` und `endl` definiert sind, der `std` Namespace:  
  
```cpp  
// C2065_scope.cpp  
// compile with: cl /EHsc C2065_scope.cpp
#include <iostream>  
// using namespace std;   // Uncomment this line to fix  

int main() {  
    cout << "Hello" << endl;   // C2065 'cout': undeclared identifier 
                               // C2065 'endl': undeclared identifier
    // Or try the following line instead  
    std::cout << "Hello" << std::endl;  
}
```  
  
Bezeichner, die innerhalb eines deklarierten `class`, `struct`, oder `enum class` Typen müssen auch durch den Namen von ihrem umschließenden Bereich qualifiziert werden, bei Verwendung außerhalb dieses Bereichs.
  
## <a name="example-missing-header-file"></a>Beispiel: fehlende Headerdatei.  
  
Sie haben nicht die Header-Datei enthalten, die den Bezeichner deklariert. Stellen Sie sicher, dass die Datei mit der Deklaration des Bezeichners in jede Quelldatei enthalten ist, die verwendet werden.  
  
```cpp  
// C2065_header.cpp  
// compile with: cl /EHsc C2065_header.cpp 

//#include <stdio.h> 
int main() { 
    fpos_t file_position = 42; // C2065: 'fpos_t': undeclared identifier 
    // To fix, uncomment the #include <stdio.h> line
    // to include the header where fpos_t is defined  
} 
```  

Ein weiterer möglicher Grund ist bei Verwendung eine Initialisiererliste ohne Angabe der \<initializer_list-Element > Header.

```cpp  
// C2065_initializer.cpp  
// compile with: cl /EHsc C2065_initializer.cpp 

// #include <initializer_list> 
int main() { 
    for (auto strList : {"hello", "world"})
        if (strList == "hello") // C2065: 'strList': undeclared identifier 
            return 1; 
    // To fix, uncomment the #include <initializer_list> line
} 
```  
  
Dieser Fehler in den Quelldateien für Windows-Desktop-app möglicherweise angezeigt werden, wenn Sie definieren `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN`, oder `WIN32_EXTRA_LEAN`. Diese Präprozessormakros einige Headerdateien aus windows.h und Afxv ausschließen\_w32.h beschleunigen kompiliert. Suchen Sie in windows.h und afxv_w32.h auf eine aktuelle Beschreibung der ausgeschlossenen.  
  
## <a name="example-missing-closing-quote"></a>Beispiel: Fehlendes schließendes Anführungszeichen  
  
Dieser Fehler kann auftreten, wenn ein schließendes Anführungszeichen hinter einer Zeichenfolgenkonstante fehlt. Dies ist eine einfache Möglichkeit, die den Compiler Schreibzugriff zu verwechseln. Beachten Sie, dass die fehlende schließende Anführungszeichen mehrere Zeilen vor dem gemeldeten Fehler. 
  
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
  
## <a name="example-ccli-type-deduction-failure"></a>Beispiel: C + c++ / CLI-Typ Abzug Fehler  
  
Dieser Fehler kann auftreten, wenn eine generische Funktion aufrufen und das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann. Weitere Informationen finden Sie unter [generische Funktionen (C + c++ / CLI)](../../windows/generic-functions-cpp-cli.md).  
  
```cpp  
// C2065_b.cpp  
// compile with: cl /clr C2065_b.cpp 
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);     // C2065  
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
