---
title: ID (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 5faf08418771deda3086a434cff6b1900a37e36e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409498"
---
# <a name="id"></a>id

Gibt an, eine *Dispid* Parameter für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).

## <a name="syntax"></a>Syntax

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Parameter

*dispid*<br/>
Die Dispatch-ID für die Schnittstellenmethode.

## <a name="remarks"></a>Hinweise

Die **Id** C++-Attribut hat die gleiche Funktionalität wie die [Id](/windows/desktop/Midl/id) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) ein Beispiel zur Verwendung für **Id**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[Datenmemberattribute](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)