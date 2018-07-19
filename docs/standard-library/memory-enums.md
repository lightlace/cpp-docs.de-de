---
title: '&lt;memory&gt; enums | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 9b9ea485bb66292c3c0509036c22dd161a694dd3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961414"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; enums

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a> pointer_safety-Enumeration

Die Enumeration möglicher Werte, die von `get_pointer_safety` zurückgegeben werden.

Klasse pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>Hinweise

Die Bereichsbezogene **Enum** definiert die Werte, die zurückgegeben werden können `get_pointer_safety()`:

`relaxed` – nicht sicher abgeleitete Zeiger (offensichtlich die Zeiger von deklarierten oder zugeordneten Objekte) werden genauso behandelt, wie die sicher abgeleiteten.

`preferred` – wie zuvor, aber nicht sicher abgeleitete Zeiger sollten nicht dereferenziert werden.

`strict` – nicht sicher abgeleitete Zeiger werden möglicherweise anders behandelt als sicher berechnete Zeiger.

## <a name="see-also"></a>Siehe auch

[\<memory>](../standard-library/memory.md)<br/>
