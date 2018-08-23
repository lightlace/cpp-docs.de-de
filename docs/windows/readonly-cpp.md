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
ms.openlocfilehash: fc70734867b0b6b7c1d9ebc5e66c45893cf1db1e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602090"
---
# <a name="readonly-c"></a>readonly (C++)

Verhindert die Zuweisung zu einem Datenelement

## <a name="syntax"></a>Syntax

```cpp
[readonly]
```

## <a name="remarks"></a>Hinweise

Das C++-Attribut **readonly** hat die gleiche Funktion wie das MIDL-Attribut [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152) .

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

[IDL-Attribute](../windows/idl-attributes.md)  
[Datenmemberattribute](../windows/data-member-attributes.md)  