---
title: '&lt;forward_list&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: b425461f1428470b04a525efdd9a702ae038a283
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477336"
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt;-Funktionen

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

Tauscht die Elemente zweier Vorwärtslisten aus.

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Ein Objekt vom Typ `forward_list`.|
|*right*|Ein Objekt vom Typ `forward_list`.|

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion führt `left.swap(right)` aus.

## <a name="see-also"></a>Siehe auch

[<forward_list>](../standard-library/forward-list.md)<br/>
