---
title: is_trivially_copyable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1577f067b398a53ab4f91847f890beaa96f0639f
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102810"
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable-Klasse

Testet, ob der Typ ein trivialer Kopiertyp ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des typprädikats ist true, wenn der Typ *T* ist ein trivialer Kopiertyp, andernfalls er false enthält. Triviale Kopiertypen haben keine nicht trivialen Kopiervorgänge, Zuweisungsvorgänge oder Destruktoren. Im Allgemeinen wird ein Kopiervorgang als trivial angesehen, wenn er als eine bitweise Kopie implementiert werden kann. Integrierte Typen und Arrays trivialer Kopiertypen sind jeweils trivial kopierbar.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
