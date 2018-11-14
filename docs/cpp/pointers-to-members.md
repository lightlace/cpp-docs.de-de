---
title: Zeiger auf Member
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
ms.openlocfilehash: a15e519be14d9a05cb30a8c9282baccc87a5f35e
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326965"
---
# <a name="pointers-to-members"></a>Zeiger auf Member

Deklarationen von Zeigern auf Member sind Sonderfälle von Zeigerdeklarationen.  Sie können mithilfe der folgenden Sequenz deklariert werden:

```
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier
[= & qualified-name :: member-name];
```

1. Der Deklarationsbezeichner:

   - Ein optionaler Speicherklassenbezeichner.

   - Optionale **const** und/oder **flüchtige** Spezifizierer.

   - Der Typspezifizierer: der Name eines Typs  Dies ist der Typ des Members, auf das gezeigt werden muss, nicht der der Klasse.

1. Der Deklarator:

   - Ein optionaler Microsoft-spezifischer Modifizierer. Weitere Informationen finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).

   - Der qualifizierte Name der Klasse, die die Member enthält, auf die gezeigt werden muss.

   - Die __::__ Operator.

   - Die __\*__ Operator.

   - Optionale **const** und/oder **flüchtige** Spezifizierer.

   - Der Bezeichner, der den Zeiger auf ein Member benennt.

1. Ein optionaler Initialisierer:

   - Die **=** Operator.

   - Die **&** Operator.

   - Der qualifizierte Name der Klasse.

   - Die __::__ Operator.

   - Der Name eines nicht statischen Members der Klasse des entsprechenden Typs.

Wie immer sind mehrere Deklaratoren (sowie alle zugeordneten Initialisierer) in einer einzelnen Deklaration zulässig.

Ein Zeiger auf einen Member einer Klasse unterscheidet sich von einem normalen Zeiger, da er Typinformationen für den Membertyp und die Klasse besitzt, zu der der Member gehört. Ein normaler Zeiger identifiziert nur ein einzelnes Objekt im Arbeitsspeicher (hat nur die Adresse dieses Objekts). Ein Zeiger auf einen Member einer Klasse identifiziert den Member in jeder Instanz der Klasse. Im folgenden Beispiel werden die Klasse `Window` und mehrere Zeiger auf Memberdaten deklariert.

```cpp
// pointers_to_members1.cpp
class Window
{
public:
   Window();                               // Default constructor.
   Window( int x1, int y1,                 // Constructor specifying
   int x2, int y2 );                       //  window size.
bool SetCaption( const char *szTitle ); // Set window caption.
   const char *GetCaption();               // Get window caption.
   char *szWinCaption;                     // Window caption.
};

// Declare a pointer to the data member szWinCaption.
char * Window::* pwCaption = &Window::szWinCaption;
int main()
{
}
```

Im vorherigen Beispiel `pwCaption` ist ein Zeiger auf einen Member der Klasse `Window` weist den Typ, der `char*`. Der Typ von `pwCaption` lautet `char * Window::* `. Im nächsten Codefragment werden Zeiger auf die Memberfunktionen `SetCaption` und `GetCaption` deklariert.

```cpp
const char * (Window::*pfnwGC)() = &Window::GetCaption;
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;
```

Die Zeiger `pfnwGC` und `pfnwSC` zeigen auf `GetCaption` bzw. `SetCaption` der Klasse `Window`. Mithilfe des Zeigers auf den Member `pwCaption` kopiert der Code Informationen direkt in die Fensterbeschriftung:

```cpp
Window wMainWindow;
Window *pwChildWindow = new Window;
char   *szUntitled    = "Untitled -  ";
int    cUntitledLen   = strlen( szUntitled );

strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     //same as
//wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; //same as //pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';
```

Der Unterschied zwischen der **.** <strong>\*</strong> und **->** <strong>\*</strong> Operatoren (der Pointer-to-Member-Operatoren) ist, die die **.** <strong>\*</strong> Operator wählt Elemente zwar angegeben, ein Objekt oder einen Objektverweis, der **->** <strong>\*</strong> Operator Wählt Elemente über einen Zeiger an. (Weitere Informationen zu diesen Operatoren finden Sie unter [Ausdrücke mit Zeiger-auf-Member-Operatoren](../cpp/pointer-to-member-operators-dot-star-and-star.md).)

Das Ergebnis der Pointer-to-Member-Operatoren ist der Typ des Members – in diesem Fall `char *`.

Im folgenden Codefragment werden die Memberfunktionen `GetCaption` und `SetCaption` mithilfe der Zeiger auf Member aufgerufen:

```cpp
// Allocate a buffer.
enum {
    sizeOfBuffer = 100
};
char szCaptionBase[sizeOfBuffer];

// Copy the main window caption into the buffer
//  and append " [View 1]".
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );
// Set the child window's caption.
(pwChildWindow->*pfnwSC)( szCaptionBase );
```

## <a name="restrictions-on-pointers-to-members"></a>Einschränkungen für Zeiger auf Member

Die Adresse eines statischen Members ist kein Zeiger auf einen Member. Es ist ein regulärer Zeiger auf die eine Instanz des statischen Members. Da nur eine Instanz eines statischen Members für alle Objekte einer bestimmten Klasse, die normale Address-of vorhanden ist (**&**) und der Dereferenzierungsoperator (<strong>\*</strong>) Operatoren können verwendet werden.

## <a name="pointers-to-members-and-virtual-functions"></a>Zeiger auf Member und virtuelle Funktionen

Das Aufrufen einer virtuellen Funktion durch einen Zeiger auf eine Memberfunktion verhält sich wie beim direkten Aufruf der Funktion. Die ordnungsgemäße Funktion wird in v-table gesucht und aufgerufen.

Entscheidend für das Funktionieren von virtuellen Funktionen ist immer, dass sie durch einen Zeiger auf eine Basisklasse aufgerufen werden. (Weitere Informationen zu virtuellen Funktionen, finden Sie unter [virtuelle Funktionen](../cpp/virtual-functions.md).)

Der folgende Code zeigt, wie eine virtuelle Funktion durch einen Zeiger auf eine Memberfunktion aufgerufen werden kann:

```cpp
// virtual_functions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base
{
    public:
    virtual void Print();
};
void (Base ::* bfnPrint)() = &Base :: Print;
void Base :: Print()
{
    cout << "Print function for class Base\n";
}

class Derived : public Base
{
    public:
    void Print();  // Print is still a virtual function.
};

void Derived :: Print()
{
    cout << "Print function for class Derived\n";
}

int main()
{
    Base   *bPtr;
    Base    bObject;
    Derived dObject;
    bPtr = &bObject;    // Set pointer to address of bObject.
    (bPtr->*bfnPrint)();
    bPtr = &dObject;    // Set pointer to address of dObject.
    (bPtr->*bfnPrint)();
}

//Output: Print function for class Base
Print function for class Derived
```