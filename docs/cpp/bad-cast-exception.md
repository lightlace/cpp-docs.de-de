---
title: bad_cast-Ausnahme
ms.date: 10/04/2019
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: 7384394fb53c6aa4bc009a903ba0ed22bf0ed0d6
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998776"
---
# <a name="bad_cast-exception"></a>bad_cast-Ausnahme

Die **bad_cast** -Ausnahme wird vom **dynamic_cast** -Operator als Ergebnis einer fehlgeschlagenen Umwandlung in einen Verweistyp ausgelöst.

## <a name="syntax"></a>Syntax

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Hinweise

Die Schnittstelle für **bad_cast** lautet:

```cpp
class bad_cast : public exception
```

Der folgende Code enthält ein Beispiel für eine fehlgeschlagene **dynamic_cast** , die die **bad_cast** -Ausnahme auslöst.

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo>
#include <iostream>

class Shape {
public:
   virtual void virtualfunc() const {}
};

class Circle: public Shape {
public:
   virtual void virtualfunc() const {}
};

using namespace std;
int main() {
   Shape shape_instance;
   Shape& ref_shape = shape_instance;
   try {
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);
   }
   catch (bad_cast b) {
      cout << "Caught: " << b.what();
   }
}
```

Die-Ausnahme wird ausgelöst, da das Objekt, das umgewandelt wird (eine Form), nicht vom angegebenen Umwandlungs Typen (Kreis) abgeleitet ist. Um die Ausnahme zu vermeiden, fügen Sie `main` diese Deklarationen hinzu:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Umkehren Sie dann den Sinn der Umwandlung im **try** -Block wie folgt:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Member

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[bad_cast](#bad_cast)|Der Konstruktor für Objekte des Typs `bad_cast`.|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[worüber](#what)|Wird nachgeliefert.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Ein Zuweisungs Operator, der ein `bad_cast`-Objekt einem anderen zuweist.|

## <a name="bad_cast"></a>bad_cast

Der Konstruktor für Objekte des Typs `bad_cast`.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a>Operator =

Ein Zuweisungs Operator, der ein `bad_cast`-Objekt einem anderen zuweist.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a>worüber

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>Siehe auch

[dynamic_cast-Operator](../cpp/dynamic-cast-operator.md)\
[Stichwörter](../cpp/keywords-cpp.md)\
[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)
