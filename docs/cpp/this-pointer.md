---
title: "this-Zeiger | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "this"
  - "this_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nicht statische Memberfunktionen"
  - "Zeiger, Auf Klasseninstanzen"
  - "This-Zeiger"
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# this-Zeiger
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der **this**\-Zeiger ist ein Zeiger, auf den nur in nicht statischen Memberfunktionen des Typs **class**, `struct` oder **union** zugegriffen werden kann.  Er zeigt auf das Objekt, für das die Memberfunktion aufgerufen wird.  Statische Memberfunktionen haben keinen **this**\-Zeiger.  
  
## Syntax  
  
```  
  
        this   
this->member-identifier  
```  
  
## Hinweise  
 Der **this**\-Zeiger eines Objekts ist nicht Teil des Objekts selbst. Er wird nicht im Ergebnis einer `sizeof`\-Anweisung für das Objekt wiedergegeben.  Wenn stattdessen eine nicht statische Memberfunktion für ein Objekt aufgerufen wird, wird die Adresse des Objekts vom Compiler als ausgeblendetes Argument an die Funktion übergeben.  Folgender Funktionsaufruf kann beispielsweise:  
  
```  
myDate.setMonth( 3 );  
```  
  
 auf diese Weise interpretiert werden:  
  
```  
setMonth( &myDate, 3 );  
```  
  
 Die Adresse des Objekts ist von innerhalb der Memberfunktion als **this**\-Zeiger verfügbar.  Die meisten Verwendungen von **this** sind implizit.  Es ist zulässig, wenn auch unnötig, **this** explizit für den Verweis auf Member der Klasse zu verwenden.  Zum Beispiel:  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 Der Ausdruck `*this` wird häufig verwendet, um das aktuelle Objekt aus einer Memberfunktion zurückzugeben:  
  
```  
return *this;  
```  
  
 Der **this**\-Zeiger wird auch verwendet, um vor Selbstverweisen zu schützen:  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  Da der **this**\-Zeiger nicht veränderbar ist, sind Zuweisungen zu **this** nicht zulässig.  Frühere Implementierungen von C\+\+ lassen Zuweisungen zu **this** zu.  
  
 Gelegentlich wird der **this**\-Zeiger direkt verwendet, beispielsweise um auf sich selbst verweisende Datenstrukturen zu bearbeiten, für welche die Adresse des aktuellen Objekts erforderlich ist.  
  
## Beispiel  
  
```  
// this_pointer.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
class Buf   
{  
public:  
    Buf( char* szBuffer, size_t sizeOfBuffer );  
    Buf& operator=( const Buf & );  
    void Display() { cout << buffer << endl; }  
  
private:  
    char*   buffer;  
    size_t  sizeOfBuffer;  
};  
  
Buf::Buf( char* szBuffer, size_t sizeOfBuffer )  
{  
    sizeOfBuffer++; // account for a NULL terminator  
  
    buffer = new char[ sizeOfBuffer ];  
    if (buffer)  
    {  
        strcpy_s( buffer, sizeOfBuffer, szBuffer );  
        sizeOfBuffer = sizeOfBuffer;  
    }  
}  
  
Buf& Buf::operator=( const Buf &otherbuf )   
{  
    if( &otherbuf != this )   
    {  
        if (buffer)  
            delete [] buffer;  
  
        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;   
        buffer = new char[sizeOfBuffer];  
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );  
    }  
    return *this;  
}  
  
int main()  
{  
    Buf myBuf( "my buffer", 10 );  
    Buf yourBuf( "your buffer", 12 );  
  
    // Display 'my buffer'  
    myBuf.Display();  
  
    // assignment opperator  
    myBuf = yourBuf;  
  
    // Display 'your buffer'  
    myBuf.Display();  
}  
```  
  
  **my buffer**  
**your buffer**   
## Typ des this\-Zeigers.  
 Der Typ des **this**\-Zeigers kann in der Funktionsdeklaration durch die **const**\- und `volatile`\-Schlüsselwörter geändert werden.  Um eine Funktion so zu deklarieren, dass sie die Attribute von mindestens einem dieser Schlüsselwörter hat, fügen Sie die Schlüsselwörter nach der Funktionsargumentliste hinzu.  
  
 Betrachten Sie das folgende Beispiel:  
  
```  
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Der vorangehende Code deklariert eine Memberfunktion, `X`, in der der **this**\-Zeiger als **const**\-Zeiger auf ein **const**\-Objekt behandelt wird.  Kombinationen von *cv\-mod\-list*\-Optionen können verwendet werden, sie ändern jedoch immer das Objekt, auf das von **this** gezeigt wird, nicht den **this**\-Zeiger selbst.  Daher deklariert die folgende Deklaration die Funktion `X`; der **this**\-Zeiger ist ein **const**\-Zeiger auf ein **const**\-Objekt:  
  
```  
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Der Typ von **this** in einer Memberfunktion wird durch die folgende Syntax beschrieben, wobei *cv\-qualifier\-list* vom Memberfunktionsdeklarator bestimmt wird und **const** oder **volatile**\(oder beide\) sein kann, und *class\-type* ist der Name der Klasse:  
  
 *\[cv\-qualifier\-list\] class\-type* **\* const this**  
  
 Das heißt, **this** ist immer ein konstanter Zeiger, er kann nicht erneut zugeordnet werden.  Die **const**\- oder `volatile`\-Qualifizierer, die in der Memberfunktionsdeklaration verwendet werden, gelten für die Klasseninstanz, auf die von **this** im Rahmen dieser Funktion verwiesen wird.  
  
 In der folgenden Tabelle wird näher erläutert, wie diese Modifizierer funktionieren.  
  
### Semantik dieser Modifizierer  
  
|Modifizierer|Bedeutung|  
|------------------|---------------|  
|**const**|Kann Memberdaten nicht ändern; kann Memberfunktionen, nicht **const** sind, nicht aufrufen.|  
|`volatile`|Memberdaten werden vom Arbeitsspeicher geladen, wenn darauf zugegriffen wird; deaktiviert bestimmte Optimierungen.|  
  
 Es ist nicht zulässig, ein **const**\-Objekt an eine Memberfunktion zu übergeben, die nicht **const** ist.  Außerdem ist es nicht zulässig, ein `volatile`\-Objekt an eine Memberfunktion zu übergeben, die nicht `volatile` ist.  
  
 Memberfunktionen, die als **const** deklariert sind, können Memberdaten nicht ändern – in solchen Funktionen ist der **this** Zeiger ein Zeiger auf ein **const**\-Objekt.  
  
> [!NOTE]
>  Konstruktoren und Destruktoren können nicht als **const** oder `volatile` deklariert werden.  Sie können jedoch auf **const**\- oder `volatile`\-Objekten aufgerufen werden.  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Typ des this\-Zeigers](../misc/type-of-this-pointer.md)   
 [Argumentübereinstimmung und der this\-Zeiger](../misc/argument-matching-and-the-this-pointer.md)