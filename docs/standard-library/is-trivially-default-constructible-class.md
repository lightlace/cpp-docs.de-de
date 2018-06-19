---
title: is_trivially_default_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f2bd65fa7145325fd4c5c2f1a2483851d0738b7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852135"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible-Klasse

Testet, ob der Typ einen trivialen Standardkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der `Ty` Typ eine Klasse ist, die einen trivialen Konstruktor aufweist; andernfalls „false“.

Einen Standardkonstruktor für eine Klasse `Ty` ist trivial, wenn:

- es ist eine implizit deklarierte Standardkonstruktor

- die Klasse `Ty` hat keine virtuellen Funktionen

- die Klasse `Ty` hat keine virtuellen Basen

- alle direkten Basisklassen der Klasse `Ty` weisen triviale Konstruktoren auf

- die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Konstruktoren

- die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Konstruktoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
