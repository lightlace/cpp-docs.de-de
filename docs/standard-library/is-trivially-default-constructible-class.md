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
ms.openlocfilehash: aa7b831790804005f0649dbae0dbb98df5121106
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954733"
---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible-Klasse

Testet, ob der Typ einen trivialen Standardkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>Parameter

*Ty* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *Ty* ist eine Klasse, die einen trivialen Konstruktor aufweist; andernfalls ist Sie false.

Einen Standardkonstruktor für eine Klasse *Ty* ist trivial wenn:

- es ist eine implizit deklarierte Standardkonstruktor

- die Klasse *Ty* verfügt über keine virtuellen Funktionen

- die Klasse *Ty* hat keine virtuellen Basen

- alle direkten Basisklassen der Klasse *Ty* haben triviale Konstruktoren

- die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Konstruktoren

- die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Konstruktoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
