---
title: mem_fun_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 19ccd4835c4257a7f409bcf0f7bda1a898567458
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245086"
---
# <a name="memfunt-class"></a>mem_fun_t-Klasse

Eine Adapterklasse, die ermöglicht eine `non_const` Memberfunktion, die keine Argumente als wenn Sie mit einem Zeigerargument Initialisiert ein unäres Funktionsobjekt aufgerufen zu werden. Veraltet in C ++ 11, C ++ 17 entfernt.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;
};
```

### <a name="parameters"></a>Parameter

*_Pm*\
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*_Pleft*\
Das Objekt, das die *_Pm* auf Memberfunktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie des *_Pm*, die einen Zeiger auf eine Memberfunktion der Klasse sein muss `Type`, in einem privaten Memberobjekt. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert (`_Pleft`->* `_Pm`) ().

## <a name="example"></a>Beispiel

Der Konstruktor von `mem_fun_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).
