---
title: propput (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propput
helpviewer_keywords:
- propput attribute
ms.assetid: 1f84dda9-9cce-4e16-aaf0-b2c5219827f2
ms.openlocfilehash: 5e10edba60832112a9023f796be56d88afd52042
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514193"
---
# <a name="propput"></a>propput

Gibt eine Eigenschaftseinstellungsfunktion an.

## <a name="syntax"></a>Syntax

```cpp
[propput]
```

## <a name="remarks"></a>Hinweise

Das **PROPPUT** C++ -Attribut verfügt über die gleiche Funktionalität wie das- [PROPPUT](/windows/win32/Midl/propput) -Attribut "Mittel l".

## <a name="example"></a>Beispiel

Eine Beispiel Verwendung von **PROPPUT**finden Sie im Beispiel für [bindbare](bindable.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|`propget`, `propputref`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propputref](propputref.md)