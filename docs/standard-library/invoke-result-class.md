---
title: Invoke_result-Klasse
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: 7c03240d3ee666fcda30562279a8dbda2ca8dc7b
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006871"
---
# <a name="invokeresult-class"></a>Invoke_result-Klasse

Bestimmt den Rückgabetyp des aufrufbaren Typs, der die angegebenen Argumenttypen zum Zeitpunkt der Kompilierung verwendet. In C ++ 17-hinzugefügt.

## <a name="syntax"></a>Syntax

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parameter

*aufrufbare*<br/>
Der abzufragende, aufgerufene Typ.

*Args*<br/>
Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage, um zu bestimmen, den Ergebnistyp des *Callable*(*Args*...) zum Zeitpunkt der Kompilierung, in denen *Callable* und alle Typen im *Args* sind vollständigen Typ, ein Array mit Unbekannter Grenze oder eine möglicherweise cv-qualifizierte `void`. Die `type` Datenmember der Vorlagenklasse benennt den Rückgabetyp der *Callable* Wenn aufgerufen, wobei die Argumente *Args*... Die `type` Element wird nur definiert, wenn *Callable* kann aufgerufen werden, wenn aufgerufen, wobei die Argumente *Args*... in einem nicht ausgewerteten Kontext. Andernfalls hat die Vorlagenklasse keinen Member `type`, wodurch der SFINAE für einen bestimmten Satz von Argumenttypen zum Zeitpunkt der Kompilierung überprüft.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[invoke](functional-functions.md#invoke)
