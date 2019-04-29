---
title: weak_ptr-Klasse
ms.date: 11/04/2016
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
ms.openlocfilehash: e2efb5d534ad43e2492ac4fb0bf76db402dca272
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410854"
---
# <a name="weakptr-class"></a>weak_ptr-Klasse

Umschließt einen schwach verknüpften Zeiger.

## <a name="syntax"></a>Syntax

```cpp
template<class _Ty>
   class weak_ptr {
public:
   typedef Ty element_type;
   weak_ptr();
   weak_ptr(const weak_ptr&);
   template <class Other>
      weak_ptr(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr(const shared_ptr<Other>&);
   weak_ptr& operator=(const weak_ptr&);
   template <class Other>
      weak_ptr& operator=(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr& operator=(shared_ptr<Other>&);
   void swap(weak_ptr&);
   void reset();
   long use_count() const;
   bool expired() const;
   shared_ptr<Ty> lock() const;
   };
```

### <a name="parameters"></a>Parameter

*Ty*<br/>
Der vom schwachen Zeiger gesteuerte Typ.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das auf eine Ressource zeigt, die von mindestens einem [shared_ptr-Klassen](../standard-library/shared-ptr-class.md)-Objekt verwaltet wird. Die `weak_ptr`-Objekte, die auf eine Ressource verweisen, wirken sich nicht auf den Verweiszähler der Ressource aus. Daher wird die Ressource, wenn das letzte `shared_ptr`-Objekt, das diese Ressource verwaltet, zerstört wurde, selbst dann freigegeben, wenn es `weak_ptr`-Objekte gibt, die auf diese Ressource verweisen. Dies ist entscheidend für die Vermeidung von Zyklen in Datenstrukturen.

Ein `weak_ptr`-Objekt verweist auf eine Ressource, wenn es aus einem `shared_ptr`-Objekt erstellt wurde, das diese Ressource besitzt, wenn es aus einem `weak_ptr`-Objekt erstellt wurde, das auf diese Ressource verweist, oder wenn ihm diese Ressource mit [operator=](#op_eq) zugewiesen wurde. Ein `weak_ptr`-Objekt stellt keinen direkten Zugriff auf die Ressource bereit, auf die es verweist. Code, der auf die Ressource zugreifen muss, erledigt dies über ein `shared_ptr`-Objekt, das diese Ressource besitzt, die durch Aufrufen der Memberfunktion [lock](#lock) erstellt wurde. Ein `weak_ptr`-Objekt ist abgelaufen, wenn die Ressource, auf die es verweist, freigegeben wurde, weil alle `shared_ptr`-Objekte zerstört wurden, die die Ressource besitzen. Ein Aufrufen von `lock` für ein `weak_ptr`-Objekt, das abgelaufen ist, erstellt ein leeres shared_ptr-Objekt.

Ein leeres weak_ptr-Objekt verweist auf keine Ressource und hat keinen Kontrollblock. Ihre Memberfunktion `lock` gibt ein leeres shared_ptr-Objekt zurück.

Ein Zyklus tritt auf, wenn es für zwei oder mehr Ressourcen, die von `shared_ptr`-Objekten gesteuert werden, `shared_ptr`-Objekte gibt, die gegenseitig auf sich verweisen. Angenommen, eine kreisförmig verknüpfte Liste mit drei Elementen hat den Kopfknoten `N0`; dieser Knoten enthält ein `shared_ptr`-Objekt, das den nächsten Knoten, `N1`, besitzt; dieser Knoten enthält ein `shared_ptr`-Objekt, das den nächsten Knoten, `N2`, besitzt; dieser Knoten wiederum enthält ein `shared_ptr`-Objekt, das den Kopfknoten `N0` besitzt, wodurch der Zyklus geschlossen wird. In diesem Fall wird keiner der Verweiszähler je den Wert 0 (null) annehmen, und die Knoten im Zyklus werden nicht freigegeben. Um den Zyklus zu vermeiden, sollte der letzte Knoten, `N2`, anstelle eines `shared_ptr`-Objekts ein `weak_ptr`-Objekt enthalten, das auf `N0` verweist. Da das `weak_ptr`-Objekt kein Besitzer von `N0` ist, hat es keinen Einfluss auf den Verweiszähler von `N0`, und wenn im Programm der letzte Verweis auf den Kopfknoten zerstört wurde, werden auch die Knoten in der Liste zerstört.

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[weak_ptr](#weak_ptr)|Erstellt ein Objekt vom Typ `weak_ptr`.|

### <a name="methods"></a>Methoden

|||
|-|-|
|[element_type](#element_type)|Der Typ des Elements.|
|[expired](#expired)|Überprüft, ob der Besitz abgelaufen ist.|
|[lock](#lock)|Bedingt exklusiven Besitz einer Ressource.|
|[owner_before](#owner_before)|Gibt **"true"** Wenn diese `weak_ptr` sortiert ist, bevor Sie (oder kleiner als) des bereitgestellten Zeigers.|
|[reset](#reset)|Gibt eine in Besitz befindliche Ressource frei.|
|[swap](#swap)|Tauscht zwei `weak_ptr`-Objekte.|
|[use_count](#use_count)|Ermittelt die Anzahl von festgelegten `shared_ptr`-Objekten.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Ersetzt eine in Besitz befindliche Ressource.|

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="element_type"></a> element_type

Der Typ des Elements.

```cpp
typedef Ty element_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Ty` dar.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
    }
```

```Output
*wp0.lock() == 5
```

## <a name="expired"></a> expired

Überprüft, ob der Besitz abgelaufen ist.

```cpp
bool expired() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt **"true"** Wenn `*this` abgelaufen ist, andernfalls **"false"**.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="lock"></a> lock

Bedingt exklusiven Besitz einer Ressource.

```cpp
shared_ptr<Ty> lock() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein leeres Shared_ptr-Objekt zurück, wenn `*this` abgelaufen ist; andernfalls wird eine [Shared_ptr-Klasse](../standard-library/shared-ptr-class.md)\<Ty >-Objekt, das die Ressource besitzt `*this` verweist auf.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="op_eq"></a> operator=

Ersetzt eine in Besitz befindliche Ressource.

```cpp
weak_ptr& operator=(const weak_ptr& wp);

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parameter

*Andere*<br/>
Der Typ, der vom Argument für den gemeinsamen/schwachen Zeiger gesteuert wird.

*wp*<br/>
Der zu kopierende schwache Zeiger.

*sp*<br/>
Der zu kopierende gemeinsame Zeiger

### <a name="remarks"></a>Hinweise

Die Operatoren geben alle die Ressource frei, auf die derzeit von `*this` gezeigt wird, und weisen den Besitz der Ressource, die von der Operatorsequenz benannt wird, `*this` zu. Wenn bei einem Operator ein Fehler auftritt, bleibt `*this` unverändert.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

## <a name="owner_before"></a> owner_before

Gibt **"true"** Wenn diese `weak_ptr` sortiert ist, bevor Sie (oder kleiner als) des bereitgestellten Zeigers.

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Ein `lvalue`-Verweis auf `shared_ptr` oder `weak_ptr`.

### <a name="remarks"></a>Hinweise

Die vorlagenmemberfunktion gibt **"true"** Wenn `*this` ist `ordered before` `ptr`.

## <a name="reset"></a> reset

Gibt eine in Besitz befindliche Ressource frei.

```cpp
void reset();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Ressource frei, auf die von `*this` gezeigt wird, und konvertiert `*this` in ein leeres „weak_ptr“-Objekt.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}
```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

## <a name="swap"></a> swap

Tauscht zwei `weak_ptr`-Objekte.

```cpp
void swap(weak_ptr& wp);
```

### <a name="parameters"></a>Parameter

*wp*<br/>
Der schwache Zeiger, mit dem getauscht werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion belässt die Ressource, die ursprünglich verweist `*this` anschließend verweist *wp*, und die Ressource, die ursprünglich verweist *wp* anschließend verweist`*this`. Die Funktion ändert die Verweisanzahlen für die beiden Ressourcen nicht und löst auch keine Ausnahmen aus.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="use_count"></a> use_count

Ermittelt die Anzahl von festgelegten `shared_ptr`-Objekten.

```cpp
long use_count() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Anzahl der `shared_ptr`-Objekte zurück, die die Ressource besitzen, auf die von `*this` gezeigt wird.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}
```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

## <a name="weak_ptr"></a> weak_ptr

Erstellt ein Objekt vom Typ `weak_ptr`.

```cpp
weak_ptr();

weak_ptr(const weak_ptr& wp);

template <class Other>
weak_ptr(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>Parameter

*Andere*<br/>
Der Typ, der vom Argument für den gemeinsamen/schwachen Zeiger gesteuert wird.

*wp*<br/>
Der zu kopierende schwache Zeiger.

*sp*<br/>
Der zu kopierende gemeinsame Zeiger

### <a name="remarks"></a>Hinweise

Die Konstruktoren erstellen jeweils ein Objekt, das auf die Ressource zeigt, die von der Operatorensequenz benannt wird.

### <a name="example"></a>Beispiel

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}
```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```

## <a name="see-also"></a>Siehe auch

[shared_ptr-Klasse](../standard-library/shared-ptr-class.md)<br/>
