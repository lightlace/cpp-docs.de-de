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
ms.openlocfilehash: 8cd72e62fcb65209482fd9677afcc2ec83356feb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689516"
---
# <a name="invoke_result-class"></a>invoke_result-Klasse

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

*Aufruf Bare* \
Der abzufragende, aufgerufene Typ.

*Args* \
Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage, um den Ergebnistyp der *Aufruf baren*(*args*...) zur Kompilierzeit zu bestimmen, wobei *Callable* und alle Typen in *args* ein beliebiger vollständiger Typ, ein Array mit unbekannter Grenze oder eine möglicherweise CV qualifizierte `void` sind. Der `type` Member der Klassen Vorlage benennt den Rückgabetyp von *Callable* , wenn er mit den Argumenten *args*... aufgerufen wird. Der `type` Member wird nur definiert, wenn *Callable* aufgerufen werden kann, wenn aufgerufen wird, wenn er mithilfe *der Argumente Argumente...* in einem nicht ausgewerteten Kontext. Andernfalls hat die Klassen Vorlage keinen Member `type`, der sfinae-Tests für einen bestimmten Satz von Argument Typen zur Kompilierzeit zulässt.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[Blaze](functional-functions.md#invoke)
