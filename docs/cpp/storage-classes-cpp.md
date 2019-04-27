---
title: Speicherklassen (C++)
ms.date: 11/04/2016
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: e50e5da5ea24d59131f123bb0c772897f9a30218
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266932"
---
# <a name="storage-classes-c"></a>Speicherklassen (C++)

Ein *Speicherklasse* im Kontext von C++-Variablendeklarationen ist ein Typbezeichner, der die Lebensdauer, Bindung und Speicherort von Objekten steuert. Ein angegebenes Objekt kann nur eine Speicherklasse haben. Variablen, die innerhalb eines Blocks definiert haben automatischen Speicher, sofern nicht anders angegeben, mit der **"extern"**, **statische**, oder `thread_local` Spezifizierer. Automatische Objekte und Variablen haben keine Bindung; sie sind für Code außerhalb des Blocks nicht sichtbar.

**Notizen**

1. Die [änderbare](../cpp/mutable-data-members-cpp.md) Schlüsselwort als Speicherklassenspezifizierer angesehen werden kann. Es ist jedoch nur in der Memberliste einer Klassendefinition verfügbar.

1. **Visual C++ 2010 und höher:** Die **automatisch** Schlüsselwort ist nicht mehr eine C++-Speicherklassenspezifizierer, und die **registrieren** Schlüsselwort ist veraltet. **Visual Studio 2017 Version 15.7 und höher:** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Die **registrieren** Schlüsselwort aus der Programmiersprache C++ entfernt.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>In diesem Abschnitt

- [static](#static)
- [extern](#extern)
- [thread_local](#thread_local)

## <a name="static"></a> Statische

Die **statische** -Schlüsselwort zum Deklarieren von Variablen und Funktionen im globalen Gültigkeitsbereich, Namespace-Gültigkeitsbereich und Klassengültigkeitsbereich verwendet werden kann. Statische Variablen können auch im lokalen Gültigkeitsbereich deklariert werden.

Statische Dauer bedeutet, dass das Objekt oder die Variable zugewiesen wird, wenn das Programm gestartet wird. Die Zuweisung wird wieder aufgehoben, wenn das Programm beendet wird. Externe Verknüpfung bedeutet, dass der Name der Variablen von außerhalb der Datei sichtbar ist, in der die Variable deklariert wird. Umgekehrt bedeutet interne Verknüpfung, dass der Name nicht außerhalb der Datei sichtbar ist, in der die Variable deklariert wird. Standardmäßig verfügt ein Objekt oder eine Variable, das bzw. die im globalen Namespace definiert wird, über eine statische Dauer und externe Verknüpfung. Die **statische** -Schlüsselwort kann in den folgenden Situationen verwendet werden.

1. Wenn Sie deklarieren eine Variable oder Funktion im Dateibereich (globaler und/oder Namespacebereich), wird die **statische** -Schlüsselwort Gibt an, dass die Variable oder Funktion intern verknüpft ist. Wenn Sie eine Variable deklarieren, hat die Variable eine statische Dauer und wird vom Compiler mit dem Wert 0 initialisiert, solange Sie keinen anderen Wert angeben.

1. Wenn Sie eine Variable in einer Funktion deklarieren die **statische** -Schlüsselwort Gibt an, dass die Variable ihren Status zwischen den Aufrufen der Funktion beibehält.

1. Wenn Sie einen Datenmember in einer Klassendeklaration deklarieren die **statische** -Schlüsselwort Gibt an, dass alle Instanzen der Klasse eine Kopie des Elements freigegeben wird. Ein statischer Datenmember muss im Dateibereich definiert sein. Ein ganzzahliger Datenmember, die Sie als deklarieren **const statische** kann einen Initialisierer haben.

1. Wenn Sie eine Memberfunktion in einer Klassendeklaration deklarieren die **statische** -Schlüsselwort Gibt an, dass die Funktion alle Instanzen der Klasse freigegeben wird. Eine statische Memberfunktion kann nicht auf einen Instanzmember zugreifen, da die Funktion einen impliziten keine **dies** Zeiger. Um auf einen Instanzmember zuzugreifen, deklarieren Sie die Funktion mit einem Parameter, der ein Instanzzeiger oder -verweis ist.

1. Sie können die Member einer Union nicht als statisch deklarieren. Allerdings eine global deklarierte anonyme Union explizit deklariert werden muss **statische**.

Dieses Beispiel zeigt, wie eine Variable deklariert **statische** in einer Funktion behält den Zustand zwischen Aufrufen der Funktion.

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

Dieses Beispiel zeigt die Verwendung von **statische** in einer Klasse.

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

Dieses Beispiel zeigt eine lokale Variable deklariert **statische** in einer Memberfunktion. Die statische Variable ist im gesamten Programm verfügbar. Alle Instanzen des Typs verwenden dieselbe Kopie der statischen Variable.

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

Ab C++11 ist eine statische lokale Variableninitialisierung auf jeden Fall threadsicher. Dieses Feature wird manchmal genannt *magic Statics*. Allerdings müssen alle nachfolgende Zuweisungen in einer Multithreadanwendung synchronisiert werden. Die Funktion für threadsichere statische Initialisierung kann deaktiviert werden, mithilfe der [/Zc:threadSafeInit-](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) Flag, um zu vermeiden, erstellen eine Abhängigkeit vom CRT.

## <a name="extern"></a> "extern"

Objekte und Variablen, die als **"extern"** deklarieren ein Objekt, das in einer anderen Übersetzungseinheit oder in einem einschließenden Bereich mit externer Verknüpfung definiert ist.

Deklaration von **const** Variablen mit dem **"extern"** -Speicherklasse erzwingt, dass die Variable an eine externe Bindung verfügen. Eine Initialisierung einer **Extern const** Variable ist in der definierenden Übersetzungseinheit zulässig. Initialisierungen in Übersetzungseinheiten, die keine definierenden Übersetzungseinheiten sind, erzeugen nicht definierte Ergebnisse. Weitere Informationen finden Sie unter [mithilfe von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)

Die [/Zc: externconstexpr](../build/reference/zc-externconstexpr.md) Compileroption veranlasst den Compiler anzuwendende [externe Verknüpfung](../c-language/external-linkage.md) Variablen deklariert, indem `extern constexpr`. In früheren Versionen von Visual Studio, und standardmäßig oder wenn **/Zc:externConstexpr-** angegeben ist, wird Visual Studio wendet internen Verknüpfung, **"constexpr"** Variablen auch dann, wenn die **"extern"** -Schlüsselwort wird verwendet. Die **/Zc: externconstexpr** Option ist verfügbar in Visual Studio 2017 Update 15.6 ab. und ist standardmäßig deaktiviert. / Zc: externconstexpr aktiviert der PERMISSIVE nicht.

Der folgende Code zeigt zwei **"extern"** Deklarationen `DefinedElsewhere` (die bezieht sich auf einen Namen, die in einer anderen Übersetzungseinheit definiert) und `DefinedHere` (die bezieht sich auf einen Namen in einem einschließenden Bereich definiert):

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

## <a name="thread_local"></a> Thread_local (C ++ 11)

Auf eine Variable, die mit dem `thread_local`-Bezeichner deklariert wird, kann nur in dem Thread, in dem sie erstellt wird, zugegriffen werden. Die Variable wird erstellt, wenn der Thread erstellt, und zerstört, wenn der Thread zerstört wird. Jeder Thread verfügt über eine eigene Kopie der Variable. Auf Windows `thread_local` ist funktionell gleichwertig mit der Microsoft-spezifische [__declspec (Thread)](../cpp/thread.md) Attribut.

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

Punkte zu beachten die `thread_local` Bezeichner:

- Dynamisch initialisierte Thread-lokalen Variablen in DLLs können für alle aufrufenden Threads nicht ordnungsgemäß initialisiert werden. Weitere Informationen finden Sie unter [Thread](thread.md).

- Die `thread_local` Bezeichner kann mit kombiniert werden **statische** oder **"extern"**.

- Sie können anwenden `thread_local` nur auf Datendeklarationen und-Definitionen; `thread_local` kann nicht für Funktionsdeklarationen oder-Definitionen verwendet werden.

- Sie können `thread_local` nur für Datenelemente mit statischer Speicherdauer angeben. Hierzu zählen globale Datenobjekte (sowohl **statische** und **"extern"**), lokale statische Objekte sowie statische Datenmember von Klassen. Jede lokale Variable deklariert `thread_local` ist implizit statisch, wenn keine anderen Speicherklasse angegeben wird; das heißt, im Blockbereich `thread_local` entspricht `thread_local static`.

- Sie müssen das `thread_local` für die Deklaration und Definition eines lokalen Threadobjekts angeben, egal ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.

Auf Windows `thread_local` ist funktionell gleichwertig mit [__declspec(thread)](../cpp/thread.md) mit dem Unterschied, dass **__declspec(thread)** kann auf eine Typdefinition angewendet werden und in C-Code gültig ist. Verwenden Sie nach Möglichkeit `thread_local`, da dies ein Teil des C++-Standards ist und daher besser zu potieren ist.

##  <a name="register"></a>  Registrieren

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): Die **registrieren** Schlüsselwort ist nicht mehr unterstützte Speicherklasse. Das Schlüsselwort ist immer noch in der Standard für die zukünftige Verwendung reserviert.

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

- Erstens werden `I1` und `I2` automatisch zerstört, wenn die Ablaufsteuerung den Block beendet, in dem sie definiert sind.

- Zweitens ist es in C++ nicht notwendig, Objekte oder Variablen am Anfang eines Blocks zu deklarieren. Außerdem werden diese Objekte nur initialisiert, wenn die Ablaufsteuerung deren Definitionen erreicht. (`I2` und `I3` sind Beispiele solcher Definitionen.) Die Ausgabe zeigt eindeutig, wann sie initialisiert werden.

- Des Weiteren behalten statische lokale Variablen wie `I3` ihre Werte für die Dauer des Programms bei, werden jedoch zerstört, sobald das Programm beendet wird.

## <a name="see-also"></a>Siehe auch

[Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)