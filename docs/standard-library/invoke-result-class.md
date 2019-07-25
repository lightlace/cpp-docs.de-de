---
title: invoke_result-Klasse
ms.date: 02/21/2019
f1_keywords:
- type_traits/std::invoke_result
- type_traits/std::invoke_result_t
- type_traits/std::invoke_result::type
helpviewer_keywords:
- std::invoke_result
- std::invoke_result_t
- std::invoke_result::type
ms.openlocfilehash: 2b2051b0c854151cff9b439f5ec0a951c25a6387
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447638"
---
# <a name="invokeresult-class"></a>invoke_result-Klasse

Bestimmt den Rückgabetyp des Aufruf baren Typs, der die angegebenen Argument Typen zur Kompilierzeit annimmt. Hinzugefügt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<lass Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parameter

*Callable*\
Der abzufragende, aufgerufene Typ.

*Args*\
Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage, um den Ergebnistyp der *Aufruf baren*(*args*...) zur Kompilierzeit zu bestimmen, wobei *Callable* und alle Typen in *args* ein beliebiger vollständiger Typ, ein Array mit unbekannter Grenze `void`oder eine möglicherweise CV qualifizierte sind. Der `type` Member der Vorlagen Klasse benennt den Rückgabetyp von *Callable* , wenn er mithilfe *der Argumente Argumente*... aufgerufen wird. Der `type` Member wird nur definiert, wenn *Callable* aufgerufen werden kann, wenn er mithilfe *der Argumente Argumente*... in einem nicht ausgewerteten Kontext. Andernfalls hat die Vorlagen Klasse keinen Member `type`, der sfinae-Tests für einen bestimmten Satz von Argument Typen zur Kompilierzeit zulässt.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
