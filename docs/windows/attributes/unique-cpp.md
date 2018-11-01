---
title: eindeutige (C++ COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.unique
helpviewer_keywords:
- unique attribute
ms.assetid: abd7ed14-5ae7-44a8-8333-0058e9c92b2f
ms.openlocfilehash: 9d049983bb072e073180f1821f04b79e5f5c7444
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512828"
---
# <a name="unique-c"></a>unique (C++)

Gibt einen eindeutigen Zeiger.

## <a name="syntax"></a>Syntax

```cpp
[unique]
```

## <a name="remarks"></a>Hinweise

Die **eindeutige** C++-Attribut hat die gleiche Funktionalität wie die [eindeutige](/windows/desktop/Midl/unique) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter den [Ref](ref-cpp.md) Beispiel für ein Beispiel für die Verwendung von **eindeutige**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**TypeDef**, **Struktur**, **Union**, Schnittstellenparameter,-Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)