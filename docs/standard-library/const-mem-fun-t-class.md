---
title: const_mem_fun_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_t
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
ms.openlocfilehash: 0bdfdbac7a23a4b0e3b830b05990bf028c7bb316
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244548"
---
# <a name="constmemfunt-class"></a>const_mem_fun_t-Klasse

Eine Adapterklasse, die einer const-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird. Veraltet in C ++ 11, C ++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type>
class const_mem_fun_t : public unary_function <Type *, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type* Pleft) const;
};
```

### <a name="parameters"></a>Parameter

*PM*\
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*Pleft*\
Das Objekt, das die *Uhr* auf Memberfunktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie des *Uhr*, die einen Zeiger auf eine Memberfunktion der Klasse sein muss `Type`, in einem privaten Memberobjekt. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (`Pleft` -> \* `Pm`) () **const**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).
