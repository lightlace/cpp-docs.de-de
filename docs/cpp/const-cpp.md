---
title: "const (C++)"
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
  - "const_cpp"
  - "const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const-Schlüsselwort [C++]"
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# const (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn eine Datendeklaration geändert wird, gibt das **const**\-Schlüsselwort an, dass das Objekt oder die Variable nicht änderbar ist.  
  
## Syntax  
  
```  
  
        const declaration ;  
member-function const ;  
```  
  
## Konstante Werte  
 Das **const**\-Schlüsselwort gibt an, dass der Wert einer Variablen konstant ist, und weist den Compiler an, eine Änderung des Werts durch den Programmierer zu verhindern.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 In C\+\+ können Sie das **const**\-Schlüsselwort anstelle der [\#define](../preprocessor/hash-define-directive-c-cpp.md)\-Präprozessordirektiven verwenden, um konstante Werte zu definieren.  Werte, die mit **const** definiert werden, unterliegen der Typüberprüfung und können anstelle von konstanten Ausdrücken verwendet werden.  In C\+\+ können Sie die Größe eines Arrays mit einer **const**\-Variablen angeben:  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 In C erhalten konstante Werte standardmäßig den Wert einer externen Bindung. Daher können sie nur in den Quelldateien stehen.  In C\+\+ erhalten konstante Werte standardmäßig den Wert einer internen Bindung, daher können sie in den Headerdateien angezeigt werden.  
  
 Das **const**\-Schlüsselwort kann auch in Zeigerdeklarationen verwendet werden.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Ein Zeiger auf eine Variable, die als **const** deklariert ist, kann nur einem Zeiger zugewiesen werden, der auch als **const** deklariert ist.  
  
```  
// constant_values4.cpp  
#include <stdio.h>  
int main() {  
   const char *mybuf = "test";  
   char *yourbuf = "test2";  
   printf_s("%s\n", mybuf);  
  
   const char *bptr = mybuf;   // Pointer to constant data  
   printf_s("%s\n", bptr);  
  
   // *bptr = 'a';   // Error  
}  
```  
  
 Sie können Zeiger auf konstante Daten als Funktionsparameter verwenden, um zu verhindern, dass die Funktion einen Parameter ändert, der über einen Zeiger übergeben wird.  
  
 Für Objekte, die als **const** deklariert sind, können Sie nur [konstante Memberfunktionen](../misc/constant-member-functions.md) aufrufen.  Dadurch wird sichergestellt, dass das konstante Objekt nie geändert wird.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Sie können für ein nicht konstantes Objekt konstante oder nicht konstante Memberfunktionen aufrufen.  Zudem können Sie eine Memberfunktion mit dem **const**\-Schlüsselwort überladen. Dadurch kann für konstante und nicht konstante Objekte jeweils eine andere Version der Funktion aufgerufen werden.  
  
 Sie können Konstruktoren oder Destruktoren nicht mit dem **const**\-Schlüsselwort deklarieren.  
  
## Konstante Memberfunktionen  
 Die Deklaration einer Memberfunktion mit dem **const**\-Schlüsselwort gibt an, dass die Funktion eine "schreibgeschützte" Funktion ist, die das Objekt, für das sie aufgerufen wird, nicht ändert.  Eine konstante Memberfunktion kann keine nicht statischen Datenmember ändern oder Memberfunktionen aufrufen, die nicht als konstant betrachtet werden. Setzen Sie das **const**\-Schlüsselwort hinter die schließende Klammer der Argumentliste, um eine konstante Memberfunktion zu deklarieren.  Das **const**\-Schlüsselwort ist in der Deklaration und in der Definition erforderlich.  
  
```  
// constant_member_function.cpp  
class Date  
{  
public:  
   Date( int mn, int dy, int yr );  
   int getMonth() const;     // A read-only function  
   void setMonth( int mn );   // A write function; can't be const  
private:  
   int month;  
};  
  
int Date::getMonth() const  
{  
   return month;        // Doesn't modify anything  
}  
void Date::setMonth( int mn )  
{  
   month = mn;          // Modifies data member  
}  
int main()  
{  
   Date MyDate( 7, 4, 1998 );  
   const Date BirthDate( 1, 18, 1953 );  
   MyDate.setMonth( 4 );    // Okay  
   BirthDate.getMonth();    // Okay  
   BirthDate.setMonth( 4 ); // C2662 Error  
}  
```  
  
## Unterschiede bei const in C und C\+\+  
 Wenn Sie eine Variable in einer C\-Quellcodedatei als **const** deklarieren, gehen Sie wie folgt vor:  
  
```  
const int i = 2;  
```  
  
 Sie können diese Variable dann in einem anderen Modul wie folgt verwenden:  
  
```  
extern const int i;  
```  
  
 Um jedoch das gleiche Verhalten in C\+\+ abzurufen, müssen Sie die **const**\-Variable als deklarieren:  
  
```  
extern const int i = 2;  
```  
  
 Wenn Sie eine `extern`\-Variable in einer C\+\+\-Quellcodedatei für die Verwendung in einer C\-Quellcodedatei deklarieren möchten, verwenden Sie:  
  
```  
extern "C" const int x=10;  
```  
  
 um die Namenszerlegung durch den C\+\+\-Compiler zu verhindern.  
  
## Hinweise  
 Wenn das **const**\-Schlüsselwort auf die Parameterliste einer Memberfunktion folgt, gibt es an, dass die Funktion das Objekt nicht ändert, für das sie aufgerufen wird.  
  
 Weitere Informationen zu **const** finden Sie in den folgenden Themen:  
  
-   [Konstante Werte](../misc/constant-values.md)  
  
-   [Konstante Memberfunktionen](../misc/constant-member-functions.md)  
  
-   [const\- und volatile\-Zeiger](../cpp/const-and-volatile-pointers.md)  
  
-   [Typqualifizierer \(C\-Programmiersprachenreferenz\)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [\#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)