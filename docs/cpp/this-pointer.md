---
title: this-Zeiger
description: Der this Zeiger ist ein vom Compiler generierter Zeiger auf das aktuelle-Objekt in nicht statischen Element Funktionen.
ms.date: 01/22/2020
f1_keywords:
- this_cpp
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
no-loc:
- this
- class
- struct
- union
- sizeof
- const
- volatile
ms.openlocfilehash: 58bba2edd7a457c624b747b5a65d209995852848
ms.sourcegitcommit: a930a9b47bd95599265d6ba83bb87e46ae748949
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "76518334"
---
# <a name="opno-locthis-pointer"></a>this-Zeiger

Der **this** Zeiger ist ein Zeiger, auf den nur innerhalb der nicht statischen Element Funktionen eines **class** , **struct** oder **union** Typs zugegriffen werden kann. Er zeigt auf das Objekt, für das die Memberfunktion aufgerufen wird. Statische Member-Funktionen verfügen nicht über einen **this** -Zeiger.

## <a name="syntax"></a>Syntax

```cpp
this
this->member-identifier
```

## <a name="remarks"></a>Hinweise

Der **this** Zeiger eines Objekts ist nicht Teil des Objekts selbst. Dies wird im Ergebnis einer **sizeof** -Anweisung für das-Objekt nicht widergespiegelt. Wenn eine nicht statische Member-Funktion für ein Objekt aufgerufen wird, übergibt der Compiler die Adresse des Objekts als verborgenes Argument an die Funktion. Folgender Funktionsaufruf kann beispielsweise:

```cpp
myDate.setMonth( 3 );
```

kann wie folgt interpretiert werden:

```cpp
setMonth( &myDate, 3 );
```

Die Adresse des Objekts ist innerhalb der Member-Funktion als **this** Zeiger verfügbar. Die meisten **this** Zeiger verwenden implizit. Es ist jedoch nicht erforderlich, ein explizites **this** zu verwenden, wenn Sie auf Mitglieder der classverweisen. Beispiel:

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

Der **this** Zeiger wird auch zum Schutz vor selbst verweisen verwendet:

```cpp
if (&Object != this) {
// do not execute in cases of self-reference
```

> [!NOTE]
> Da der **this** Zeiger nicht änderbar ist, sind Zuweisungen zum **this** Zeiger nicht zulässig. Frühere Implementierungen der C++ zulässigen Zuweisung zu **this** .

Gelegentlich wird der **this** Zeiger direkt verwendet, z. –. zum Bearbeiten von selbstreferenziellen Datenstrukturen, bei denen die Adresse des aktuellen-Objekts erforderlich ist.

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

    // assignment operator
    myBuf = yourBuf;

    // Display 'your buffer'
    myBuf.Display();
}
```

```Output
my buffer
your buffer
```

## <a name="type-of-the-opno-locthis-pointer"></a>Der Typ des this Zeigers.

Der Typ des **this** Zeigers kann in der Funktionsdeklaration durch die Schlüsselwörter **const** und **volatile** geändert werden. Um eine Funktion mit einem dieser Attribute zu deklarieren, fügen Sie das Schlüsselwort (e) nach der Funktions Argumentliste hinzu.

Sehen Sie sich ein Beispiel an:

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

Der vorangehende Code deklariert eine Member-Funktion `X`, in der der **this** Zeiger als **const** Zeiger auf ein **const** Objekt behandelt wird. Es können Kombinationen von *CV-mod-List-* Optionen verwendet werden, aber Sie ändern immer das Objekt, auf das der **this** Zeiger zeigt, nicht der Zeiger selbst. In der folgenden Deklaration werden Funktions `X`deklariert, wobei der **this** Zeiger ein **const** Zeiger auf ein **const** Objekt ist:

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

Der Typ der **this** in einer Member-Funktion wird durch die folgende Syntax beschrieben. Die *CV-qualifiziererliste* wird vom Deklarator der Element Funktion bestimmt. Sie kann **const** oder **volatile** (oder beides) sein. *class-Type* ist der Name des class:

[*CV-Qualifizierer-List*] *class* **\* const this**

Dies bedeutet, dass der **this** Zeiger immer ein const Zeiger ist. Sie kann nicht neu zugewiesen werden.  The **const** or **volatile** qualifiers used in the member function declaration apply to the class instance the **this** pointer points at, in the scope of that function.

In der folgenden Tabelle wird näher erläutert, wie diese Modifizierer funktionieren.

### <a name="semantics-of-opno-locthis-modifiers"></a>Semantics of this modifiers

|Modifizierer|Bedeutung|
|--------------|-------------|
|**const**|Can't change member data; can't invoke member functions that aren't **const** .|
|**volatile**|Member data is loaded from memory each time it's accessed; disables certain optimizations.|

It's an error to pass a **const** object to a member function that isn't **const** .

Similarly, it's also an error to pass a **volatile** object to a member function that isn't **volatile** .

Member functions declared as **const** can't change member data — in such functions, the **this** pointer is a pointer to a **const** object.

> [!NOTE]
> Constructors and destructors can't be declared as **const** or **volatile** . They can, however, be invoked on **const** or **volatile** objects.

## <a name="see-also"></a>Siehe auch

[Stichwörter](../cpp/keywords-cpp.md)
