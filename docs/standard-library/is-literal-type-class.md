---
title: is_literal_type-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_literal_type
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
ms.openlocfilehash: 804ef0462308b967fc0c4c95d8dfa96476475aab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336466"
---
# <a name="isliteraltype-class"></a>is_literal_type-Klasse

Testet, ob ein Typ als eine `constexpr`-Variable verwendet werden kann, oder von `constexpr`-Funktionen erstellt, verwendet oder zurückgegeben werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist eine *Literaltyp*, andernfalls ist Sie false. Ein Literaltyp ist entweder **"void"**, ein skalarer Typ, ein Verweistyp, ein Array von Literaltypen oder ein literalklassentyp. Ein Literalklassentyp ist ein Klassentyp, der einen trivialen Destruktor aufweist, entweder ein aggregierter Typ ist oder mindestens über einen non-move, non-copy `constexpr`-Konstruktor verfügt. Alle seine Basisklassen und nichtstatischen Datenmember sind nicht volatile Literaltypen. Während der Typ eines Literals immer ein literal-Typ ist, enthält das Konzept eines literal-Typ alles, was der Compiler zur Kompilierzeit als ein `constexpr` auswerten kann.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
