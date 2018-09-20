---
title: ReadOnly (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.readonly
dev_langs:
- C++
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba2edf438e305be772894cdf3a03116f7218848c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394685"
---
# <a name="readonly-c"></a>readonly (C++)

Verhindert die Zuweisung zu einem Datenelement

## <a name="syntax"></a>Syntax

```cpp
[readonly]
```

## <a name="remarks"></a>Hinweise

Die **Readonly** C++-Attribut hat die gleiche Funktionalität wie die [Readonly](/windows/desktop/Midl/readonly) MIDL-Attribut.

Wenn Sie die Änderung eines Methodenparameters verhindern möchten, verwenden Sie das [in](../windows/in-cpp.md) -Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Verwendung des **readonly** -Attributs:

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Datenmemberattribute](../windows/data-member-attributes.md)  