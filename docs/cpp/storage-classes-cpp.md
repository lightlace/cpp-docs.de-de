---
title: "Speicherklassen (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "thread_local_cpp"
  - "external_cpp"
  - "static_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Speicherklassen, Grundlegende Konzepte"
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherklassen (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine *Speicherklasse* im Kontext von C\+\+\-Variablendeklarationen ist ein Typbezeichner, der Lebensdauer, Bindung und Speicherort von Objekten steuert.  Ein angegebenes Objekt kann nur eine Speicherklasse haben.  Variablen, die innerhalb eines Blocks definiert sind, haben automatischen Speicher, wenn nicht anders mithilfe der Bezeichner `extern`, `static` oder `thread_local` angegeben.  Automatische Objekte und Variablen haben keine Bindung; sie sind für Code außerhalb des Blocks nicht sichtbar.  
  
 **Notizen**  
  
1.  Das Schlüsselwort [mutable](../cpp/mutable-data-members-cpp.md) kann als Speicherklassenspezifizierer angesehen werden.  Es ist jedoch nur in der Memberliste einer Klassendefinition verfügbar.  
  
2.  Ab [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] ist das `auto`\-Schlüsselwort kein C\+\+\-Speicherklassenspezifizierer mehr, und das `register`\-Schlüsselwort ist veraltet.  
  
-   [Static](#static)  
  
-   [extern](#extern)  
  
-   [thread\_local](#thread_local)  
  
## statisch  
 Das `static`\-Schlüsselwort kann zum Deklarieren von Variablen und Funktionen im globalen Gültigkeitsbereich, Namespace\-Gültigkeitsbereich und Klassengültigkeitsbereich verwendet werden.  Statische Variablen können auch im lokalen Gültigkeitsbereich deklariert werden.  
  
 Statische Dauer bedeutet, dass das Objekt oder die Variable zugewiesen wird, wenn das Programm gestartet wird. Die Zuweisung wird wieder aufgehoben, wenn das Programm beendet wird.  Externe Verknüpfung bedeutet, dass der Name der Variablen von außerhalb der Datei sichtbar ist, in der die Variable deklariert wird.  Umgekehrt bedeutet interne Verknüpfung, dass der Name nicht außerhalb der Datei sichtbar ist, in der die Variable deklariert wird.  Standardmäßig verfügt ein Objekt oder eine Variable, das bzw. die im globalen Namespace definiert wird, über eine statische Dauer und externe Verknüpfung.  Das `static`\-Schlüsselwort kann in folgenden Situationen verwendet werden:  
  
1.  Wenn Sie eine Variable oder eine Funktion im Dateibereich \(globaler und\/oder Namespacebereich\) deklarieren, gibt das `static`\-Schlüsselwort die Variable oder Funktion mit interner Verknüpfung an.  Wenn Sie eine Variable deklarieren, hat die Variable eine statische Dauer und wird vom Compiler mit dem Wert 0 initialisiert, solange Sie keinen anderen Wert angeben.  
  
2.  Wenn Sie eine Variable in einer Funktion deklarieren, gibt das `static`\-Schlüsselwort an, dass die Variable ihren Status zwischen den Aufrufen der Funktion beibehält.  
  
3.  Wenn Sie einen Datenmember in einer Klassendeklaration deklarieren, gibt das `static`\-Schlüsselwort an, dass eine Kopie des Members für alle Instanzen der Klasse freigegeben wird.  Ein statischer Datenmember muss im Dateibereich definiert sein.  Ein ganzzahliger Datenmember, den Sie als `const` `static` deklarieren, kann einen Initialisierer haben.  
  
4.  Wenn Sie eine Memberfunktion in einer Klassendeklaration deklarieren, gibt das `static`\-Schlüsselwort an, dass die Funktion für alle Instanzen der Klasse freigegeben wird.  Eine statische Memberfunktion kann nicht auf einen Instanzmember zugreifen, weil die Funktion keinen impliziten `this` Zeiger aufweist.  Um auf einen Instanzmember zuzugreifen, deklarieren Sie die Funktion mit einem Parameter, der ein Instanzzeiger oder \-verweis ist.  
  
5.  Sie können die Member einer Union nicht als statisch deklarieren.  Allerdings muss eine global deklarierte anonyme Union explizit als `static` deklariert werden.  
  
 Das folgende Beispiel zeigt, wie eine als `static` deklarierte Variable in einer Funktion ihren Status zwischen den Aufrufen der Funktion beibehält.  
  
```  
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
  
  **nStatic is 0**  
**nStatic is 1**  
**nStatic is 3**  
**nStatic is 6**  
**nStatic is 10** Im folgenden Beispiel wird die Verwendung von `static` in einer Klasse gezeigt.  
  
```  
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
  
  **0**  
**0**  
**1**  
**1**  
**2**  
**2**  
**3**  
**3** Das folgende Beispiel zeigt eine lokale als `static` deklarierte Variable in einer Memberfunktion.  Die statische Variable ist im gesamten Programm verfügbar. Alle Instanzen des Typs verwenden dieselbe Kopie der statischen Variable.  
  
```  
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
  
  **var \!\= value**  
**var \=\= value** Ab C\+\+11 ist eine statische lokale Variableninitialisierung auf jeden Fall threadsicher.  Dieses Feature wird auch als *magic Statics* bezeichnet.  Allerdings müssen alle nachfolgende Zuweisungen in einer Multithreadanwendung synchronisiert werden.  Die Funktion für threadsichere statische Variablen kann mithilfe des Flags "\/Zc:threadSafeInit\-" deaktiviert werden, um eine Abhängigkeit vom CRT zu vermeiden.  
  
## extern  
 Objekte und Variablen, die als `extern` deklariert werden, deklarieren ein Objekt, das in einer anderen Übersetzungseinheit oder in einem einschließenden Bereich mit externer Verknüpfung definiert ist.  
  
 Die Deklaration von **const**\-Variablen mit der `extern`\-Speicherklasse erzwingt eine externe Bindung für die Variable.  Eine Initialisierung einer **extern const**\-Variable ist in der definierenden Übersetzungseinheit zulässig.  Initialisierungen in Übersetzungseinheiten, die keine definierenden Übersetzungseinheiten sind, erzeugen nicht definierte Ergebnisse.  Weitere Informationen finden Sie unter [Verwenden von "extern" zur Angabe der Verknüpfung](../cpp/using-extern-to-specify-linkage.md)  
  
 Der folgende Code zeigt zwei `extern`\-Deklarationen, `DefinedElsewhere` \(die sich auf einen Namen bezieht, der in einer anderen Übersetzungseinheit definiert wurde\) und `DefinedHere` \(die sich auf einen Namen bezieht, der in einem einschließenden Bereich definiert wurde\):  
  
```  
// external.cpp  
// defined in another translation unit  
extern int DefinedElsewhere;     
int main() {  
   int DefinedHere;   
   {  
      // refers to DefinedHere in the enclosing scope  
      extern int DefinedHere;  
    }  
}  
```  
  
## thread\_local \(C\+\+11\)  
 Auf eine Variable, die mit dem `thread_local`\-Bezeichner deklariert wird, kann nur in dem Thread, in dem sie erstellt wird, zugegriffen werden.  Die Variable wird erstellt, wenn der Thread erstellt, und gelöscht, wenn der Thread gelöscht wird.  Jeder Thread verfügt über eine eigene Kopie der Variable.  Unter Windows ist `thread_local` funktionell gleichwertig mit dem Microsoft\-spezifischen [\_\_declspec\(thread\)](../cpp/thread.md)\-Attribut.  
  
```  
thread_local float f = 42.0; //global namespace  
  
struct C // cannot be applied to type definition  
{  
thread_local int i; //local  
thread_local static char buf[10]; // local and static  
};  
  
void DoSomething()  
{  
thread_local C my_struct; // Apply  thread_local to a variable  
}  
```  
  
1.  Der thread\_local\-Bezeichner kann mit `static` oder `extern` kombiniert werden.  
  
2.  Sie können `thread_local` nur auf Datendeklarationen und \-Definitionen anwenden; **thread\_local** kann nicht für Funktionsdeklarationen oder \-Definitionen verwendet werden.  
  
3.  Die Verwendung von`thread_local` kann mit dem [verzögerten Laden](../build/reference/linker-support-for-delay-loaded-dlls.md) von DLL\-Importen in Konflikt treten**.**  
  
4.  Auf XP\-Systemen funktioniert `thread_local` möglicherweise nicht ordnungsgemäß, wenn eine DLL `thread_local`\-Daten verwendet und dynamisch über LoadLibrary geladen wird.  
  
5.  Sie können `thread_local` nur für Datenelemente mit statischer Speicherdauer angeben.  Hierzu zählen globale Datenobjekte \(sowohl **static** als auch `extern`\), lokale statische Objekte sowie statische Datenmember von Klassen.  Sie können automatische Datenobjekte nicht mit **thread\_local** deklarieren.  
  
6.  Sie müssen das `thread_local` für die Deklaration und Definition eines lokalen Threadobjekts angeben, egal ob die Deklaration und Definition in der gleichen Datei oder in separaten Dateien auftreten.  
  
 Unter Windows ist `thread_local` funktionell gleichwertig mit  [\_\_declspec\(thread\)](../cpp/thread.md), außer dass \_\_declspec\(thread\) auf eine Typdefinition angewendet werden kann und im C\-Code gültig ist.  Verwenden Sie nach Möglichkeit `thread_local`, da dies ein Teil des C\+\+\-Standards ist und daher besser zu potieren ist.  
  
 Weitere Informationen finden Sie unter [Lokaler Threadspeicher \(TLS\)](../parallel/thread-local-storage-tls.md).  
  
## register  
 In C\+\+11 ist das **register**\-Schlüsselwort veraltet.  Es gibt an, dass die Variable nach Möglichkeit auf einem Computerregister gespeichert werden soll.  Es können nur Funktionsargumente und lokale Variablen mit der Registerspeicherklasse deklariert werden.  
  
```  
register int num;  
```  
  
 Wie automatische Variablen werden Registervariablen nur bis zum Ende des Blocks beibehalten, in dem sie deklariert werden.  
  
 Der Compiler berücksichtigt keine Benutzeranforderungen für Registervariablen. Stattdessen trifft er selbst die Registerauswahl, wenn globale Optimierungen aktiviert sind.  Jede andere Semantik, die dem [register](assetId:///5b66905a-2f7f-4918-bb55-5e66d4bc50f9)\-Schlüsselwort zugeordnet ist, wird jedoch vom Compiler berücksichtigt.  
  
 Wenn der address\-of\-Operator \(**&**\) für ein Objekt verwendet wird, das mit "register" deklariert wird, muss der Compiler das Objekt im Arbeitsspeicher anstelle eines Registers ablegen.  
  
## Beispiel: automatische im Vergleich zurstatischen Initialisierung  
 Ein lokales automatisches Objekt oder eine lokale automatische Variable wird jedes Mal initialisiert, wenn die Ablaufsteuerung ihre Definition erreicht.  Ein lokales automatisches Objekt oder eine lokale automatische Variable wird erstmalig initialisiert, wenn die Ablaufsteuerung ihre Definition erreicht.  
  
 Betrachten Sie das folgende Beispiel, in dem eine Klasse definiert wird, die die Initialisierung und Beschädigung von Objekten protokolliert und dann drei Objekte, `I1`, `I2` und `I3`, definiert:  
  
```  
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
   if( szWhat != 0 && strlen( szWhat ) > 0 ) {  
      // Allocate storage for szObjName, then copy  
      // initializer szWhat into szObjName, using  
      // secured CRT functions.  
      sizeofObjName = strlen( szWhat ) + 1;  
  
      szObjName = new char[ sizeofObjName ];  
      strcpy_s( szObjName, sizeofObjName, szWhat );  
  
      cout << "Initializing: " << szObjName << "\n";  
   }  
   else  
      szObjName = 0;  
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
  
  **Initializing: Auto I1**  
**In block.  Initializing: Auto I2**  
**Initializing: Static I3**  
**Destroying: Auto I2**  
**Exited block.  Destroying: Auto I1**  
**Destroying: Static I3**  Der vorhergehende Code zeigt, wie und wann die Objekte `I1`, `I2` und `I3` initialisiert und beschädigt werden.  
  
 In Bezug auf das Programm sind einige Punkte zu beachten.  
  
 Erstens werden `I1` und `I2` automatisch beschädigt, wenn die Ablaufsteuerung den Block beendet, in dem sie definiert sind.  
  
 Zweitens ist es in C\+\+ nicht notwendig, Objekte oder Variablen am Anfang eines Blocks zu deklarieren.  Außerdem werden diese Objekte nur initialisiert, wenn die Ablaufsteuerung deren Definitionen erreicht.  \(`I2` und `I3` sind Beispiele solcher Definitionen.\) Die Ausgabe zeigt eindeutig, wann sie initialisiert werden.  
  
 Des Weiteren behalten statische lokale Variablen wie `I3` ihre Werte für die Dauer des Programms bei, werden jedoch beschädigt, sobald das Programm beendet wird.  
  
## Siehe auch  
 [Deklarationen und Definitionen](../cpp/declarations-and-definitions-cpp.md)