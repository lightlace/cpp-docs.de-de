---
title: is_trivially_default_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 581ebc488e733bfb149f9074126ce721b78df156
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
