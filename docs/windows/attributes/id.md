---
title: ID (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 6f1d1d2b9d147e8b33b3b5fae629e0805971bb71
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501409"
---
# <a name="id"></a>id

Gibt einen *DISPID-* Parameter für eine Element Funktion an (entweder eine Eigenschaft oder eine Methode in einer Schnittstelle oder einer dispinterface).

## <a name="syntax"></a>Syntax

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Parameter

*dispid*<br/>
Die Dispatch-ID für die Schnittstellen Methode.

## <a name="remarks"></a>Hinweise

Das **ID** C++ -Attribut verfügt über die gleiche Funktionalität wie das Attribut der [ID](/windows/win32/Midl/id) -Mittell.

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung der **ID**finden Sie im Beispiel für [bindbare](bindable.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[Datenmemberattribute](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)