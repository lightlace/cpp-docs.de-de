---
title: is_trivially_copy_constructible-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 410566c623595cc941ab6e6ad21dd95bd70fe516
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963666"
---
# <a name="istriviallycopyconstructible-class"></a>is_trivially_copy_constructible-Klasse

Testet, ob der Typ einen trivialen Kopierkonstruktor aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>Parameter

*T* der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist eine Klasse, die einen trivialen Kopierkonstruktor, andernfalls er false enthält.

Ein Kopierkonstruktor für eine Klasse *T* ist trivial, wenn er implizit deklariert, die Klasse *T* verfügt über keine virtuellen Funktionen oder Basen und alle direkten Basen der Klasse *T* haben triviale Kopierkonstruktoren, die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Kopierkonstruktoren, und die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Kopierkonstruktoren.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
