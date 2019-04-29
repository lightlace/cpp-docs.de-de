---
title: in (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.in
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
ms.openlocfilehash: 06d78552ef2ebb878ed630eb377e6249ba60cad4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409342"
---
# <a name="in-c"></a>in (C++)

Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.

## <a name="syntax"></a>Syntax

```cpp
[in]
```

## <a name="remarks"></a>Hinweise

Die **in** C++-Attribut hat die gleiche Funktionalität wie die [in](/windows/desktop/Midl/in) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter [bindbare](bindable.md) ein Beispiel zur Verwendung für **in**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Parameter, für die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|**retval**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[ID](id.md)<br/>
[out](out-cpp.md)