---
title: public (C++)
ms.date: 11/04/2016
f1_keywords:
- public_cpp
helpviewer_keywords:
- public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
ms.openlocfilehash: 24cc4dd3cd7e0c893664339e7ad83383839b0b11
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244475"
---
# <a name="public-c"></a>public (C++)

## <a name="syntax"></a>Syntax

```
public:
   [member-list]
public base-class
```

## <a name="remarks"></a>Hinweise

Wenn einer Liste von Klassenmembern vorangestellt der **öffentliche** -Schlüsselwort Gibt an, dass diese Member aus jeder Funktion zugegriffen werden. Dies gilt für alle Member, die bis zum nächsten Zugriffsspezifizierer oder am Ende der Klasse deklariert werden.

Wenn Sie den Namen einer Basisklasse vorangestellt der **öffentliche** Schlüsselwort Gibt an, dass die öffentlichen und geschützten Member der Basisklasse öffentliche und geschützte Member, der abgeleiteten Klasse.

Der Standardzugriff von Membern einer Klasse ist privat. Der Standardzugriff der Member in einer Struktur oder Union ist öffentlich.

Der Standardzugriff einer Basisklasse ist bei Klassen privat und bei Strukturen öffentlich. Unions können keine Basisklassen aufweisen.

Weitere Informationen finden Sie unter [private](../cpp/private-cpp.md), [geschützt](../cpp/protected-cpp.md), [Friend](../cpp/friend-cpp.md), und der memberzugriffstabelle in [Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md) .

## <a name="clr-specific"></a>"/clr"-spezifisch

In CLR-Typen, die C++ Schlüsselwörter für Zugriffsspezifizierer zugreifen (**öffentliche**, **private**, und **geschützt**) kann die Sichtbarkeit von Typen und Methoden hinsichtlich der Assemblys beeinträchtigen. Weitere Informationen finden Sie unter [Memberzugriffssteuerung](member-access-control-cpp.md).

> [!NOTE]
>  Dateien mit kompiliert [/ln](../build/reference/ln-create-msil-module.md) durch dieses Verhalten nicht betroffen sind. In diesem Fall werden alle verwalteten Klassen (entweder "public" oder "private") angezeigt.

## <a name="end-clr-specific"></a>"/clr"-spezifisch – Ende

## <a name="example"></a>Beispiel

```cpp
// keyword_public.cpp
class BaseClass {
public:
   int pubFunc() { return 0; }
};

class DerivedClass : public BaseClass {};

int main() {
   BaseClass aBase;
   DerivedClass aDerived;
   aBase.pubFunc();       // pubFunc() is accessible
                          //    from any function
   aDerived.pubFunc();    // pubFunc() is still public in
                          //    derived class
}
```

## <a name="see-also"></a>Siehe auch

[Steuern des Zugriffs auf Klassenmember](member-access-control-cpp.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)