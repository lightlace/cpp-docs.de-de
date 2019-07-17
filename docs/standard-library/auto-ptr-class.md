---
title: auto_ptr-Klasse
ms.date: 11/04/2016
f1_keywords:
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
helpviewer_keywords:
- std::auto_ptr [C++]
- std::auto_ptr [C++], element_type
- std::auto_ptr [C++], get
- std::auto_ptr [C++], release
- std::auto_ptr [C++], reset
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
ms.openlocfilehash: c64865c98f52f68fcb6d38160ac885657a7b8916
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244009"
---
# <a name="autoptr-class"></a>auto_ptr-Klasse

Schließt eine Ressource in einen intelligenten Zeiger ein, der sicherstellt, dass die Ressource automatisch zerstört wird, wenn die Steuerung einen Block verlässt.

Die leistungsfähigere `unique_ptr`-Klasse ersetzt `auto_ptr`. Weitere Informationen finden Sie unter [unique_ptr Class(unique_ptr-Klasse)](../standard-library/unique-ptr-class.md).

Weitere Informationen zu `throw()` und zur Behandlung von Ausnahmen finden Sie unter [Ausnahmespezifikationen (throw)](../cpp/exception-specifications-throw-cpp.md).

## <a name="syntax"></a>Syntax

```cpp
class auto_ptr {
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```

### <a name="parameters"></a>Parameter

*Richting*\
Der `auto_ptr`, aus dem eine vorhandene Ressource abgerufen werden soll.

*PTR*\
Der Zeiger, der den gespeicherten Zeiger ersetzen soll.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt einen intelligenten Zeiger, der Namen einer `auto_ptr`, auf ein zugeordnetes Objekt. Der Zeiger muss entweder null oder ein Objekt von zugeordneten **neue**. Der `auto_ptr` übergibt den Besitz, wenn sein gespeicherter Wert einem anderen Objekt zugewiesen wird. (Er ersetzt den gespeicherten Wert nach einer Übergabe mit einem NULL-Zeiger.) Der Destruktor für `auto_ptr<Type>` löscht das zugeordnete Objekt. Der `auto_ptr<Type>` stellt sicher, dass ein zugeordnetes Objekt automatisch gelöscht wird, wenn die Steuerung einen Block verlässt, selbst wenn dies über eine ausgelöste Ausnahme erfolgt. Sie sollten nicht zwei `auto_ptr<Type>`-Objekte erstellen, die Eigentümer desselben Objekts sind.

Sie können ein `auto_ptr<Type>`-Objekt als Wert als ein Argument für einen Funktionsaufruf übergeben. Ein `auto_ptr`-Objekt kann kein Element eines Standardbibliothekcontainers sein. Es ist nicht möglich, eine Sequenz von `auto_ptr<Type>`-Objekten zuverlässig mit einem Container für eine C++-Standardbibliothek zu verwalten.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|||
|-|-|
|[auto_ptr](#auto_ptr)|Der Konstruktor für Objekte des Typs `auto_ptr`.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[element_type](#element_type)|Der Type stellt ein Synonym für den Vorlagenparameter `Type` dar.|

### <a name="functions"></a>Funktionen

|||
|-|-|
|[get](#get)|Die Memberfunktion gibt den gespeicherten Zeiger `myptr` zurück.|
|[release](#release)|Der Member ersetzt den gespeicherten Zeiger `myptr` durch einen NULL-Zeiger und gibt den zuvor gespeicherten Zeiger zurück.|
|[reset](#reset)|Die Memberfunktion wertet den Ausdruck `delete myptr` aus, allerdings nur, wenn sich der Wert des gespeicherten Zeigers `myptr` aufgrund eines Funktionsaufrufs ändert. Anschließend ersetzt die Funktion den gespeicherten Zeiger durch *ptr*.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator=](#op_eq)|Ein Zuweisungsoperator, der den Besitz von einem `auto_ptr`-Objekt an ein anderes Objekt übergibt.|
|[operator*](#op_star)|Der dereferenzierende Operator für Objekte des Typs `auto_ptr`.|
|[operator->](#op_arrow)|Der Operator zum Ermöglichen von Memberzugriff.|
|[operator auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|Nimmt eine Umwandlung aus einer Art von `auto_ptr` in eine andere Art von `auto_ptr` vor.|
|[operator auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|Nimmt eine Umwandlung von einem `auto_ptr` zu einem anderen `auto_ptr_ref` vor.|

### <a name="auto_ptr"></a> auto_ptr

Der Konstruktor für Objekte des Typs `auto_ptr`.

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

#### <a name="parameters"></a>Parameter

*PTR*\
Der Zeiger auf das Objekt, das `auto_ptr` kapselt.

*Richting*\
Das `auto_ptr`-Objekt, das vom Konstruktor kopiert werden soll.

#### <a name="remarks"></a>Hinweise

Der erste Konstruktor speichert *Ptr* in `myptr`, den gespeicherten Zeiger auf das zugeordnete Objekt. Der zweite Konstruktor überträgt den Besitz des Zeigers in gespeicherten *rechten*, durch das Speichern von *rechten*. [Release](#release) in `myptr`.

Der dritte Konstruktor verhält sich wie der zweite, außer dass es speichert `right`. `ref`. `release` in `myptr`, wobei `ref` wird der Verweis gespeichert `right`.

Der vorlagenkonstruktor verhält sich genauso wie der zweite Konstruktor, bereitgestellt, die einen Zeiger auf `Other` kann implizit konvertiert werden, auf einen Zeiger auf `Type`.

#### <a name="example"></a>Beispiel

```cpp
// auto_ptr_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

void function ( auto_ptr<Int> &pi )
{
   ++( *pi );
   auto_ptr<Int> pi2( pi );
   ++( *pi2 );
   pi = pi2;
}

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   cout << pi->x << endl;
   function( pi );
   cout << pi->x << endl;
}
```

```Output
Constructing 00311AF8
5
7
Destructing 00311AF8
```

### <a name="element_type"></a> ELEMENT_TYPE

Der Type stellt ein Synonym für den Vorlagenparameter `Type` dar.

```cpp
typedef Type element  _type;
```

### <a name="get"></a> Erhalten

Die Memberfunktion gibt den gespeicherten Zeiger `myptr` zurück.

```cpp
Type *get() const throw();
```

#### <a name="return-value"></a>Rückgabewert

Der gespeicherte Zeiger `myptr`.

#### <a name="example"></a>Beispiel

```cpp
// auto_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      x = i;
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;
   };

   int x;

};

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   pi.reset( new Int( 6 ) );
   Int* pi2 = pi.get ( );
   Int* pi3 = pi.release ( );
   if (pi2 == pi3)
      cout << "pi2 == pi3" << endl;
   delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="op_eq"></a> Operator =

Ein Zuweisungsoperator, der den Besitz von einem `auto_ptr`-Objekt an ein anderes Objekt übergibt.

```cpp
template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

#### <a name="parameters"></a>Parameter

*Richting*\
Ein Objekt vom Typ `auto_ptr`.

#### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein Objekt des Typs `auto_ptr<Type>`.

#### <a name="remarks"></a>Hinweise

Die Zuweisung wertet den Ausdruck `delete myptr`, aber nur, wenn der gespeicherte Zeiger `myptr` aufgrund der Zuweisung ändert. Überträgt es dann den Besitz von im gespeicherten Zeigers *rechten*, durch das Speichern von *rechten*.[ Release](#release) in `myptr`. Die Funktion gibt __\*this__ zurück.

#### <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung des memberoperators finden Sie unter [Auto_ptr](#auto_ptr).

### <a name="op_star"></a> Operator *

Der dereferenzierende Operator für Objekte des Typs `auto_ptr`.

```cpp
Type& operator*() const throw();
```

#### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein Objekt des Typs `Type` , das der Zeiger besitzt.

#### <a name="remarks"></a>Hinweise

Der Dereferenzierungsoperator gibt `*`[get](#get) zurück. Daher darf der gespeicherte Zeiger nicht NULL sein.

#### <a name="example"></a>Beispiel

Ein Beispiel dafür, wie die Member-Funktion verwenden, finden Sie unter [Auto_ptr](#auto_ptr).

### <a name="op_arrow"></a> Operator-&gt;

Der Operator zum Ermöglichen von Memberzugriff.

```cpp
Type * operator->() const throw();
```

#### <a name="return-value"></a>Rückgabewert

Ein Member des Objekts, das `auto_ptr` besitzt.

#### <a name="remarks"></a>Hinweise

Der Auswahloperator gibt [get](#get)`( )` zurück, sodass der Ausdruck *ap*-> **member** sich genauso verhält wie ( *ap*. **get**( ) )-> **member**, wo *ap* ein Objekt der Klasse `auto_ptr`\< **Type**> ist. Daher der gespeicherte Zeiger darf nicht null sein, und `Type` muss eine Klasse, Struktur oder union-Typ mit einem `member` Member.

#### <a name="example"></a>Beispiel

Ein Beispiel dafür, wie die Member-Funktion verwenden, finden Sie unter [Auto_ptr](#auto_ptr).

### <a name="op_auto_ptr_lt_other_gt"></a> Operator Auto_ptr&lt;andere&gt;

Nimmt eine Umwandlung aus einer Art von `auto_ptr` in eine andere Art von `auto_ptr` vor.

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

#### <a name="return-value"></a>Rückgabewert

Der Typumwandlungsoperator gibt `auto_ptr` \< **Other**>( **\*this**) zurück.

#### <a name="example"></a>Beispiel

```cpp
// auto_ptr_op_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;
int main()
{
   auto_ptr<int> pi ( new int( 5 ) );
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;
}
```

### <a name="op_auto_ptr_ref_lt_other_gt"></a> Operator Auto_ptr_ref&lt;andere&gt;

Nimmt eine Umwandlung von einem `auto_ptr` zu einem anderen `auto_ptr_ref` vor.

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

#### <a name="return-value"></a>Rückgabewert

Der Typumwandlungsoperator gibt **auto_ptr_ref**\< **Other**>( **\*this**) zurück.

#### <a name="example"></a>Beispiel

```cpp
// auto_ptr_op_auto_ptr_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer
    // f(ciap);
    f(iap); // compiles, but gives up ownership of pointer

            // here, iap owns a destroyed pointer so the following is bad:
            // *iap = 5; // BOOM

    cout << "main exiting\n";
}
```

```Output
~C:  2
main exiting
~C:  1
```

### <a name="release"></a> Version

Der Member ersetzt den gespeicherten Zeiger `myptr` durch einen NULL-Zeiger und gibt den zuvor gespeicherten Zeiger zurück.

```cpp
Type *release() throw();
```

#### <a name="return-value"></a>Rückgabewert

Der zuvor gespeicherte Zeiger.

#### <a name="remarks"></a>Hinweise

Der Member ersetzt den gespeicherten Zeiger `myptr` durch einen NULL-Zeiger und gibt den zuvor gespeicherten Zeiger zurück.

#### <a name="example"></a>Beispiel

```cpp
// auto_ptr_release.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="reset"></a> Zurücksetzen

Die Memberfunktion wertet den Ausdruck `delete myptr`, aber nur, wenn der Wert des gespeicherten Zeigers `myptr` aufgrund eines Funktionsaufrufs ändert. Anschließend ersetzt die Funktion den gespeicherten Zeiger durch `ptr`.

```cpp
void reset(Type* ptr = 0);
```

#### <a name="parameters"></a>Parameter

*PTR*\
Der Zeiger, der den gespeicherten Zeiger ersetzen `myptr`.

#### <a name="example"></a>Beispiel

```cpp
// auto_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

## <a name="see-also"></a>Siehe auch

[unique_ptr-Klasse](../standard-library/unique-ptr-class.md)<br/>
