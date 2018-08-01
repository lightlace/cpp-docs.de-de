---
title: Const (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- const_cpp
dev_langs:
- C++
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73e030ede8305db4ea05826f0ce7704420ac0400
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403400"
---
# <a name="const-c"></a>const (C++)
Wenn eine Datendeklaration der **const** -Schlüsselwort Gibt an, dass das Objekt oder die Variable nicht geändert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
const declaration ;  
member-function const ;  
```  
  
## <a name="const-values"></a>Konstante Werte  
 Die **const** -Schlüsselwort Gibt an, dass der Wert einer Variablen konstant ist und weist den Compiler an, um zu verhindern, dass den Programmierer diese zu ändern.  
  
```cpp 
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 In C++ können Sie die **const** -Schlüsselwort anstelle von der [#define](../preprocessor/hash-define-directive-c-cpp.md) Präprozessordirektive zum Definieren von konstanter Werten. Mit definierten Werte **const** unterliegen der typüberprüfung und können anstelle von Konstanten Ausdrücken verwendet werden. In C++ können Sie angeben, die Größe eines Arrays mit einem **const** Variable wie folgt:  
  
```cpp 
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 In C erhalten konstante Werte standardmäßig den Wert einer externen Bindung. Daher können sie nur in den Quelldateien stehen. In C++ erhalten konstante Werte standardmäßig den Wert einer internen Bindung, daher können sie in den Headerdateien angezeigt werden.  
  
 Die **const** -Schlüsselwort kann auch in Zeigerdeklarationen verwendet werden.  
  
```cpp 
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Ein Zeiger auf eine Variable, die als **const** zugewiesen werden können, nur auf einen Zeiger, der auch als deklariert wird **const**.  
  
```cpp 
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
  
 Für Objekte, die als deklariert sind **const**, Sie können nur Konstante Memberfunktionen aufrufen. Dadurch wird sichergestellt, dass das konstante Objekt nie geändert wird.  
  
```cpp 
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Sie können für ein nicht konstantes Objekt konstante oder nicht konstante Memberfunktionen aufrufen. Sie können auch überladen, eine Memberfunktion mit der **const** Schlüsselwort; Dadurch wird eine andere Version der Funktion, die für Konstanten und nicht Konstante Objekte aufgerufen werden.  
  
 Sie können keine Konstruktoren oder Destruktoren mit deklarieren die **const** Schlüsselwort.  
  
## <a name="const-member-functions"></a>Konstante Memberfunktionen  
 Deklariert eine Memberfunktion mit dem **const** Schlüsselwort Gibt an, dass die Funktion eine Funktion "Read-only", die nicht mit das Objekt ändert, für das es aufgerufen wird. Eine Konstante Memberfunktion kann nicht keine nicht statischen Datenmember ändern oder Memberfunktionen aufrufen, die nicht konstant sind. Um eine Konstante Memberfunktion zu deklarieren, platzieren Sie die **const** Schlüsselwort nach der schließenden Klammer der Argumentliste. Die **const** Schlüsselwort ist in der Deklaration und Definition erforderlich.  
  
```cpp 
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
  
## <a name="c-and-c-const-differences"></a>Unterschiede bei const in C und C++  
 Wenn Sie eine Variable deklarieren **const** in einem C-Quellcodedatei Sie dies als:  
  
```cpp 
const int i = 2;  
```  
  
 Sie können diese Variable dann in einem anderen Modul wie folgt verwenden:  
  
```cpp 
extern const int i;  
```  
  
 Um das gleiche Verhalten in C++ zu erhalten, müssen Sie deklarieren, aber Ihre **const** als Variable:  
  
```cpp 
extern const int i = 2;  
```  
  
 Wenn Sie, deklarieren möchten einen **"extern"** -Variable in eine C++-Quellcodedatei für die Verwendung in einer C Quellcodedatei verwenden:  
  
```cpp 
extern "C" const int x=10;  
```  
  
 um die Namenszerlegung durch den C++-Compiler zu verhindern.  
  
## <a name="remarks"></a>Hinweise  
 Beim Befolgen der Parameterliste einer Memberfunktion, die **const** -Schlüsselwort Gibt an, dass die Funktion nicht das Objekt ändert, für das es aufgerufen wird.  
  
 Weitere Informationen zu **const**, finden Sie unter den folgenden Themen:  
    
-   [const- und volatile-Zeiger](../cpp/const-and-volatile-pointers.md)  
  
-   [Typqualifizierer (C-Programmiersprachenreferenz)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)