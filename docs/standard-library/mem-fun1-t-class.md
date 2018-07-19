---
title: mem_fun1_t-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- mem_fun1_t class
ms.assetid: 01a8c2c2-b2f7-4e3f-869c-5b5b9f06ea54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d73beb5b935a729eb5e304eb03cbc37536c4d0e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963153"
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

*_Pm* ein Zeiger auf die Memberfunktion der Klasse `Type` in ein Funktionsobjekt konvertiert werden.

*_Pleft* das Objekt, das die *_Pm* auf Memberfunktion aufgerufen wird.

*richtige* das Argument, das zum übergeben wird *_Pm*.

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
