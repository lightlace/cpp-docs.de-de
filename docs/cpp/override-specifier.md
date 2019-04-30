---
title: override-Bezeichner
ms.date: 11/04/2016
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
ms.openlocfilehash: 71505f8b9b4dc2800e80a78a64f0ca6984af1349
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345865"
---
# <a name="override-specifier"></a>override-Bezeichner

Sie können die **außer Kraft setzen** Schlüsselwort, um Memberfunktionen festzulegen, die eine virtuelle Funktion in einer Basisklasse überschreiben.

## <a name="syntax"></a>Syntax

```
function-declaration override;
```

## <a name="remarks"></a>Hinweise

**außer Kraft setzen** ist kontextbezogen und hat eine besondere Bedeutung, wenn sie nach einer memberfunktionsdeklaration verwendet wird; andernfalls wird Sie kein reserviertes Schlüsselwort.

## <a name="example"></a>Beispiel

Verwendung **überschreiben** um Vererbungsverhalten im Code zu verhindern. Das folgende Beispiel zeigt, wo, ohne **überschreiben**, das memberfunktionsverhalten der abgeleiteten Klasse möglicherweise nicht vorgesehen wurde. Der Compiler gibt keinen Fehler für diesen Code aus.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA(); // ok, works as intended

    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not
                          // override BaseClass::funcB() const and it is a new member function

    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different
                                      // parameter type than BaseClass::funcC(int), so
                                      // DerivedClass::funcC(double) is a new member function
};
```

Bei Verwendung von **überschreiben**, generiert der Compiler Fehler, anstatt im Hintergrund Erstellen von neuen Member-Funktionen.

```cpp
class BaseClass
{
    virtual void funcA();
    virtual void funcB() const;
    virtual void funcC(int = 0);
    void funcD();
};

class DerivedClass: public BaseClass
{
    virtual void funcA() override; // ok

    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not
                                   // override BaseClass::funcB() const

    virtual void funcC( double = 0.0 ) override; // compiler error:
                                                 // DerivedClass::funcC(double) does not
                                                 // override BaseClass::funcC(int)

    void funcD() override; // compiler error: DerivedClass::funcD() does not
                           // override the non-virtual BaseClass::funcD()
};
```

Um anzugeben, dass Funktionen nicht überschrieben werden können und Klassen nicht geerbt werden können, verwenden die [endgültige](../cpp/final-specifier.md) Schlüsselwort.

## <a name="see-also"></a>Siehe auch

[final-Bezeichner](../cpp/final-specifier.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)