---
title: in (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: e97008d0399764beeca73dbbc5914e4b891df748
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514594"
---
# <a name="in-c"></a>in (C++)

Gibt an, dass ein Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden soll.

## <a name="syntax"></a>Syntax

```cpp
[in]
```

## <a name="remarks"></a>Hinweise

Das **in** C++ -Attribut verfügt über die gleiche Funktionalität wie das [in](/windows/win32/Midl/in) -Attribut.

## <a name="example"></a>Beispiel

Unter [bindbare](bindable.md) finden Sie ein Beispiel für die Verwendung von **in**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|**retval**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[ID](id.md)<br/>
[out](out-cpp.md)