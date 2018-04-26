---
title: const_mem_fun_t-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::const_mem_fun_t
dev_langs:
- C++
helpviewer_keywords:
- const_mem_fun_t class
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8189148262f0996f8082db154f161c03615da530
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="constmemfunt-class"></a>const_mem_fun_t-Klasse

Eine Adapterklasse, die einer const-Memberfunktion, die keine Argumente akzeptiert, ermöglicht, als unäres Funktionsobjekt aufgerufen zu werden, wenn sie mit einem Verweisargument initialisiert wird.

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

`Pm` Ein Zeiger auf die Memberfunktion der Klasse **Typ** , um ein Funktionsobjekt konvertiert werden soll.

`Pleft` Das Objekt, das die `Pm` für Memberfunktion aufgerufen wird.

## <a name="return-value"></a>Rückgabewert

Eine anpassungsfähige unäre Funktion.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse speichert eine Kopie von `Pm`, die ein Zeiger auf eine Memberfunktion der Klasse **Type** in einem privaten Memberobjekt sein muss. Für seine Memberfunktion `operator()` definiert sie als Rückgabewert ( `Pleft`->\* `Pm`)() **const**.

## <a name="example"></a>Beispiel

Der Konstruktor von `const_mem_fun_t` wird in der Regel nicht direkt verwendet; die Hilfsfunktion `mem_fun` wird verwendet, um Memberfunktionen anzupassen. Weitere Beispiele für die Verwendung von Memberfunktionsadaptern finden Sie unter [mem_fun](../standard-library/functional-functions.md#mem_fun).

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
