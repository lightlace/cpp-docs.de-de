---
title: Speicherklassen (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
dev_langs:
- C++
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: db5a6c23d11f8cdf144e42aee4880ee1ac26066a
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="storage-classes-c"></a>Speicherklassen (C++)  
  
Ein *Speicherklasse* im Kontext von C++-Variablendeklarationen ist ein Typbezeichner, die die Lebensdauer, Bindung und Speicherort von Objekten steuert. Ein angegebenes Objekt kann nur eine Speicherklasse haben. Variablen, die innerhalb eines Blocks definiert sind, haben automatischen Speicher, wenn nicht anders mithilfe der Bezeichner `extern`, `static` oder `thread_local` angegeben. Automatische Objekte und Variablen haben keine Bindung; sie sind für Code außerhalb des Blocks nicht sichtbar.  
  
**Notizen**  
  
1.  Die [änderbare](../cpp/mutable-data-members-cpp.md) Schlüsselwort kann als Speicherklassenspezifizierer angesehen werden. Es ist jedoch nur in der Memberliste einer Klassendefinition verfügbar.  
  
2.  **Visual C++ 2010 und höher:** der `auto` Schlüsselwort ist nicht mehr als eine C++-Speicherklassenspezifizierer, und die `register` Schlüsselwort ist veraltet. **Visual Studio 2017 15,3 und höher:** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): die `register` Schlüsselwort ist nicht mehr unterstützte Speicherklasse. Das Schlüsselwort ist immer noch in der Standard für zukünftige Verwendung reserviert. 
```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>In diesem Abschnitt
  
-   [static](#static)  
-   [extern](#extern)  
-   [thread_local](#thread_local)

<a name="static"></a>
  
## <a name="static"></a>static  
  
Das `static`-Schlüsselwort kann zum Deklarieren von Variablen und Funktionen im globalen Gültigkeitsbereich, Namespace-Gültigkeitsbereich und Klassengültigkeitsbereich verwendet werden. Statische Variablen können auch im lokalen Gültigkeitsbereich deklariert werden.  
  
Statische Dauer bedeutet, dass das Objekt oder die Variable zugewiesen wird, wenn das Programm gestartet wird. Die Zuweisung wird wieder aufgehoben, wenn das Programm beendet wird. Externe Verknüpfung bedeutet, dass der Name der Variablen von außerhalb der Datei sichtbar ist, in der die Variable deklariert wird. Umgekehrt bedeutet interne Verknüpfung, dass der Name nicht außerhalb der Datei sichtbar ist, in der die Variable deklariert wird. Standardmäßig verfügt ein Objekt oder eine Variable, das bzw. die im globalen Namespace definiert wird, über eine statische Dauer und externe Verknüpfung. Das `static`-Schlüsselwort kann in folgenden Situationen verwendet werden:  
  
1.  Wenn Sie eine Variable oder eine Funktion im Dateibereich (globaler und/oder Namespacebereich) deklarieren, gibt das `static`-Schlüsselwort die Variable oder Funktion mit interner Verknüpfung an. Wenn Sie eine Variable deklarieren, hat die Variable eine statische Dauer und wird vom Compiler mit dem Wert 0 initialisiert, solange Sie keinen anderen Wert angeben.  
  
2.  Wenn Sie eine Variable in einer Funktion deklarieren, gibt das `static`-Schlüsselwort an, dass die Variable ihren Status zwischen den Aufrufen der Funktion beibehält.  
  
3.  Wenn Sie einen Datenmember in einer Klassendeklaration deklarieren, gibt das `static`-Schlüsselwort an, dass eine Kopie des Members für alle Instanzen der Klasse freigegeben wird. Ein statischer Datenmember muss im Dateibereich definiert sein. Ein ganzzahliger Datenmember, die Sie als deklarieren `const static` kann einen Initialisierer haben.  
  
4.  Wenn Sie eine Memberfunktion in einer Klassendeklaration deklarieren, gibt das `static`-Schlüsselwort an, dass die Funktion für alle Instanzen der Klasse freigegeben wird. Eine statische Memberfunktion kann nicht auf einen Instanzmember zugreifen, weil die Funktion keinen impliziten `this` Zeiger aufweist. Um auf einen Instanzmember zuzugreifen, deklarieren Sie die Funktion mit einem Parameter, der ein Instanzzeiger oder -verweis ist.  
  
5.  Sie können die Member einer Union nicht als statisch deklarieren. Allerdings muss eine global deklarierte anonyme Union explizit als `static` deklariert werden.  
  
In diesem Beispiel wird gezeigt, wie eine Variable deklariert `static` in einer Funktion behält ihren Status zwischen den Aufrufen der Funktion.  
  
```cpp  
// static1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
void showstat( int curr ) {  
   static int nStatic;    // Value of nStatic is retained  
                          // between each function call  
   nStatic += curr;  
   cout << "nStatic is " << nStatic << endl;  
}  
  
int main() {  
   for ( int i = 0; i < 5; i++ )  
      showstat( i );  
}  
```  
  
```Output  
nStatic is 0  
nStatic is 1  
nStatic is 3  
nStatic is 6  
nStatic is 10  
```  
  
Dieses Beispiel zeigt die Verwendung von `static` in einer Klasse.  
  
```cpp  
// static2.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class CMyClass {  
public:  
   static int m_i;  
};  
  
int CMyClass::m_i = 0;  
CMyClass myObject1;  
CMyClass myObject2;  
  
int main() {  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject1.m_i = 1;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   myObject2.m_i = 2;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
  
   CMyClass::m_i = 3;  
   cout << myObject1.m_i << endl;  
   cout << myObject2.m_i << endl;  
}  
```  
  
```Output  
0  
0  
1  
1  
2  
2  
3  
3  
```  
  
Dieses Beispiel zeigt eine lokale Variable deklariert `static` in einer Memberfunktion. Die statische Variable ist im gesamten Programm verfügbar. Alle Instanzen des Typs verwenden dieselbe Kopie der statischen Variable.  
  
```cpp  
// static3.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
struct C {  
   void Test(int value) {  
      static int var = 0;  
      if (var == value)   
         cout << "var == value" << endl;  
      else  
         cout << "var != value" << endl;  
  
      var = value;  
   }  
};   
  
int main() {  
   C c1;  
   C c2;  
   c1.Test(100);  
   c2.Test(100);  
}  
```  
  
```Output  
var != value  
var == value  
```  
  
Ab C++11 ist eine statische lokale Variableninitialisierung auf jeden Fall threadsicher. Dieses Feature wird manchmal bezeichnet *"magische" static-Objekte*. Allerdings müssen alle nachfolgende Zuweisungen in einer Multithreadanwendung synchronisiert werden. Die Thread-sichere statischen Initialisierung-Feature kann deaktiviert werden, mithilfe der [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) zu vermeiden, erstellen eine Abhängigkeit vom CRT-Flag.  
  
<a name="extern"></a>  
  
## <a name="extern"></a>extern  
  
Objekte und Variablen, die als `extern` deklariert werden, deklarieren ein Objekt, das in einer anderen Übersetzungseinheit oder in einem einschließenden Bereich mit externer Verknüpfung definiert ist.  
  
Deklaration von `const` Variablen mit der `extern` -Speicherklasse erzwingt, dass die Variable an eine externe Bindung aufweisen. Eine Initialisierung einer `extern const` Variable ist in der definierenden Übersetzungseinheit zulässig. Initialisierungen in Übersetzungseinheiten, die keine definierenden Übersetzungseinheiten sind, erzeugen nicht definierte Ergebnisse. Weitere Informationen finden Sie unter [mithilfe von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)  
  
Der folgende Code zeigt zwei `extern`-Deklarationen, `DefinedElsewhere` (die sich auf einen Namen bezieht, der in einer anderen Übersetzungseinheit definiert wurde) und `DefinedHere` (die sich auf einen Namen bezieht, der in einem einschließenden Bereich definiert wurde):  
  
```cpp  
// external.cpp  
// DefinedElsewhere is defined in another translation unit  
extern int DefinedElsewhere;     
int main() {  
   int DefinedHere;   
   {  
      // refers to DefinedHere in the enclosing scope  
      extern int DefinedHere;  
   }  
}  
```  
  
<a name="thread_local"></a>  
  
## <a name="threadlocal-c11"></a>thread_local (C++11)  
  
Auf eine Variable, die mit dem `thread_local`-Bezeichner deklariert wird, kann nur in dem Thread, in dem sie erstellt wird, zugegriffen werden. Die Variable wird erstellt, wenn der Thread erstellt, und gelöscht, wenn der Thread gelöscht wird. Jeder Thread verfügt über eine eigene Kopie der Variable. Unter Windows `thread_local` ist funktionell gleichwertig mit der Microsoft-spezifische [__declspec (Thread)](../cpp/thread.md) Attribut.  
  
```cpp  
thread_local float f = 42.0; // Global namespace. Not implicitly static.
  
struct S // cannot be applied to type definition  
{  
    thread_local int i; // Illegal. The member must be static.  
    thread_local static char buf[10]; // OK 
};  
  
void DoSomething()  
{  
    // Apply thread_local to a local variable.
    // Implicitly "thread_local static S my_struct".
    thread_local S my_struct;  
}  
```  
  
Dinge zu beachten Sie die `thread_local` Bezeichner:  
  
-  Die `thread_local` Bezeichner kann mit kombiniert werden `static` oder `extern`.  
  
-  Sie können anwenden `thread_local` nur auf Datendeklarationen und-Definitionen; `thread_local` kann nicht für Funktionsdeklarationen oder-Definitionen verwendet werden.  
  
-  Die Verwendung von `thread_local` beeinträchtigen möglicherweise [das verzögerte Laden](../build/reference/linker-support-for-delay-loaded-dlls.md) von DLL-Importen. 
  
-  Auf XP-Systemen `thread_local` möglicherweise nicht ordnungsgemäß, wenn eine DLL verwendet `thread_local` Daten und dynamisch über geladen wird `LoadLibrary`.  
  
-  Sie können `thread_local` nur für Datenelemente mit statischer Speicherdauer angeben. Hierzu zählen globale Datenobjekte (sowohl `static` und `extern`), lokale statische Objekte sowie statische Datenmember von Klassen. Jede lokale Variable deklariert `thread_local` ist implizit statisch, wenn keine anderen Speicherklasse angegeben wird; also am Blockbereich `thread_local` entspricht `thread_local static`. 
  
-  Sie müssen das `thread_local` für die Deklaration und Definition eines lokalen Threadobjekts angeben, egal ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.  
  
Unter Windows `thread_local` ist funktionell gleichwertig mit [__declspec(thread)](../cpp/thread.md) mit dem Unterschied, dass `__declspec(thread)` kann auf eine Typdefinition angewendet werden und in C-Code gültig ist. Verwenden Sie nach Möglichkeit `thread_local`, da dies ein Teil des C++-Standards ist und daher besser zu potieren ist.  
  
##  <a name="register"></a>Registrieren  
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): die `register` Schlüsselwort ist nicht mehr unterstützte Speicherklasse. Das Schlüsselwort ist immer noch in der Standard für zukünftige Verwendung reserviert. 

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Beispiel: automatische im Vergleich zu statischen Initialisierung  
  
Ein lokales automatisches Objekt oder eine lokale automatische Variable wird jedes Mal initialisiert, wenn die Ablaufsteuerung ihre Definition erreicht. Ein lokales automatisches Objekt oder eine lokale automatische Variable wird erstmalig initialisiert, wenn die Ablaufsteuerung ihre Definition erreicht.  
  
Betrachten Sie das folgende Beispiel, in dem eine Klasse definiert wird, die die Initialisierung und Beschädigung von Objekten protokolliert und dann drei Objekte, `I1`, `I2` und `I3`, definiert:  
  
```cpp  
// initialization_of_objects.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
using namespace std;  
  
// Define a class that logs initializations and destructions.  
class InitDemo {  
public:  
    InitDemo( const char *szWhat );  
    ~InitDemo();  
  
private:  
    char *szObjName;  
    size_t sizeofObjName;  
};  
  
// Constructor for class InitDemo  
InitDemo::InitDemo( const char *szWhat ) :  
    szObjName(NULL), sizeofObjName(0) {  
    if ( szWhat != 0 && strlen( szWhat ) > 0 ) {  
        // Allocate storage for szObjName, then copy  
        // initializer szWhat into szObjName, using  
        // secured CRT functions.  
        sizeofObjName = strlen( szWhat ) + 1;  
  
        szObjName = new char[ sizeofObjName ];  
        strcpy_s( szObjName, sizeofObjName, szWhat );  
  
        cout << "Initializing: " << szObjName << "\n";  
    }  
    else {  
        szObjName = 0;  
    }
}  
  
// Destructor for InitDemo  
InitDemo::~InitDemo() {  
    if( szObjName != 0 ) {  
        cout << "Destroying: " << szObjName << "\n";  
        delete szObjName;  
    }  
}  
  
// Enter main function  
int main() {  
    InitDemo I1( "Auto I1" ); {  
        cout << "In block.\n";  
        InitDemo I2( "Auto I2" );  
        static InitDemo I3( "Static I3" );  
    }  
    cout << "Exited block.\n";  
}  
```  
  
```Output  
Initializing: Auto I1  
In block.  
Initializing: Auto I2  
Initializing: Static I3  
Destroying: Auto I2  
Exited block.  
Destroying: Auto I1  
Destroying: Static I3  
```  
  
In diesem Beispiel wird veranschaulicht, wie und wann die Objekte `I1`, `I2`, und `I3` werden initialisiert und zerstört werden.  
  
Es gibt einige Punkte zu beachten über das Programm:  
  
- Erstens werden `I1` und `I2` automatisch beschädigt, wenn die Ablaufsteuerung den Block beendet, in dem sie definiert sind.  
  
- Zweitens ist es in C++ nicht notwendig, Objekte oder Variablen am Anfang eines Blocks zu deklarieren. Außerdem werden diese Objekte nur initialisiert, wenn die Ablaufsteuerung deren Definitionen erreicht. (`I2` und `I3` sind Beispiele solcher Definitionen.) Die Ausgabe zeigt eindeutig, wann sie initialisiert werden.  
  
- Des Weiteren behalten statische lokale Variablen wie `I3` ihre Werte für die Dauer des Programms bei, werden jedoch beschädigt, sobald das Programm beendet wird.  
  
## <a name="see-also"></a>Siehe auch  
  
 [Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)

