---
title: mem_fun1_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 00d9322a8f0530da2e48b3f16fb52c00f9d1b075
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687736"
---
# <a name="mem_fun1_t-class"></a>mem_fun1_t-Klasse

Eine Adapter Klasse, die es ermöglicht, dass eine `non_const` Member-Funktion, die ein einzelnes Argument annimmt, als binäres Funktions Objekt aufgerufen wird, wenn es mit einem Zeigerargument initialisiert wird. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type, class Arg>
class mem_fun1_t : public binary_function<Type *, Arg, Result> {
    explicit mem_fun1_t(
    Result (Type::* _Pm)(Arg));

    Result operator()(
    Type* _Pleft,
    Arg right) const;
};
```

### <a name="parameters"></a>Parameter

*_Pm* \
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*_Pleft* \
Das-Objekt, für das die *_Pm* -Member-Funktion aufgerufen wird.

*Rechte* \
Das Argument, das an *_Pm*übergeben wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige binäre Funktion.

## <a name="remarks"></a>Hinweise

In der Klassen Vorlage wird eine Kopie von *_Pm*gespeichert, die ein Zeiger auf eine Member-Funktion der Klasse `Type` in einem privaten Member-Objekt sein muss. Er definiert seine Member-Funktion `operator()` als Rückgabe ( **_Pleft** -> \* `_Pm`) (**right**).

## <a name="example"></a>Beispiel

Der Konstruktor von `mem_fun1_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).
