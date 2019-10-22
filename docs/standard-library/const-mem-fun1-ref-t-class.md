---
title: const_mem_fun1_ref_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_ref_t
helpviewer_keywords:
- const_mem_fun1_ref_t class
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
ms.openlocfilehash: 76fae1ce29cb4c47870e45e8f946f6ff1fea1885
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688178"
---
# <a name="const_mem_fun1_ref_t-class"></a>const_mem_fun1_ref_t-Klasse

Eine Adapterklasse, die einer **const**-Memberfunktion, die ein einzelnes Argument akzeptiert, ermöglicht, als binäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird. In c++ 11 veraltet, entfernt in c++ 17.

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

*Pm* -\
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*Linker* \
Das **Konstante Objekt, für das die** *pm* -Mitglieds Funktion aufgerufen wird.

*Rechte* \
Das Argument, das *pm*zugewiesen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige binäre Funktion.

## <a name="remarks"></a>Hinweise

Die Klassen Vorlage speichert eine Kopie von *pm*, bei der es sich um einen Zeiger auf eine Member-Funktion der Klasse `Type` in einem privaten Member-Objekt handeln muss. Er definiert seine Member-Funktion `operator()` als Rückgabe von (`left`. \* *pm*) (`right`) **Konstanten**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun1_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).
