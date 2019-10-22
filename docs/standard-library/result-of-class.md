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
ms.openlocfilehash: ab575ac31936e7003f19fc2ceb3c5b1727d0728c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689001"
---
# <a name="result_of-class"></a>result_of-Klasse

Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen akzeptiert. In c++ 14 hinzugefügt, veraltet in c++ 17.

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

*FN* -\
Der abzufragende, aufgerufene Typ.

*ArgTypes* \
Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage, um zur Kompilierzeit den Ergebnistyp `Fn` (`ArgTypes`) zu bestimmen, wobei *FN* ein Aufruf barer Typ, Verweis auf eine Funktion oder ein Verweis auf einen Aufruf baren Typ ist, der mit einer Argumentliste der Typen in *ArgTypes*aufgerufen wird. Der `type` Member der Klassen Vorlage benennt den Ergebnistyp `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, wenn der nicht ausgewertete Ausdruck `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` wohl geformt ist. Andernfalls hat die Klassen Vorlage keinen Member `type`. Der Typ *FN* und alle Typen im Parameter Paket " *ArgTypes* " müssen vollständige Typen, **void**oder Arrays mit unbekannter Grenze sein. Veraltet zugunsten von [invoke_result](invoke-result-class.md) in c++ 17.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[invoke_result-Klasse](invoke-result-class.md)
