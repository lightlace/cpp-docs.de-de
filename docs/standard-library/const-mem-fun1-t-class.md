---
title: const_mem_fun1_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 1af44635400037c6359b13c4f2925c3ac7f2d9d5
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689749"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t-Klasse

Eine Adapterklasse, die einer **const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Zeigerargument initialisiert wird. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>Parameter

*member_ptr* \
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*Linker* \
Das **Konstante Objekt, für das die** *member_ptr* -Member-Funktion aufgerufen wird.

*Rechte* \
Das Argument, das an *member_ptr*übergeben wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige binäre Funktion.

## <a name="remarks"></a>Hinweise

In der Klassen Vorlage wird eine Kopie von *member_ptr*gespeichert, die ein Zeiger auf eine Member-Funktion der Klasse `Type` in einem privaten Member-Objekt sein muss. Er definiert seine Member-Funktion `operator()` als Rückgabe `(left->member_ptr)(right) const`.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun1_t` wird nur selten direkt verwendet. `mem_fn` wird zum Anpassen von Element Funktionen verwendet. Ein Beispiel für die Verwendung von Membern der Element Funktion finden Sie unter [mem_fn](../standard-library/functional-functions.md#mem_fn) .
