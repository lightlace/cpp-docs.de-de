---
title: is_literal_type-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b123144643fd50b019853d21e4140ba2d931f7c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844984"
---
# <a name="isliteraltype-class"></a>is_literal_type-Klasse

Testet, ob ein Typ als eine `constexpr`-Variable verwendet werden kann, oder von `constexpr`-Funktionen erstellt, verwendet oder zurückgegeben werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` ein *Literaltyp* ist; andernfalls ist sie FALSE. Ein Literaltyp ist entweder `void`, ein skalarer Typ, ein Verweistyp, ein Array von Literaltypen oder ein Literalklassentyp. Ein Literalklassentyp ist ein Klassentyp, der einen trivialen Destruktor aufweist, entweder ein aggregierter Typ ist oder mindestens über einen non-move, non-copy `constexpr`-Konstruktor verfügt. Alle seine Basisklassen und nichtstatischen Datenmember sind nicht volatile Literaltypen. Während der Typ eines Literals immer ein literal-Typ ist, enthält das Konzept eines literal-Typ alles, was der Compiler zur Kompilierzeit als ein `constexpr` auswerten kann.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
