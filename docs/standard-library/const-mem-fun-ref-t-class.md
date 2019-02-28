---
title: const_mem_fun_ref_t-Klasse
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun_ref_t
helpviewer_keywords:
- const_mem_fun_ref_t class
ms.assetid: 316ddbaa-9f46-4931-8eba-ea4ca66360ef
ms.openlocfilehash: 16025764cdcf28900c30ef53dced871998f8bd07
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006577"
---
# <a name="constmemfunreft-class"></a>const_mem_fun_ref_t-Klasse

Eine Adapterklasse, die einer **const**-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird. Veraltet in C ++ 11, C ++ 17 entfernt.

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

*Pm*<br/>
Ein Zeiger auf die Memberfunktion der Klasse `Type`, die in ein Funktionsobjekt konvertiert werden soll.

*left*<br/>
Das Objekt, das die *Uhr* auf Memberfunktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie des *Uhr*, die einen Zeiger auf eine Memberfunktion der Klasse sein muss `Type`, in einem privaten Memberobjekt. Sie definiert ihre Memberfunktion `operator()` als Rückgabewert ( **linken**.\* `Pm`) () **const**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun_ref_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun_ref` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun_ref](../standard-library/functional-functions.md#mem_fun_ref).

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
