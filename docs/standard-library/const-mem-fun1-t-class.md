---
title: const_mem_fun1_t-Klasse| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun1_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d42bc03e9fcb16ba8c0832a10ee96b361c525523
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699972"
---
# <a name="constmemfun1t-class"></a>const_mem_fun1_t-Klasse

Eine Adapterklasse, die einer **const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* _Pm)(Arg) const);
    Result operator()(const Type* _Pleft, Arg right) const;
};
```

### <a name="parameters"></a>Parameter

*_Pm*<br/>
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*_Pleft*<br/>
Die **const** -Objekt, das *_Pm* auf Memberfunktion aufgerufen wird.

*right*<br/>
Das Argument, das zum übergeben wird *_Pm*.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige binäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie des *_Pm*, die einen Zeiger auf eine Memberfunktion der Klasse sein muss `Type`, in einem privaten Memberobjekt. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert ( *_Pleft*->\*<em>Uhr</em>) ( *rechten* ) **Const**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun1_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
