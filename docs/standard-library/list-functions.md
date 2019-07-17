---
title: '&lt;Liste&gt; Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 04f00a9274018432cd03917ae5485f2d395649e4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269022"
---
# <a name="ltlistgt-functions"></a>&lt;Liste&gt; Funktionen

## <a name="swap"></a> Swap

Tauscht die Elemente zweier Listen aus.

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>Parameter

*Links*\
Ein Objekt vom Typ `list`.

*Richting*\
Ein Objekt vom Typ `list`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt `left.swap(right)` aus.
