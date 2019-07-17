---
title: const_mem_fun1_ref_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: 59790b5791dc50d217053dc7a13856d436101020
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244538"
---
# <a name="constmemfun1reft-class"></a>const_mem_fun1_ref_t-Klasse

Eine Adapterklasse, die einer **const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird. Veraltet in C ++ 11, C ++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type, class Arg>
    class const_mem_fun1_ref_t
        : public binary_function<Type, Arg, Result>
{
    explicit const_mem_fun1_ref_t(Result (Type::* Pm)(Arg) const);
    Result operator()(const Type& left, Arg right) const;
};
```

### <a name="parameters"></a>Parameter

*PM*\
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*Links*\
Die **const** -Objekt, das *Uhr* auf Memberfunktion aufgerufen wird.

*Richting*\
Das Argument, das zum übergeben wird *Uhr*.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige binäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie des *Uhr*, die einen Zeiger auf eine Memberfunktion der Klasse sein muss `Type`, in einem privaten Memberobjekt. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (`left`.\* *PM*) (`right`) **const**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun1_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).
