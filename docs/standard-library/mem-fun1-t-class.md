---
title: mem_fun1_t-Klasse
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::mem_fun1_t
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
ms.openlocfilehash: 9a1fe26e66eb2ad20e6889b95640fadd2b3c45a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613196"
---
# <a name="memfun1t-class"></a>mem_fun1_t-Klasse

Eine Adapterklasse, die ermöglicht eine `non_const` Memberfunktion, die ein einzelnes Argument als ein binäres Funktionsobjekt, wenn Sie mit einem Zeigerargument initialisiert aufgerufen werden.

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

*_Pm*<br/>
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*_Pleft*<br/>
Das Objekt, das die *_Pm* auf Memberfunktion aufgerufen wird.

*right*<br/>
Das Argument, das zum übergeben wird *_Pm*.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige binäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie des *_Pm*, die einen Zeiger auf eine Memberfunktion der Klasse sein muss `Type`, in einem privaten Memberobjekt. Für seine Memberfunktion `operator()` definiert sie als Rückgabewert (**_Pleft**->\* `_Pm`)(**right**).

## <a name="example"></a>Beispiel

Der Konstruktor von `mem_fun1_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
