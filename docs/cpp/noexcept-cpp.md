---
title: noexcept (C++)
ms.date: 01/12/2018
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: cf53aca918e36d18ab7f8aa14b01caaf0e55627c
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975896"
---
# <a name="noexcept-c"></a>noexcept (C++)

**C++11:** Gibt an, ob eine Funktion Ausnahmen auslösen kann.

## <a name="syntax"></a>Syntax

> *noaußer-Expression*: &nbsp; &nbsp; &nbsp; noaußer noaußer&nbsp; **(** *Constant-* Expression &nbsp; &nbsp; &nbsp; &nbsp;  **)**

### <a name="parameters"></a>Parameter

*constant-expression*<br/>
Ein konstanter Ausdruck vom Typ **bool** , der angibt, ob der Satz potenzieller Ausnahme Typen leer ist. Die bedingungslose Version entspricht `noexcept(true)`.

## <a name="remarks"></a>Hinweise

Ein *noaußer-Ausdruck* ist eine Art von *Ausnahme Spezifikation*, ein Suffix für eine Funktionsdeklaration, die einen Satz von Typen darstellt, die möglicherweise von einem Ausnahmehandler für jede Ausnahme, die eine Funktion beendet, abgeglichen werden. Unärer Bedingter Operator `noexcept(` *constant_expression* `)` wobei *constant_expression* **true**ergibt und das Bedingungs bedingte Synonym **noaußer**, gibt an, dass der Satz potenzieller Ausnahme Typen, die kann eine Funktion beenden, ist leer. Das heißt, die Funktion löst nie eine Ausnahme aus und lässt niemals zu, dass eine Ausnahme außerhalb des Gültigkeits Bereichs weitergegeben wird. Der Operator `noexcept(` *constant_expression* `)` Where *constant_expression* ergibt **false**, oder das Fehlen einer Ausnahme Spezifikation (außer für einen Dekonstruktor oder eine Funktion zum Aufheben der Zuordnung) gibt an, dass der eine Reihe von möglichen Ausnahmen, die die Funktion beenden können, ist der Satz aller Typen.

Markieren Sie eine Funktion als " **noaußer** " nur, wenn alle Funktionen, die Sie direkt oder indirekt aufruft, auch " **noaußer** " oder " **konstant**" sind. Der Compiler überprüft nicht unbedingt jeden Codepfad auf Ausnahmen, die möglicherweise zu einer " **noaußer** "-Funktion hochskalieren. Wenn eine Ausnahme den äußeren Gültigkeitsbereich einer markierten `noexcept`Funktion beendet, wird " [Std::](../standard-library/exception-functions.md#terminate) End" sofort aufgerufen, und es gibt keine Garantie dafür, dass Dekonstruktoren von im Gültigkeitsbereich befindlichen Objekten aufgerufen werden. Verwenden Sie **noaußer** anstelle des dynamischen ausnahmebezeichers `throw()`, der jetzt im Standard veraltet ist. Es wird empfohlen, `noexcept` dass Sie auf jede Funktion anwenden, die keine Ausnahme zulässt, um die aufzurufende Stapel aufzurufen. Wenn eine Funktion als " **noaußer**" deklariert wird, ermöglicht Sie dem Compiler, effizienteren Code in verschiedenen Kontexten zu generieren. Weitere Informationen finden Sie unter [Ausnahme Spezifikationen](exception-specifications-throw-cpp.md).

## <a name="example"></a>Beispiel

Eine Vorlagen Funktion, die ihr Argument kopiert, kann als "No" deklariert werden, **außer** für die Bedingung, dass das kopierte Objekt ein Plain Old Data Type (Pod) ist. Eine solche Funktion kann wie folgt deklariert werden:

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
[Ausnahme Spezifikationen (throw, noaußer)](exception-specifications-throw-cpp.md)