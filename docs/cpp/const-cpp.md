---
title: Const (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- const_cpp
dev_langs:
- C++
helpviewer_keywords:
- const keyword [C++]
ms.assetid: b21c0271-1ad0-40a0-b21c-5e812bba0318
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8a6a238f28ec8f84cd127b4af88a84edb26506ee
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="const-c"></a>const (C++)
Wenn eine Datendeklaration der **const** -Schlüsselwort Gibt an, dass das Objekt oder die Variable nicht änderbar ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      const declaration ;  
member-function const ;  
```  
  
## <a name="const-values"></a>Konstante Werte  
 Die **const** -Schlüsselwort Gibt an, dass der Wert einer Variablen konstant ist und dem Compiler teilt, um zu verhindern, dass den Programmierer diese zu ändern.  
  
```  
// constant_values1.cpp  
int main() {  
   const int i = 5;  
   i = 10;   // C3892  
   i++;   // C2105  
}  
```  
  
 In C++ können Sie die **const** -Schlüsselwort anstelle der [#define](../preprocessor/hash-define-directive-c-cpp.md) -Präprozessordirektive zum Definieren von konstanter Werten. Werte, die mit definierten **const** unterliegen der typüberprüfung und können anstelle von Konstanten Ausdrücken verwendet werden. In C++ können Sie angeben, die Größe eines Arrays mit einem **const** Variablen wie folgt:  
  
```  
// constant_values2.cpp  
// compile with: /c  
const int maxarray = 255;  
char store_char[maxarray];  // allowed in C++; not allowed in C  
```  
  
 In C erhalten konstante Werte standardmäßig den Wert einer externen Bindung. Daher können sie nur in den Quelldateien stehen. In C++ erhalten konstante Werte standardmäßig den Wert einer internen Bindung, daher können sie in den Headerdateien angezeigt werden.  
  
 Die **const** -Schlüsselwort kann auch in Zeigerdeklarationen verwendet werden.  
  
```  
// constant_values3.cpp  
int main() {  
   char *mybuf = 0, *yourbuf;  
   char *const aptr = mybuf;  
   *aptr = 'a';   // OK  
   aptr = yourbuf;   // C3892  
}  
```  
  
 Ein Zeiger auf eine Variable als **const** zugewiesen werden können, nur in einen Zeiger, der auch als deklariert ist **const**.  
  
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
  
 Für Objekte, die als deklariert werden **const**, Sie können nur Konstante Memberfunktionen aufrufen. Dadurch wird sichergestellt, dass das konstante Objekt nie geändert wird.  
  
```  
birthday.getMonth();    // Okay  
birthday.setMonth( 4 ); // Error  
```  
  
 Sie können für ein nicht konstantes Objekt konstante oder nicht konstante Memberfunktionen aufrufen. Sie können auch überladen, eine Memberfunktion mit der **const** Schlüsselwort; Dadurch wird eine andere Version der Funktion für Konstante und nicht Konstante Objekte aufgerufen werden.  
  
 Sie können keine Konstruktoren oder Destruktoren mit deklarieren die **const** Schlüsselwort.  
  
## <a name="const-member-functions"></a>Konstante Memberfunktionen  
 Deklaration einer Memberfunktion mit dem **const** Schlüsselwort Gibt an, dass die Funktion "schreibgeschützt"-Funktion, die nicht das Objekt verändert wird für den sie aufgerufen wird. Eine Konstante Memberfunktion kann nicht keine nicht statischen Datenmember ändern oder Memberfunktionen, die Konstanten werden nicht aufrufen. Um eine Konstante Memberfunktion zu deklarieren, setzen die **const** -Schlüsselwort hinter die schließende Klammer der Argumentliste. Die **const** Schlüsselwort ist in der Deklaration und Definition erforderlich.  
  
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
  
## <a name="c-and-c-const-differences"></a>Unterschiede bei const in C und C++  
 Wenn Sie eine Variable als deklarieren **const** in einer C#-Quellcodedatei, gehen Sie wie:  
  
```  
const int i = 2;  
```  
  
 Sie können diese Variable dann in einem anderen Modul wie folgt verwenden:  
  
```  
extern const int i;  
```  
  
 Um das gleiche Verhalten in C++ abzurufen, müssen Sie deklarieren, aber Ihre **const** -Variable als:  
  
```  
extern const int i = 2;  
```  
  
 Wenn Sie eine `extern`-Variable in einer C++-Quellcodedatei für die Verwendung in einer C-Quellcodedatei deklarieren möchten, verwenden Sie:  
  
```  
extern "C" const int x=10;  
```  
  
 um die Namenszerlegung durch den C++-Compiler zu verhindern.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Parameterliste einer Memberfunktion, befolgen die **const** -Schlüsselwort Gibt an, dass die Funktion nicht das Objekt ändert, für die er aufgerufen wird.  
  
 Weitere Informationen zu **const**, finden Sie unter den folgenden Themen:  
    
-   [const- und volatile-Zeiger](../cpp/const-and-volatile-pointers.md)  
  
-   [Typqualifizierer (C-Programmiersprachenreferenz)](../c-language/type-qualifiers.md)  
  
-   [volatile](../cpp/volatile-cpp.md)  
  
-   [#define](../preprocessor/hash-define-directive-c-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)
