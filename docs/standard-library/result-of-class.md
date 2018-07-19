---
title: result_of-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b385d822c2f58d26938b3300207a790dc1193060
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953022"
---
# <a name="resultof-class"></a>result_of-Klasse

Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen akzeptiert.

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

*Fn* der aufrufbare abzufragende Typ.

*ArgTypes* die Typen der Argumentliste, die das abzufragende, aufgerufene Typ Abfrage.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage zum Zeitpunkt der Kompilierung den Ergebnistyp des bestimmen `Fn`(`ArgTypes`), wobei *Fn* ist ein aufrufbarer Typ, Verweis auf Funktion oder Verweis auf einen aufrufbaren Typ, mit der eine Argumentliste der Typen in aufgerufen *ArgTypes*. Der `type`-Member der Vorlagenklasse benennt den Ergebnistyp von `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, wenn der ausgewertete Ausdruck `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` wohlgeformt ist. Andernfalls hat die Vorlagenklasse keinen `type`-Member. Der Typ *Fn* und alle Typen im parameterpaket *ArgTypes* müssen vollständige Typen werden **"void"**, oder Arrays mit Unbekannter Grenze.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
