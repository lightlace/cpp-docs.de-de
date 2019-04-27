---
title: result_of-Klasse
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
ms.openlocfilehash: f60a3ef6528da33fd1117fc940e961e9fe0987df
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185905"
---
# <a name="resultof-class"></a>result_of-Klasse

Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen akzeptiert. Hinzugefügt in C ++ 14, C ++ 17 veraltet.

## <a name="syntax"></a>Syntax

```cpp
template<class>
struct result_of; // Causes a static assert

template <class Fn, class... ArgTypes>
struct result_of<Fn(ArgTypes...)>;

// Helper type
template<class T>
   using result_of_t = typename result_of<T>::type;
```

### <a name="parameters"></a>Parameter

*Fn*<br/>
Der abzufragende, aufgerufene Typ.

*ArgTypes*<br/>
Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage zum Zeitpunkt der Kompilierung den Ergebnistyp des bestimmen `Fn`(`ArgTypes`), wobei *Fn* ist ein aufrufbarer Typ, Verweis auf Funktion oder Verweis auf einen aufrufbaren Typ, mit der eine Argumentliste der Typen in aufgerufen *ArgTypes*. Der `type`-Member der Vorlagenklasse benennt den Ergebnistyp von `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, wenn der ausgewertete Ausdruck `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` wohlgeformt ist. Andernfalls hat die Vorlagenklasse keinen `type`-Member. Der Typ *Fn* und alle Typen im parameterpaket *ArgTypes* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze. Als veraltet markierte zugunsten des [Invoke_result](invoke-result-class.md) in C ++ 17.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[Invoke_result-Klasse](invoke-result-class.md)<br/>
