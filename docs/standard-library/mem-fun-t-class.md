---
title: mem_fun_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::mem_fun_t
helpviewer_keywords:
- mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
ms.openlocfilehash: 3c6606fe4d2df3b6068c3bb8194dc380344f7d97
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689379"
---
# <a name="mem_fun_t-class"></a>mem_fun_t-Klasse

Eine Adapter Klasse, die es ermöglicht, dass eine `non_const` Member-Funktion, die keine Argumente annimmt, als unäres Funktions Objekt aufgerufen wird, wenn Sie mit einem Zeigerargument initialisiert wird. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;
};
```

### <a name="parameters"></a>Parameter

*_Pm* \
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*_Pleft* \
Das-Objekt, für das die *_Pm* -Member-Funktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

In der Klassen Vorlage wird eine Kopie von *_Pm*gespeichert, die ein Zeiger auf eine Member-Funktion der Klasse `Type` in einem privaten Member-Objekt sein muss. Er definiert seine Member-Funktion `operator()` als Rückgabe (`_Pleft` ->*  `_Pm`) ().

## <a name="example"></a>Beispiel

Der Konstruktor von `mem_fun_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).
