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
ms.openlocfilehash: c13dcadc87c23e288c7f8c8a7f5bc9752aae5db7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853650"
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

`Fn` Der abzufragende Typ aufgerufen werden kann.

`ArgTypes` Die Typen der Argumentliste zu der aufrufbaren abzufragende Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage zum Zeitpunkt der Kompilierung zur Bestimmung des Ergebnistyps des `Fn`(`ArgTypes`), wobei `Fn` ein aufrufbarer Typ ist, ein Verweis auf eine Funktion oder der Verweis auf einen aufrufbaren Typ, der mit einer Argumentliste der Typen in `ArgTypes` bereitgestellt werden kann. Der `type`-Member der Vorlagenklasse benennt den Ergebnistyp von `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, wenn der ausgewertete Ausdruck `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` wohlgeformt ist. Andernfalls hat die Vorlagenklasse keinen `type`-Member. Der `Fn`-Typ und alle Typen im Parameterpaket `ArgTypes` müssen vollständige Typen, `void` oder Arrays mit unbekannter Grenze sein.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
