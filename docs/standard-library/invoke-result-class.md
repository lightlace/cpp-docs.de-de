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
ms.openlocfilehash: a5f67935bde103cf10c1bd9948ac1388f5221322
ms.sourcegitcommit: f38f770bfda1c174d2b81fabda7c893b15bd83a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77473887"
---
# <a name="invoke_result-class"></a>invoke_result-Klasse

Bestimmt den Rückgabetyp des Aufruf baren Typs, der die angegebenen Argument Typen zur Kompilierzeit annimmt. Hinzugefügt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Callable, class... Args>
   struct invoke_result<Callable(Args...)>;

// Helper type
template<class Callable, class... Args>
   using invoke_result_t = typename invoke_result<Callable, Args...>::type;
```

### <a name="parameters"></a>Parameter

*Aufruf Bare*\
Der abzufragende, aufgerufene Typ.

*Args*\
Die Typen der Argumentliste für den aufrufbaren, abzufragenden Typ.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Vorlage, um den Ergebnistyp der *Aufruf baren*(*args*...) zur Kompilierzeit zu bestimmen, wobei *Callable* und alle Typen in *args* ein beliebiger vollständiger Typ, ein Array mit unbekannter Grenze oder eine möglicherweise CV qualifizierte `void`sind. Der `type` Member der Klassen Vorlage benennt den Rückgabetyp von *Callable* , wenn er mit den Argumenten *args*... aufgerufen wird. Der `type` Member wird nur definiert, wenn *Callable* aufgerufen werden kann, wenn aufgerufen wird, wenn er mithilfe *der Argumente Argumente...* in einem nicht ausgewerteten Kontext. Andernfalls hat die Klassen Vorlage keinen Member `type`, der sfinae-Tests für einen bestimmten Satz von Argument Typen zur Kompilierzeit zulässt.

## <a name="requirements"></a>Voraussetzungen

**Header:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)\
[invoke](functional-functions.md#invoke)
