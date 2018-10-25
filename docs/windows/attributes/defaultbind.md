---
title: Defaultbind (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.defaultbind
dev_langs:
- C++
helpviewer_keywords:
- defaultbind attribute
ms.assetid: b20a8437-24e6-4b6d-a2df-09fe5e1006e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89fb592a29fec5198ee96b25319e194eeaffa91f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50063600"
---
# <a name="defaultbind"></a>defaultbind

Gibt an, die einfache, bindbare Eigenschaft, die das Objekt am besten darstellt.

## <a name="syntax"></a>Syntax

```cpp
[defaultbind]
```

## <a name="remarks"></a>Hinweise

Die **Defaultbind** C++-Attribut hat die gleiche Funktionalität wie die [Defaultbind](/windows/desktop/Midl/defaultbind) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) ein Beispiel zur Verwendung für **Defaultbind**.

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
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)