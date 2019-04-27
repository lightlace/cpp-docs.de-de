---
title: noexcept (C++)
ms.date: 01/12/2018
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: c314b554abb6c10e62b143f554777af50267e4e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245360"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++11:** Gibt an, ob eine Funktion Ausnahmen auslösen kann.

## <a name="syntax"></a>Syntax

> *noexcept-expression*: &nbsp;&nbsp;&nbsp;&nbsp;**noexcept** &nbsp;&nbsp;&nbsp;&nbsp;**noexcept(** *constant-expression* **)**

### <a name="parameters"></a>Parameter

*constant-expression*<br/>
Ein konstanter Ausdruck des Typs **"bool"** , das darstellt, ob der Satz von möglichen Ausnahmetypen leer ist. Die Version ohne entspricht `noexcept(true)`.

## <a name="remarks"></a>Hinweise

Ein *"noexcept" Ausdruck* ist eine Art von *Ausnahmespezifikation*, ein Suffix an, die Deklaration einer Funktion, die einen Satz von Typen darstellt, die von einem Ausnahmehandler für jede Ausnahme abgeglichen werden kann, die beendet eine -Funktion. Unäre Bedingungsoperator `noexcept(` *Constant_expression* `)` , in denen *Constant_expression* Yeilds **"true"**, und das Synonym **"noexcept"**, anzugeben, dass die Gruppe der potenziellen Ausnahmetypen, die eine Funktion zu beenden, können leer ist. Also die Funktion löst nie eine Ausnahme aus und ermöglicht nie eine Ausnahme von außerhalb ihres Bereichs weitergegeben werden. Der Operator `noexcept(` *Constant_expression* `)` , in denen *Constant_expression* Yeilds **"false"**, oder das Fehlen von eine Ausnahmespezifikation (außer bei einer Funktion Destruktor oder Aufhebung der Zuordnung), gibt an, dass der Satz von möglichen Ausnahmen, die die Funktion beendet, können den Satz aller Typen.

Markieren Sie eine Funktion als **"noexcept"** nur dann, wenn alle Funktionen, die, entweder direkt oder indirekt aufgerufen, auch werden **"noexcept"** oder **const**. Der Compiler überprüft nicht unbedingt jeden Codepfad auf Ausnahmen, die bis zu auswirken können eine **"noexcept"** Funktion. Wenn eine Ausnahme, den äußeren Bereich einer Funktion, die markiert beendet wird `noexcept`, [Std:: Terminate](../standard-library/exception-functions.md#terminate) wird sofort aufgerufen, und es gibt keine Garantie, dass alle Objekte im Gültigkeitsbereich befindlichen Destruktoren aufgerufen werden. Verwendung **"noexcept"** anstelle der dynamischen ausnahmebezeichner `throw()`, im Standard mittlerweile veraltet. Sollten Sie anwenden `noexcept` für alle Funktionen, die nie eine Ausnahme der Aufrufliste nach oben weitergegeben werden kann. Wenn eine Funktion deklariert wird **"noexcept"**, es kann der Compiler effizienteren Code in verschiedenen anderen Kontexten generieren. Weitere Informationen finden Sie unter [Ausnahmespezifikationen](exception-specifications-throw-cpp.md).

## <a name="example"></a>Beispiel

Eine Vorlagenfunktion, die ihre Argumente kopiert deklariert werden möglicherweise **"noexcept"** auf der Bedingung, dass das kopierte Objekt ein plain old Datentyp (POD) ist. Eine solche Funktion kann wie folgt deklariert werden:

```cpp
#include <type_traits>

template <typename T>
T copy_object(const T& obj) noexcept(std::is_pod<T>)
{
   // ...
}
```

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](cpp-exception-handling.md)<br/>
[Ausnahmespezifikationen (Throw, "noexcept")](exception-specifications-throw-cpp.md)