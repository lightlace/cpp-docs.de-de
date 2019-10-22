---
title: mem_fun_ref_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_ref_t
helpviewer_keywords:
- mem_fun_ref_t class
ms.assetid: 7dadcac3-8d33-4e4b-a792-81bd53d3df39
ms.openlocfilehash: d8f5ef05d1bdeec694cdf22d7e7a163478127dfc
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687761"
---
# <a name="mem_fun_ref_t-class"></a>mem_fun_ref_t-Klasse

Eine Adapter Klasse, die es ermöglicht, dass eine `non_const` Member-Funktion, die keine Argumente annimmt, als unäres Funktions Objekt aufgerufen wird, wenn Sie mit einem Verweis Argument initialisiert wird. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type>
class mem_fun_ref_t : public unary_function<Type, Result> {
    explicit mem_fun_ref_t(
    Result (Type::* _Pm)());

    Result operator()(Type& left) const;
};
```

### <a name="parameters"></a>Parameter

*_Pm* \
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*Linker* \
Das-Objekt, für das die *_Pm* -Member-Funktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

In der Klassen Vorlage wird eine Kopie von *_Pm*gespeichert, die ein Zeiger auf eine Member-Funktion der Klasse `Type` in einem privaten Member-Objekt sein muss. Er definiert seine Member-Funktion `operator()` als Rückgabe von (**left**. * `_Pm`) ().

## <a name="example"></a>Beispiel

Der Konstruktor von `mem_fun_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).
