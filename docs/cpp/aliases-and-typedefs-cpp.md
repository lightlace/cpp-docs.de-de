---
title: Aliase und Typedefs (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typedef_cpp
dev_langs:
- C++
ms.assetid: af1c24d2-4bfd-408a-acfc-482e264232f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c020d9fc4a8bc5275fe77b05eff74fdcec25ec6c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="aliases-and-typedefs-c"></a>Aliase und Typedefs (C++)
Sie können eine *Aliasdeklaration* , deklarieren einen Namen, die als ein Synonym für einen zuvor deklarierten Typ verwendet. (Dieser Mechanismus wird auch informell als bezeichnet eine *Typalias*). Sie können diesen Mechanismus auch verwenden, zum Erstellen einer *aliasvorlage*, die für benutzerdefinierte Zuweisungen besonders nützlich sein können.  
  
## <a name="syntax"></a>Syntax  
  
```  
using identifier = type;  
```  
  
## <a name="remarks"></a>Hinweise  
 `identifier`  
 Der Name des Alias.  
  
 `type`  
 Der Typbezeichner, für den Sie einen Alias erstellen.  
  
 Ein Alias führt keinen neuen Typ ein und kann die Bedeutung eines vorhandenen Typnamens nicht ändern.  
  
 Die einfachste Form eines Alias entspricht dem `typedef`-Mechanismus von C++03:  
  
```cpp  
// C++11  
using counter = long;  
  
// C++03 equivalent:  
// typedef long counter;  
```  
  
 Beides ermöglicht die Erstellung von Variablen des Typs "counter". Nützlicherer wäre ein Typalias wie dieser für `std::ios_base::fmtflags`:  
  
```cpp  
// C++11  
using fmtfl = std::ios_base::fmtflags;  
  
// C++03 equivalent:  
// typedef std::ios_base::fmtflags fmtfl;  
  
fmtfl fl_orig = std::cout.flags();  
fmtfl fl_hex = (fl_orig & ~std::cout.basefield) | std::cout.showbase | std::cout.hex;  
// ...  
std::cout.flags(fl_hex);  
```  
  
 Aliase auch mit Funktionszeigern arbeiten, aber viel besser lesbar als die entsprechende Typedef sind:  
  
```cpp  
// C++11  
using func = void(*)(int);  
  
// C++03 equivalent:  
// typedef void (*func)(int);  
  
// func can be assigned to a function pointer value  
void actual_function(int arg) { /* some code */ }  
func fptr = &actual_function;  
  
```  
  
 Eine Einschränkung des `typedef`-Mechanismus besteht darin, dass er nicht mit Vorlagen arbeitet. Die Typaliassyntax in C++11 ermöglicht jedoch die Erstellung von Aliasvorlagen:  
  
```cpp  
template<typename T> using ptr = T*;   
  
// the name 'ptr<T>' is now an alias for pointer to T  
ptr<int> ptr_int;  
  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Verwendung einer Aliasvorlage mit einer benutzerdefinierten Zuweisung, in diesem Fall einem ganzzahligen Vektortyp. Sie können jeden Typ für `int` ersetzen, um einen zweckmäßigen Alias zu erstellen, damit die komplexen Parameterlisten im Hauptfunktionscode ausgeblendet werden. Indem Sie die benutzerdefinierte Zuordnung im gesamten Code verwenden, können Sie die Lesbarkeit verbessern und das Risiko von Fehlern verringern, die sich aufgrund von Schreibfehlern einschleichen können.  
  
```cpp  
#include <stdlib.h>  
#include <new>  
  
template <typename T> struct MyAlloc {  
    typedef T value_type;  
  
    MyAlloc() { }  
    template <typename U> MyAlloc(const MyAlloc<U>&) { }  
  
    bool operator==(const MyAlloc&) const { return true; }  
    bool operator!=(const MyAlloc&) const { return false; }  
  
    T * allocate(const size_t n) const {  
        if (n == 0) {  
            return nullptr;  
        }  
  
        if (n > static_cast<size_t>(-1) / sizeof(T)) {  
            throw std::bad_array_new_length();  
        }  
  
        void * const pv = malloc(n * sizeof(T));  
  
        if (!pv) {  
            throw std::bad_alloc();  
        }  
  
        return static_cast<T *>(pv);  
    }  
  
    void deallocate(T * const p, size_t) const {  
        free(p);  
    }  
};  
  
#include <vector>  
using MyIntVector = std::vector<int, MyAlloc<int>>;  
  
#include <iostream>  
  
int main ()   
{  
    MyIntVector foov = { 1701, 1764, 1664 };  
  
    for (auto a: foov) std::cout << a << " ";  
    std::cout << "\n";  
  
    return 0;  
}  
```  
  
```Output  
1701 1764 1664  
```  
  
## <a name="typedefs"></a>Typedefs  
 Ein `typedef` -Deklaration erstellt einen Namen, der innerhalb des Bereichs liegen, ein Synonym für den Typ wird der *Typdeklaration* Teil der Deklaration.  
  
 Sie können typedef-Deklarationen verwenden, um kürzere oder aussagekräftigere Namen für Typen zu erstellen, die bereits von der Programmiersprache definiert sind, oder für Typen, die deklariert wurden. Mithilfe von typedef-Namen können Sie die Implementierungsdetails kapseln, die sich möglicherweise ändern.  
  
 Im Gegensatz zu den **Klasse**, `struct`, **Union**, und `enum` Deklarationen `typedef` -Deklarationen keine neue Typen – sie führen neue Namen für vorhandene Typen.  
  
 Mit `typedef` deklarierte Namen nehmen den gleichen Namespace ein wie andere Bezeichner (außer Anweisungsbezeichnungen). Deshalb können sie nicht den gleichen Bezeichner wie ein zuvor deklarierter Name verwenden. Nur in einer Klassentypdeklaration ist dies möglich. Betrachten Sie das folgende Beispiel:  
  
```  
// typedef_names1.cpp  
// C2377 expected  
typedef unsigned long UL;   // Declare a typedef name, UL.  
int UL;                     // C2377: redefined.  
```  
  
 Die Ausblendregeln für Namen, die andere Bezeichner betreffen, bestimmen außerdem die Sichtbarkeit von Namen, die mit `typedef` deklariert wurden. Deshalb ist das folgenden Beispiel in C++ zulässig:  
  
```  
// typedef_names2.cpp  
typedef unsigned long UL;   // Declare a typedef name, UL  
int main()  
{  
   unsigned int UL;   // Redeclaration hides typedef name  
}  
  
// typedef UL back in scope  
```  
 
  
```  
// typedef_specifier1.cpp  
typedef char FlagType;  
  
int main()  
{  
}  
  
void myproc( int )  
{  
    int FlagType;  
}  
```  
  
 Wenn ein Bezeichner für den lokalen Gültigkeitsbereich mit dem gleichen Namen wie eine typedef deklariert wird oder wenn ein Member einer Struktur oder Union im gleichen Gültigkeitsbereich oder im inneren Bereich deklariert wird, muss der Typspezifizierer angegeben werden. Zum Beispiel:  
  
```  
typedef char FlagType;  
const FlagType x;  
```  
  
 Um den `FlagType`-Namen für einen Bezeichner, einen Strukturmember oder einen Unionsmember wiederzuverwenden, muss der Typ angegeben werden:  
  
```  
const int FlagType;  // Type specifier required  
```  
  
 Folgendes ist nicht ausreichend:  
  
```  
const FlagType;      // Incomplete specification  
```  
  
 Das liegt daran, dass `FlagType` als ein Teil des Typs angesehen wird, und nicht als Bezeichner, der neu deklariert wird. Diese Deklaration wird als ungültige Deklaration angesehen, wie etwa  
  
```  
int;  // Illegal declaration   
```  
  
 Sie können einen beliebigen Typ mit typedef deklarieren, einschließlich Zeiger-, Funktions- und Arraytypen. Sie können einen typedef-Namen für einen Zeiger auf einen Struktur- oder einen Union-Typ deklarieren, bevor Sie den Struktur- oder Union-Typ definieren, solange die Definition die gleiche Sichtbarkeit wie die Deklaration aufweist.  
  
### <a name="examples"></a>Beispiele  
 `typedef`-Deklarationen können u. a. verwendet werden, um Deklarationen einheitlicher und komprimierter zu machen. Zum Beispiel:  
  
```cpp  
typedef char CHAR;          // Character type.  
typedef CHAR * PSTR;        // Pointer to a string (char *).  
PSTR strchr( PSTR source, CHAR target );  
typedef unsigned long ulong;  
ulong ul;     // Equivalent to "unsigned long ul;"  
```  
  
 Um mithilfe von `typedef` grundlegende und abgeleitete Typen in der gleichen Deklaration anzugeben, können Sie Deklaratoren durch Kommas voneinander trennen. Zum Beispiel:  
  
```  
typedef char CHAR, *PSTR;  
```  
  
 Im folgenden Beispiel wird der Typ `DRAWF` für eine Funktion bereitgestellt, die keinen Wert zurückgibt und zwei int-Argumente akzeptiert:  
  
```  
typedef void DRAWF( int, int );  
```  
  
 Nach der oben erwähnten `typedef`-Anweisung entspräche die Deklaration  
  
```  
DRAWF box;   
```  
  
 dieser Deklaration:  
  
```  
void box( int, int );  
```  
  
 `typedef` wird häufig mit `struct` kombiniert, um benutzerdefinierte Typen zu deklarieren und zu benennen:  
  
```cpp  
// typedef_specifier2.cpp  
#include <stdio.h>  
  
typedef struct mystructtag  
{  
    int   i;  
    double f;  
} mystruct;  
  
int main()  
{  
    mystruct ms;  
    ms.i = 10;  
    ms.f = 0.99;  
    printf_s("%d   %f\n", ms.i, ms.f);  
}  
```  
  
```Output  
10   0.990000  
```  
  
### <a name="re-declaration-of-typedefs"></a>Neudeklaration von Typdefinitionen  
 Die `typedef`-Deklaration kann verwendet werden, um denselben Namen erneut für den Verweis auf denselben Typ zu verwenden. Zum Beispiel:  
  
```cpp  
// FILE1.H  
typedef char CHAR;  
  
// FILE2.H  
typedef char CHAR;  
  
// PROG.CPP  
#include "file1.h"  
#include "file2.h"   // OK  
```  
  
 Das Programm PROG.CPP enthält zwei Headerdateien, die beide `typedef`-Deklarationen für den Namen `CHAR` enthalten. Solange die beiden Deklarationen auf denselben Typ verweisen, ist eine solche Neudeklaration zulässig.  
  
 Ein `typedef` kann einen Namen nicht neu definieren, der zuvor als anderer Typ deklariert wurde. Enthält FILE2.H also  
  
```cpp  
// FILE2.H  
typedef int CHAR;     // Error  
```  
  
 , gibt der Compiler aufgrund des Versuchs, den Namen `CHAR` erneut zu deklarieren, um auf einen anderen Typ zu verweisen, einen Fehler aus. Dies erstreckt sich auf Konstrukte wie die Folgenden:  
  
```cpp  
typedef char CHAR;  
typedef CHAR CHAR;      // OK: redeclared as same type  
  
typedef union REGS      // OK: name REGS redeclared  
{                       //  by typedef name with the  
    struct wordregs x;  //  same meaning.  
    struct byteregs h;  
} REGS;  
```  
  
### <a name="typedefs-in-c-vs-c"></a>Typedefs in C++ vs. C  
 Die Verwendung des `typedef`-Spezifizierers mit Klassentypen wird größtenteils aufgrund der ANSI C-Praxis des Deklarierens unbenannter Strukturen in `typedef`-Deklarationen unterstützt. Zum Beispiel verwenden viele C-Programmierer Folgendes:  
  
```cpp  
// typedef_with_class_types1.cpp  
// compile with: /c  
typedef struct {   // Declare an unnamed structure and give it the  
                   // typedef name POINT.  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 Der Vorteil einer solchen Deklaration ist, das Deklarationen wie folgt ermöglicht werden:  
  
```  
POINT ptOrigin;  
```  
  
 Anstelle von:  
  
```  
struct point_t ptOrigin;  
```  
  
 In C++ ist der Unterschied zwischen `typedef` -Namen und realen Typen (deklariert mit den **Klasse**, `struct`, **Union**, und `enum` Schlüsselwörter) klarer. Obwohl die gängige C-Praxis des Deklarierens einer namenlosen Struktur in einer `typedef`-Anweisung weiterhin funktioniert, bietet dies keine Notationsvorteile, wie in C.  
  
```cpp  
// typedef_with_class_types2.cpp  
// compile with: /c /W1  
typedef struct {  
   int POINT();  
   unsigned x;  
   unsigned y;  
} POINT;  
```  
  
 Das vorhergehende Beispiel deklariert eine Klasse namens `POINT` mit der unbenannten Klassensyntax `typedef`. `POINT` wird als Klassenname behandelt. Es gelten jedoch folgende Einschränkungen für Namen, die auf diese Weise eingeführt werden:  
  
-   Der Name (das Synonym) kann nicht angezeigt, nachdem eine **Klasse**, `struct`, oder **Union** Präfix.  
  
-   Der Name darf nicht als Konstruktor- oder Destruktorname innerhalb einer Klassendeklaration verwendet werden.  
  
 Zusammenfassend stellt diese Syntax keinen Mechanismus für die Vererbung, Konstruktion oder Löschung bereit.  
