---
title: this-Zeiger
ms.date: 11/04/2016
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
ms.openlocfilehash: 586ed9d7e07165af71eeb2ee7ab22aba9570bcd3
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328876"
---
# <a name="this-pointer"></a>this-Zeiger

Die **dies** ist ein Zeiger kann nur innerhalb der nicht statischen Memberfunktionen des zugegriffen eine **Klasse**, **Struktur**, oder **Union** Typ. Er zeigt auf das Objekt, für das die Memberfunktion aufgerufen wird. Statische Memberfunktionen haben keine **dies** Zeiger.

## <a name="syntax"></a>Syntax

```
this
this->member-identifier
```

## <a name="remarks"></a>Hinweise

Eines Objekts **dies** Zeiger ist nicht Teil des Objekts selbst nicht im Ergebnis übernommen wird eine **"sizeof"** -Anweisung für das Objekt. Wenn stattdessen eine nicht statische Memberfunktion für ein Objekt aufgerufen wird, wird die Adresse des Objekts vom Compiler als ausgeblendetes Argument an die Funktion übergeben. Folgender Funktionsaufruf kann beispielsweise:

```cpp
myDate.setMonth( 3 );
```

auf diese Weise interpretiert werden:

```cpp
setMonth( &myDate, 3 );
```

Die Adresse des Objekts in der Memberfunktion als verfügbar ist die **dies** Zeiger. Die meisten Verwendungen von **dies** sind implizit. Es ist zulässig, jedoch nicht erforderlich, explizit **dies** beim Verweisen auf Member der Klasse. Zum Beispiel:

```cpp
void Date::setMonth( int mn )
{
   month = mn;            // These three statements
   this->month = mn;      // are equivalent
   (*this).month = mn;
}
```

Der Ausdruck `*this` wird häufig verwendet, um das aktuelle Objekt aus einer Memberfunktion zurückzugeben:

```cpp
return *this;
```

Die **dies** -Zeiger wird auch verwendet, um vor Selbstverweisen zu schützen:

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
>  Da die **dies** -Zeiger nicht veränderbar ist, ist Zuweisungen zu **dies** sind nicht zulässig. Frühere Implementierungen von C++ lassen Zuweisungen zu **dies**.

In einigen Fällen die **dies** -Zeiger direkt verwendet, z. B. zum Bearbeiten von auf sich selbst verweisende Datenstrukturen, wenn die Adresse des aktuellen Objekts erforderlich ist.

## <a name="example"></a>Beispiel

```cpp
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

```Output
my buffer
your buffer
```

## <a name="type-of-the-this-pointer"></a>Typ des this-Zeigers.

Die **dies** Typ des Zeigers kann geändert werden, in der Funktionsdeklaration durch die **const** und **flüchtige** Schlüsselwörter. Um eine Funktion so zu deklarieren, dass sie die Attribute von mindestens einem dieser Schlüsselwörter hat, fügen Sie die Schlüsselwörter nach der Funktionsargumentliste hinzu.

Betrachten Sie das folgende Beispiel:

```cpp
// type_of_this_pointer1.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

Der vorangehende Code deklariert eine Memberfunktion `X`, in dem der **dies** Zeiger behandelt, als eine **const** Zeiger auf eine **const** Objekt. Kombinationen von *cv-mod-List* Optionen können verwendet werden, sie ändern jedoch immer das Objekt verweist **dies**, nicht die **dies** Zeiger selbst. Aus diesem Grund wird die folgende Deklaration Funktion deklariert `X`; die **dies** -Zeiger ist ein **const** Zeiger auf eine **const** Objekt:

```cpp
// type_of_this_pointer2.cpp
class Point
{
    unsigned X() const;
};
int main()
{
}
```

Der Typ des **dies** in einen Member-Funktion wird durch die folgende Syntax, beschrieben, in denen *cv-Qualifier-List* wird vom Deklarator Funktionen Element bestimmt und kann **Const**oder **flüchtige** (oder beides), und *Klassentyp* ist der Name der Klasse:

*[cv-Qualifier-List] Klassentyp* **&#42; const dies**

Das heißt, **dies** ist immer ein konstanter Zeiger, sie kann nicht zugewiesen werden.  Die **const** oder **flüchtige** Qualifizierer, die in der memberfunktionsdeklaration verwendet, gelten für die Instanz der Klasse verweist **dies** im Rahmen dieser Funktion.

In der folgenden Tabelle wird näher erläutert, wie diese Modifizierer funktionieren.

### <a name="semantics-of-this-modifiers"></a>Semantik dieser Modifizierer

|Modifizierer|Bedeutung|
|--------------|-------------|
|**const**|Kann Memberdaten nicht ändern. kann nicht aufgerufen werden, die nicht-Memberfunktionen **const**.|
|**volatile**|Memberdaten werden vom Arbeitsspeicher geladen, wenn darauf zugegriffen wird; deaktiviert bestimmte Optimierungen.|

Es ist ein Fehler zum Übergeben einer **const** Objekt auf eine Memberfunktion, die nicht **const**. Es ist auch zu übergeben eine **flüchtige** Objekt auf eine Memberfunktion, die nicht **flüchtige**.

Memberfunktionen deklariert als **const** Memberdaten nicht ändern – in solchen Funktionen ist die **dies** ist ein Zeiger auf eine **const** Objekt.

> [!NOTE]
>  Konstruktoren und Destruktoren können nicht als deklariert werden **const** oder **flüchtige**. Sie können jedoch werden aufgerufen **const** oder **flüchtige** Objekte.

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../cpp/keywords-cpp.md)