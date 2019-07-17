---
title: '&lt;memory&gt; enums'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: b2f5b50dc1344b95e88742d346e32fc55f821336
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243847"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; enums

## <a name="pointer_safety"></a> Pointer_safety-Enumeration

Die Enumeration möglicher Werte, die von `get_pointer_safety` zurückgegeben werden.

```
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>Hinweise

Die Bereichsbezogene **Enum** definiert die Werte, die zurückgegeben werden können `get_pointer_safety()`:

`relaxed` – nicht sicher abgeleitete Zeiger (offensichtlich die Zeiger von deklarierten oder zugeordneten Objekte) werden genauso behandelt, wie die sicher abgeleiteten.

`preferred` – wie zuvor, aber nicht sicher abgeleitete Zeiger sollten nicht dereferenziert werden.

`strict` – nicht sicher abgeleitete Zeiger werden möglicherweise anders behandelt als sicher berechnete Zeiger.
