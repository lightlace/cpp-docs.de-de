---
title: Last_is (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.last_is
helpviewer_keywords:
- last_is attribute
ms.assetid: 9e045ac0-fa38-4249-af55-67bde5d0a58c
ms.openlocfilehash: ce19d8d727a359054289200b2cdcb6a6427dc706
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545716"
---
# <a name="lastis"></a>last_is

Gibt den Index des letzten Elements Array übertragen werden.

## <a name="syntax"></a>Syntax

```cpp
[ last_is("expression") ]
```

### <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Eine oder mehrere Programmiersprache C-Ausdrücke. Leere Argumentliste Slots sind zulässig.

## <a name="remarks"></a>Hinweise

Die **Last_is** C++-Attribut hat die gleiche Funktionalität wie die [Last_is](/windows/desktop/Midl/last-is) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter [First_is](first-is.md) ein Beispiel für einen Abschnitt eines Arrays angeben.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Im Feld **Struktur** oder **Union**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)<br/>
[size_is](size-is.md)