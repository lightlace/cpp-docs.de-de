---
title: is_trivially_copyable-Klasse
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copyable
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
ms.openlocfilehash: d3062ae311b63be76ba07185f4f8173afa4229cc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459751"
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable-Klasse

Testet, ob der Typ ein trivialer Kopiertyp ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parameter

*BUND*\
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist "true", wenn der Typ " *T* " ein triviale kopiert-Typ ist; andernfalls "false". Triviale Kopiertypen haben keine nicht trivialen Kopiervorgänge, Zuweisungsvorgänge oder Destruktoren. Im Allgemeinen wird ein Kopiervorgang als trivial angesehen, wenn er als eine bitweise Kopie implementiert werden kann. Integrierte Typen und Arrays trivialer Kopiertypen sind jeweils trivial kopierbar.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
