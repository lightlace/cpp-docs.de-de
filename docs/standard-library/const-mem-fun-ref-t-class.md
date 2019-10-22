---
title: const_mem_fun_ref_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_ref_t
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
ms.openlocfilehash: 8ce29eb0d2122dbd95fea34fa59f3fa11b9b388e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689759"
---
# <a name="const_mem_fun_ref_t-class"></a>const_mem_fun_ref_t-Klasse

Eine Adapterklasse, die einer **const**-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird. In c++ 11 veraltet, entfernt in c++ 17.

## <a name="syntax"></a>Syntax

```cpp
template <class Result, class Type>
    class const_mem_fun_ref_t
: public unary_function<Type, Result>
{
    explicit const_mem_fun_t(Result (Type::* Pm)() const);
    Result operator()(const Type& left) const;
};
```

### <a name="parameters"></a>Parameter

*Pm* -\
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*Linker* \
Das-Objekt, für das die *pm* -Mitglieds Funktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

Die Klassen Vorlage speichert eine Kopie von *pm*, bei der es sich um einen Zeiger auf eine Member-Funktion der Klasse `Type` in einem privaten Member-Objekt handeln muss. Er definiert seine Member-Funktion `operator()` als Rückgabe von (**left**. \* `Pm`) () **Konstanten**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).
