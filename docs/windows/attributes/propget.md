---
title: Propget (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propget
helpviewer_keywords:
- propget attribute
ms.assetid: c9d4a97f-36dd-4b61-8eb0-b1a217598f14
ms.openlocfilehash: 044562ba870d6e36ddfcec0c7e84253b111a9eea
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514207"
---
# <a name="propget"></a>propget

Gibt eine eigenschaftenaccessorfunktion an.

## <a name="syntax"></a>Syntax

```cpp
[propget]
```

## <a name="remarks"></a>Hinweise

Das **propget** C++ -Attribut verfügt über die gleiche Funktionalität wie das-Attribut von [propget](/windows/win32/Midl/propget) .

## <a name="example"></a>Beispiel

Eine Beispiel Verwendung von **propget finden Sie**im Beispiel für [bindbare](bindable.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|`propput`, `propputref`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[propput](propput.md)<br/>
[propputref](propputref.md)